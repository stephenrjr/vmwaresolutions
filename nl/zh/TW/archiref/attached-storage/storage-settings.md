---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-13"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 連接儲存空間的配置及設定
{: #storage-settings}

此設計僅支援透過 NFS 第 3 版連接共用儲存空間。不支援 NFS 第 4 版及 4.1 版。

此設計的連接儲存空間僅限於與 vCenter Server 解決方案相同的 {{site.data.keyword.CloudDataCent_notm}} 中可用的 {{site.data.keyword.cloud_notm}} 儲存空間。此外，依預設，儲存至該資料儲存庫的所有虛擬磁碟都採取精簡佈建的方式。
{:note}

架構指定使用 {{site.data.keyword.cloud_notm}} 儲存空間中的 DNS 名稱來連接 NFS 第 3 版資料儲存庫，以連接至共用。NFS 共用會連接到 vCenter Server 叢集中的所有主機，並放置在已啟用儲存空間 DRS 的資料儲存庫叢集中。

## vSphere 儲存空間分散式資源排程器（儲存空間 DRS）
{: #storage-settings-vsphere-storage-drs}

使用「儲存空間 DRS」來管理資料儲存庫叢集的聚集資源。啟用「儲存空間 DRS」之後，它會提供關於虛擬機器 (VM) 磁碟放置和移轉的建議，以平衡資料儲存庫叢集裡各資料儲存庫之間的空間和 I/O 資源。

開啟儲存空間 DRS 之後，下列特性可供使用：
* 資料儲存庫叢集內各資料儲存庫之間的空間負載平衡
* 資料儲存庫叢集內各資料儲存庫之間的 I/O 負載平衡
* 根據空間和 I/O 工作負載的虛擬磁碟起始位置。

在本設計中，已啟用「儲存空間 DRS」，且自動化層次設為**全自動**。因此，會自動移轉檔案，讓資料叢集上的資源用量達到最佳化。因為叢集為全自動，所以所有其他「儲存空間 DRS」選項都會設為**使用叢集設定**。

## NFS 第 3 版的儲存空間 DRS 運行環境設定
{: #storage-settings-drs-nfs3}

可指定所使用空間的臨界值和 I/O 延遲來決定「儲存空間 DRS」的積極程度。「儲存空間 DRS」會收集資料儲存庫叢集裡的資料儲存庫資源用量資訊。vCenter Server 使用此資訊來產生虛擬磁碟在資料儲存庫上的放置建議。

若對資料儲存庫叢集設定低積極程度，則「儲存空間 DRS」只有在必要時才會建議「儲存空間 vMotion」移轉。例如，如果 I/O 負載、空間使用率或兩者不平衡性很高，則「儲存空間 DRS」會建議移轉。如果對資料儲存庫叢集設定高積極程度，則每當資料儲存庫叢集可從空間或 I/O 負載平衡中獲益時，「儲存空間 DRS」就會建議移轉。

資料儲存庫叢集中可用的臨界值種類如下。

* 空間使用率：當資料儲存庫上的空間使用率百分比大於您在 vSphere Web Client 中設定的臨界值時，「儲存空間 DRS」會產生建議或執行移轉。
* I/O 延遲：當針對資料儲存庫一天所測量到的第 90 百分位 I/O 延遲大於臨界值時，「儲存空間 DRS」會產生建議或執行移轉。

在本設計中，已啟用「儲存空間 DRS 運行環境設定」，且臨界值保留其各自的預設值。請根據工作負載 I/O 需求和延遲靈敏度來變更這些值。

下表顯示 VMware vSphere Web Client 中的設定。

表 1. 儲存空間 DRS 運行環境設定

| 設定          | 值  |
|:--------------- |:------ |
|對 SDRS 建議啟用 I/O 度量值| 已選取|
| 使用空間 | 已選取，設為 80% |
| I/O 延遲臨界值 | 15 毫秒 |

如需在 vSphere Web Client 中配置這些設定的相關資訊，請參閱 [Set Storage DRS Runtime Rules in the vSphere Web Client](https://docs.vmware.com/en/VMware-vSphere/5.5/com.vmware.vsphere.resmgmt.doc/GUID-AD2D13CE-539B-48C3-BBC9-E55A834874F0.html)。

## NFS 第 3 版的儲存空間 I/O 控制
{: #storage-settings-io-control-nfs-v3}

環境中啟用 SIOC（儲存空間 I/O 控制）時，會變更單一 VM 的裝置佇列長度。裝置佇列長度的變更，會將所有 VM 的儲存空間陣列佇列，縮減為儲存空間佇列的相等共用和節流控制。只有在資源受限且儲存空間 I/O 延遲高於定義的臨界值時，SIOC 才會介入。

為了讓 SIOC 判斷儲存裝置何時壅塞或受限，需要已定義的臨界值。不同儲存空間類型的壅塞臨界值延遲也不同。本設計建議且實作的臨界值延遲為 10 毫秒。

您可以使用 SIOC 限制個別 VM 的個別虛擬磁碟，或授與它們不同的共用。限制磁碟及授與不同共用，可讓您比對及調整環境，使之適合具備所獲取之檔案儲存空間磁區 IOPS 數目的工作負載。此限制是由 IOPS 設定，可設定不同的加權或共用。

虛擬磁碟共用設為**高**（2,000 個共用）時，其接收的 I/O 是設為**正常**（1,000 個共用）的磁碟的兩倍之多，更是設為**低**（500 個共用）的磁碟的四倍之多。所有 VM 的預設值都是**正常**，因此，您得為需要它的 VM 調整**正常**設定。

## NFS 第 3 版的其他儲存空間
{: #storage-settings-additional-storage-nfs-v3}

當環境因為空間不足或高延遲而需要新增更多儲存空間時，您可以從主控台訂購另一個 NFS 共用。訂購共用之後，請將匯出連接至叢集裡的 vSphere ESXi 主機，並將它放入儲存空間叢集。在儲存空間叢集裡放置新的 NVS 共用，可以有效且無縫地橫向擴充與環境相關聯的儲存空間，而不會因儲存空間層次移轉對您造成負擔。

## 進階配置參數
{: #storage-settings-adv-config-param}

本設計新增了 {{site.data.keyword.cloud_notm}} 所建議的進階配置參數。因此，下列參數會設定在已連接至 {{site.data.keyword.cloud_notm}} NFS 共用的每一部 vSphere ESXi 主機上。

表 2. NFS 進階配置參數

| 參數               | 值  |
|:--------------- |:------ |
| Net.TcpipHeapSize | 32 |
| Net.TcpipHeapMax | 512 |
| NFS.MaxVolumes | 256 |
| NFS.HeartbeatMaxFailures | 10 |
| NFS.HeartbeatFrequency  | 12 |
| NFS.HeartbeatTimeout | 5 |
| NFS.MaxQueueDepth | 64 |

## 相關鏈結
{: #storage-settings-related}

* [解決方案概觀](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_overview)

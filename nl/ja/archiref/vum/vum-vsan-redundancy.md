---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

# 仮想マシン vSAN の冗長性
{: #vum-vsan-redundancy}

vSAN クラスターで vSphere ESXi ホストを保守モードにする場合は、データ退避モードを選択する必要があります。 モードの選択は、vSAN データ・ストアを消費している仮想マシン (VM) および仮想アプライアンスに影響を与える可能性があります。
* **全データ・マイグレーション**では、ホストからすべてのデータを退避し、vSAN クラスター内の他の vSphere ESXi ホストに移動します。 この退避モードでは大量のデータが転送されるため、非常に多くの時間とリソースが消費されます。 選択したホストのローカル・ストレージ上にあるすべてのコンポーネントは、クラスター内の別の場所にマイグレーションされます。 ホストが保守モードにある場合、すべての VM および仮想アプライアンスはストレージ・コンポーネントにアクセスでき、割り当てられたストレージ・ポリシーに引き続き準拠します。 すべてのデータを退避するには長時間かかる場合があり、アップグレードの保守ウィンドウが長期間にわたる可能性があります。
* **アクセシビリティーを確保するデータ退避**モードはデフォルト・オプションであり、vSphere ESXi ホストが保守モードの場合、vSAN では、ホスト上のアクセス可能なすべての VM または仮想アプライアンスに引き続きアクセスできます。 部分的なデータのみの退避が発生した場合、退避時に VM または仮想アプライアンスが VM ストレージ・ポリシーに完全には準拠しなくなり、そのすべてのレプリカにアクセスできなくなる可能性があります。 ホストが保守モードのときに障害が発生し、許容される障害のプライマリー・レベルが 1 に設定されている場合、データ損失が発生して、VM または仮想アプライアンスを使用できなくなる可能性があります。
* **データ・マイグレーションなし**モードでは、ホストが保守モードになるとき、vSAN はホストからデータを退避しません。 これにより、保守モードになる時間が短縮されるため、保守ウィンドウの期間は短縮されますが、一部の VM または仮想アプライアンスはアクセス不能になる可能性があります。

このセクションでは、新しい VM ストレージ・ポリシーを作成します。このポリシーを使用すると、保守ウィンドウを短縮するために**アクセシビリティーを確保するデータ退避**モードが選択されますが、これにより、別のホストが保守モードであるときにホストの障害が発生して、VM または仮想アプライアンスがアクセス不能になるというリスクが軽減されます。 vSAN ホストが保守モードになったときに VM または仮想アプライアンスが非冗長にならないようにするには、修復アクションを実行する前に以下のプロセスを実行します。 少なくとも 6 つのホストが存在するクラスターが必要になります。

1. 「RAID 5/6」および「FTT =2 (RAID 6)」が設定された新しい vSAN プロファイルを作成してから、必要な VM または仮想アプライアンスにこのポリシーを適用します。

2. vSAN で同期が完了するまで待機してから、修復アクションを開始します。 完了状況を確認するには、クラスターの**「vSAN Virtual Objects monitoring」ページ**にナビゲートして、**「Completion Status」**を確認します。

## 関連リンク
{: #vum-vsan-redundancy-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} ソリューションのアーキテクチャー](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} Digital Technical Engagement](https://ibm-dte.mybluemix.net/vmware) (デモンストレーション)

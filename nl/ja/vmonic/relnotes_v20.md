---

copyright:

  years:  2016, 2017

lastupdated: "2017-11-20"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# V2.0 のリリース・ノート
{: #relnotes_v20}

このリリースには、新機能、コンポーネントの更新、使いやすさの向上、バグ修正などが含まれています。 各リリースの修正された問題のリスト、製品に関する既知の問題、および {{site.data.keyword.vmwaresolutions_full}} を使用するためのヒントについては、[{{site.data.keyword.vmwaresolutions_short}} dW の回答](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}を参照してください。

## FortiGate Virtual Appliance on IBM Cloud
{: #relnotes_v20-fva}

FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} サービスが、V2.0 以降の VMware Cloud Foundation インスタンスと VMware vCenter Server インスタンスで使用できるようになりました。 このサービスは、お客様の環境に FortiGate Virtual Appliance の高可用性 (HA) ペアをデプロイします。これにより、仮想インフラストラクチャー内にクリティカルなセキュリティー制御を実装してリスクを軽減できます。

FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} サービスを組み込んだ形でインスタンスを注文するか、後からインスタンスの詳細ページの**「サービス」**タブで既存のインスタンスにこのサービスを追加します。 このサービスで、デプロイメント・サイズとライセンスについての 3 つのオプションの中から 1 つを要件に応じて選択します。 サービスが正常にインストールされたら、FortiGate コンソールから FortiGate Virtual Appliance のファイアウォール・ルールを管理および構成します。

詳しくは、以下のトピックを参照してください。
* [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} のコンポーネントと考慮事項](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_considerations)
* [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} の管理](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingfortinetvm)

## F5 on IBM Cloud および FortiGate Virtual Appliance on IBM Cloud の複数サービス・インストール
{: #relnotes_v20-multiple-services}

Cloud Foundation インスタンスでも vCenter Server インスタンスでも、F5 on {{site.data.keyword.cloud_notm}} サービスおよび FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} サービスの複数のインスタンスをインストールできるようになりました。 インスタンスの注文中に F5 サービスまたは FortiGate サービスを選択するときに、後でインストールする追加のサービス・インスタンスと区別するために、サービス・インスタンスの名前を指定する必要があります。

インスタンスのデプロイメントが完了したら、インスタンスの詳細ページの**「サービスの追加」**タブで F5 または FortiGate サービスをインストールして、サービスのインスタンスを追加できます。 サービス・インスタンスは一度に 1 つしか追加できないので、サービスに追加するすべてのインスタンスについてこの処理を繰り返す必要があります。

詳しくは、[vCenter Server インスタンスのサービスの注文、表示、削除](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices)を参照してください。

## FortiGate Security Appliance on IBM Cloud の更新
{: #relnotes_v20-fsa}

このリリースでは、Fortinet on {{site.data.keyword.cloud_notm}} サービスの名前が FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} に変更されました。 このサービスの FortiGate Security Appliance (FSA) のペアには、インスタンスへのデプロイ時にデフォルトで保護が構成されます。
* 新規の Cloud Foundation インスタンスまたは vCenter Server インスタンスの一部として FSA のペアをデプロイすると、FSA は、インスタンスからパブリック・ネットワークへの必要なアウトバウンド通信のみを許可し、他のすべての通信を拒否するように構成されます。
* 既存の Cloud Foundation インスタンスまたは vCenter Server インスタンスの一部として FSA のペアをデプロイすると、FSA には、インスタンスからパブリック・ネットワークへの必要な管理用アウトバウンド通信をすべて許可する明示的なルールが構成されます。また、既存のアプリケーション・トラフィックが中断されないように、他のすべての通信を許可するルールも構成されます。

どのような場合でも、必要な通信だけを許可して他のすべての通信を拒否するように、お客様が FSA 設定を慎重に管理する必要があります。

## 完全修飾ドメイン・ネームの形式の統一
{: #relnotes_v20-fqdn}

完全修飾ドメイン・ネーム (FQDN) の表記がすべてのインスタンスで統一されました。 注文時に、独自のサブドメイン接頭部とホスト名接頭部を入力すると、FQDN 形式の業界規則に従うことができます。 例えば、`host-name-prefix<n>.subdomain-prefix.domain-name` と入力します。

詳しくは、以下のトピックを参照してください。
* [vCenter Server インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [新規 vSphere クラスターの注文](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## インスタンス注文中のワークロードとストレージの見積もり
{: #relnotes_v20-estimates-order}

* VMware vSphere on {{site.data.keyword.cloud_notm}} の注文中に、注文するインスタンスで実行できる仮想マシン数の見積もりが表示されます。
* Cloud Foundation および vCenter Server の注文中に、注文するインスタンスで使用できるストレージ容量の見積もりが表示されます。

詳しくは、以下のトピックを参照してください。
* [vCenter Server インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [新規 vSphere クラスターの注文](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## VMware Cloud Foundation インスタンスの更新
{: #relnotes_v20-vcf}

現行リリースでは、新規デプロイメントに以下のコンポーネントの更新と改善が適用されます。

* VMware vSphere Enterprise Plus 6.5u1 (5969303)
* VMware SDDC Manager 2.4
* VMware vCenter Server 6.5U1a
* VMware vSAN 6.6.1
* VMware NSX for vSphere 6.3.4
* VMware ESXi 6.5、パッチ・リリース ESXi650-201710401-BG。 esx-base、esx-tboot、vsan、vsanhealth VIB の更新 (2151061)。 パッチについて詳しくは、[VMware vCenter Server Appliance Photon OS Security Patches](https://docs.vmware.com/en/VMware-vSphere/6.5/rn/vcenter-server-appliance-photonos-security-patches.html){:new_window} を参照してください。

既存のインスタンス (リリース V1.9 以前) を、このリストに挙げられているコンポーネント・バージョンにアップグレードすることはできません。
{:note}

### Cloud Foundation インスタンスのクラスター・サポート
{: #relnotes_v20-vcf-cluster}

V2.0 以降のリリースでデプロイされた Cloud Foundation インスタンスでは、クラスターを使用して ESXi サーバーを管理できるので、リソース管理と可用性が向上します。 インスタンスの注文時に構成した ESXi サーバーは、デフォルトでは **SDDC-Cluster** としてグループ化されます。

インスタンスの詳細ページの**「インフラストラクチャー」**タブで、クラスターの詳細を表示したり、最大 5 つのクラスターをインスタンスに追加したりできます。 インスタンスの容量を拡張または縮小する場合は、ESXi サーバーを追加または削除するクラスターを選択できます。

### Cloud Foundation インスタンスのカスタム vSAN ストレージのサポート
{: #relnotes_v20-custom-vsan-vcf}

インスタンスの注文の中で vSAN ストレージ・ドライブの数とサイズを選択して、vSAN ストレージ構成をカスタマイズできるようになりました。

### Cloud Foundation インスタンスの VMware vSAN ライセンス・エディションの選択肢: Advanced または Enterprise
{: #relnotes_v20-vsan-license}

Cloud Foundation インスタンスの注文の中で、必要な vSAN ライセンス・エディションを選択できるようになりました。 注文の中でライセンスを購入することも、ライセンス持ち込み (BYOL) を利用することもできます。

### Cloud Foundation インスタンス用の新たに標準化された IBM ベア・メタル・サーバー構成
{: #relnotes_v20-vcf-bare-metal}

以下のベア・メタル・サーバーの構成設定を使用できるようになりました。
* スモール (Dual Intel Xeon E5-2650 v4 / 合計 24 コア、2.2 GHz / 128 GB RAM / 12 ディスク)
* ラージ (Dual Intel Xeon E5-2690 v4 / 合計 28 コア、2.6 GHz / 512 GB RAM / 12 ディスク)

シャーシには 12 個のディスク用のスペースがあります。 すべてのスロットが使用されているわけではありません。 **「スモール」**構成では 2 つの 1.9 TB Micron 5100 MAX ドライブが提供され、**「ラージ」**構成では 4 つの 3.8 TB Micron 5100 PRO ドライブが提供されます。
{:note}

## VMware vCenter Server インスタンスの更新
{: #relnotes_v20-vcs}

現行リリースでは、新規デプロイメントに以下のコンポーネントの更新が適用されます。

* VMware vSphere Enterprise Plus 6.5u1 (5969303)
* VMware vCenter Server 6.5U1a
* VMware vSAN 6.6.1
* VMware NSX for vSphere 6.3.4

VMware vSAN コンポーネントの有無に関わらず、vCenter Server のカスタマイズ注文には必ず 12 ディスク・シャーシのサーバーが組み込まれます。 このサーバーが組み込まれることで、見積もり価格の PDF で vSAN なしの注文の{{site.data.keyword.baremetal_short}}のコストが若干高くなります。
{:note}

コンポーネントについて詳しくは、[vCenter Server の概要](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)を参照してください。

### vCenter Server インスタンスのマルチサイト構成のサポート
{: #relnotes_v20-vcs-multisite}

プライマリー・インスタンスに接続されたセカンダリー・インスタンスに加えて、単一の vCenter Server インスタンスをデプロイできるようになりました。 マルチサイト構成モデルでは、ハブ・アンド・スポーク・トポロジーでプライマリー・サイトと最大 7 つのセカンダリー・サイトを使用します。

詳しくは、[vCenter Server インスタンスのマルチサイト構成](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_multisite)を参照してください。

### vCenter Server インスタンスのカスタム vSAN ストレージのサポート
{: #relnotes_v20-custom-vsan-vcs}

vSAN ストレージを、vCenter Server インスタンスのプライマリー・インスタンスとセカンダリー・インスタンスの両方で使用できるようになりました。 これは、ユーザー・カスタマイズ型の構成を選択した場合にのみ使用できます。 vCenter Server インスタンスの注文中に、必要な vSAN ライセンス・エディション (Advanced または Enterprise) を選択できるようになりました。 注文の中でライセンスを購入することも、ライセンス持ち込み (BYOL) を利用することもできます。

詳しくは、[vCenter Server インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)を参照してください。

### VMware vCenter Server インスタンスでのライセンス持ち込み (BYOL)
{: #relnotes_v20-byol}

vCenter Server インスタンスで BYOL を利用できるようになりました。 vCenter Server インスタンスの注文時に、所有している vCenter Server、vSphere、vSAN、および NSX VMware ライセンスを 1 つ以上使用します。

詳しくは、以下のトピックを参照してください。
* [vCenter Server インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [新規 vSphere クラスターの注文](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## VMware vSphere on IBM Cloud の更新
{: #relnotes_v20-vss}

### ベア・メタル・サーバーのための新しいディスク・タイプ
{: #relnotes_v20-disk-type}

VMware vSAN コンポーネントの場合、{{site.data.keyword.baremetal_short}}に以下のディスク・タイプを使用できるようになりました。
* 960 GB SSD SED
* 1.9 TB SSD SED
* 3.8 TB SSD SED

**注**:
* 3.8 TB SSD SED ドライブは、{{site.data.keyword.CloudDataCent_notm}}で一般提供が開始されたらサポートされます。
* VMware vSAN コンポーネントの有無に関わらず、注文には必ず 12 ディスク・シャーシのサーバーが組み込まれます。 このサーバーが組み込まれることで、見積もり価格の PDF で vSAN なしの注文の{{site.data.keyword.baremetal_short}}のコストが若干高くなります。

詳しくは、[新規 vSphere クラスターの注文](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)を参照してください。

## NetApp ONTAP Select on IBM Cloud の更新
{: #relnotes_v20-netapp}

### 新しいベア・メタル・サーバー・オプション
{: #relnotes_v20-netapp-bare-metal}

以下のベア・メタル・サーバーの構成オプションを使用できるようになりました。
* **ハイパフォーマンス (ミディアム)** – プレミアム・ライセンス / Dual Intel Xeon E5-2650 v4 (合計 24 コア、2.2 GHz) / 128 GB RAM / ノードあたり 22 個の 1.9 TB SSD ドライブ容量 / 4 ノード・クラスターの実効容量 – 59 TB
* **ハイパフォーマンス (ラージ)** – プレミアム・ライセンス / Dual Intel Xeon E5-2650 v4 (合計 24 コア、2.2 GHz) / 128 GB RAM / ノードあたり 22 個の 3.8 TB SSD ドライブ容量 / 4 ノード・クラスターの実効容量 – 118 TB
* **大容量** – 標準ライセンス / Dual Intel Xeon E5-2650 v4 (合計 24 コア、2.2 GHz) / 64 GB RAM / ノードあたり 10 個の 4 TB SATA ドライブ容量 / 4 ノード・クラスターの実効容量 – 60 TB

3.8 TB SSD ドライブは、{{site.data.keyword.CloudDataCent_notm}}で一般提供が開始されたらサポートされます。
{:note}

詳しくは、以下のトピックを参照してください。
* [NetApp ONTAP Select の概要](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_netappoverview)
* [NetApp ONTAP Select インスタンスの注文](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)

## 新規資料および更新された資料
{: #relnotes_v20-new-docs}

VMware Cloud Foundation ユーザーは、{{site.data.keyword.cloud_notm}} の VMware NSX プラットフォームについての順を追った説明を使用して、仮想マシンの相互通信とインターネット通信を可能にすることができます。 詳しくは、[VMware Cloud Foundation on {{site.data.keyword.cloud_notm}} (VCF) でのワークロード VM のための NSX のセットアップ](https://developer.ibm.com/recipes/tutorials/setting-up-nsx-for-workload-vms-on-vmware-cloud-foundation-on-ibm-cloud-vcf/){:new_window}を参照してください。

## ユーザー・インターフェースの更新と向上
{: #relnotes_v20-ui}

* クラスターに追加できる ESXi サーバーの最大数が 32 台に更新されました。 クラスターの最大数はまだ 5 個です。
* **「リソース」**ページのインスタンスのサマリー表の**「ESXi サーバー」**列が、**「バージョン」**列に置き換えられました。この列で、インスタンスがデプロイまたは更新されたリリース・バージョンを確認できます。
* SDDC Manager for Cloud Foundation インスタンスのバージョンが、インスタンスの詳細ページに表示されるようになりました。
* ユーザー・インターフェースで適切な設定を選択できるように、エラー・メッセージとツールチップにさまざまな改良が加えられました。

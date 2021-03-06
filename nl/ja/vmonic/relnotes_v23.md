---

copyright:

  years:  2016, 2018

lastupdated: "2018-05-28"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# V2.3 のリリース・ノート
{: #relnotes_v23}

このリリースには、新機能、コンポーネントの更新、使いやすさの向上、バグ修正などが含まれています。 各リリースの修正された問題のリスト、製品に関する既知の問題、および {{site.data.keyword.vmwaresolutions_full}} を使用するためのヒントについては、[{{site.data.keyword.vmwaresolutions_short}} dW の回答](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}を参照してください。

## Spectre および Meltdown への対処
{: #relnotes_v23-spectre}

{{site.data.keyword.vmwaresolutions_short}} は、Spectre および Meltdown と呼ばれる脆弱性 (CVE-2017-5753、CVE-2017-5715、CVE-2017-5754) に対して VMware から提供されたパッチをリリースしました。

* CVEID: [CVE-2017-5753](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)
* CVEID: [CVE-2017-5715](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715)
* CVEID: [CVE-2017-5754](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)

## VMware vCenter Server on IBM Cloud with Hybridity Bundle
{: #relnotes_v23-vcs-hybrid}

このリリースでは、VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle オファリングが導入されました。 vCenter Server with Hybridity Bundle は、オンプレミスのインフラストラクチャーを素早く簡単にクラウドに拡張できるホステッド・プライベート・クラウドです。 この VMware 環境は、IBM 提供の VMware Software Defined Data Center ライセンスに基づくものであり、VMware HCX on {{site.data.keyword.cloud_notm}} サービスが含まれています。このサービスを使用すると、オンプレミスの vSphere 5.0+ 環境を {{site.data.keyword.cloud_notm}} サイトに簡単かつ安全に接続して、シームレスなインフラストラクチャーのハイブリッド化と真のアプリケーション・モビリティーを実現できます。

HCX on {{site.data.keyword.cloud_notm}} サービスは、vCenter Server with Hybridity Bundle インスタンスでのみ利用可能です。 既存の vCenter Server インスタンスを vCenter Server with Hybridity Bundle インスタンスにアップグレードするには、まず基本 vCenter Server V2.3 のソフトウェア更新を適用しなければなりません。 詳しくは、[vCenter Server インスタンスへの更新の適用](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_applyingupdates)を参照してください。

vCenter Server with Hybridity Bundle について詳しくは、以下のトピックを参照してください。

* [vCenter Server with Hybridity Bundle の概要](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_overview)
* [vCenter Server with Hybridity Bundle インスタンスの要件と計画](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_planning)
* [vCenter Server with Hybridity Bundle インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_orderinginstance)

## vCenter Server インスタンスおよび Cloud Foundation インスタンスのクラスター削除のサポート
{: #relnotes_v23-delete-cluster}

インスタンス全体を削除しなくても、インスタンスからクラスターを削除できるようになりました。 V2.2 以前のインスタンスでデプロイしたクラスターの場合に、インスタンスに追加したクラスターを削除するには、インスタンスを V2.3 にアップグレードする必要があります。

詳しくは、[vCenter Server インスタンスのクラスターの追加、表示、削除](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)を参照してください。

## VMware vCenter Server インスタンスの更新
{: #relnotes_v23-vcs}

このリリースでは、以下のアップグレードと機能改善が適用されます。
*	VMware vSphere ESXi 6.5 U1g (パッチ・レベル ESXi650-201803001 を適用済みの ESXi 6.5u1)
*	VMware vCenter Server 6.5 Update 1g

V2.3 リリース以降、**カスタマイズ型** のベア・メタル設定を選択した場合に、以下の新しい CPU モデルをデプロイメントできるようになりました。
* Dual Intel Xeon Silver 4110 プロセッサー / 合計 16 コア、2.1 GHz
* Dual Intel Xeon Gold 5120 Processor / 合計 28 コア、2.2 GHz

詳しくは、以下のトピックを参照してください。

* [vCenter Server インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [vCenter Server インスタンスのクラスターの追加、表示、削除](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)

## VMware Cloud Foundation インスタンスの更新
{: #relnotes_v23-vcf}

このリリースでは、以下のアップグレードと機能改善が適用されます。
*	VMware vSphere ESXi 6.5 U1g (パッチ・レベル ESXi650-201803001 を適用済みの ESXi 6.5u1)
*	VMware vCenter Server 6.5 Update 1g
*	VMware NSX for vSphere 6.3.5

## アドオン・サービスの更新
{: #relnotes_v23-services}

### HyTrust CloudControl on IBM Cloud
{: #relnotes_v23-htcc}

V2.3 以降のリリースでデプロイまたは V2.3 以降のリリースにアップグレードされた VMware Cloud Foundation インスタンスと VMware vCenter Server インスタンスで vSphere 6.5 を実行する場合、HyTrust CloudControl on {{site.data.keyword.cloud_notm}} サービスを使用できるようになりました。 このサービスは、セキュリティー規格に対するコンプライアンスを実行および制御し役割ベースのアクセス制御 (RBAC) を提供します。 このサービスを HyTrust DataControl と組み合わせると、仮想マシンとワークロードのデータを特定の地域、クラスター、または {{site.data.keyword.cloud_notm}} データ・センターの ESXi サーバーから外に出さないようにすることができます。

このサービスを組み込んだ形でインスタンスを注文することも、後から既存のインスタンスにこのサービスを追加することもできます。

詳しくは、以下のトピックを参照してください。
* [HyTrust CloudControl on {{site.data.keyword.cloud_notm}} のコンポーネントと考慮事項](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htcc_considerations)
* [HyTrust CloudControl on {{site.data.keyword.cloud_notm}} の管理](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managinghtcc)

### HyTrust DataControl on IBM Cloud
{: #relnotes_v23-htdc}

V2.3 以降のリリースでデプロイまたは V2.3 以降のリリースにアップグレードされた VMware Cloud Foundation インスタンスと VMware vCenter Server インスタンスで vSphere 6.5 を実行する場合、HyTrust DataControl on {{site.data.keyword.cloud_notm}} サービスを使用できるようになりました。 このサービスでは、鍵管理機能が組み込まれた強い暗号を使用して、ワークロードをライフサイクルにわたって保護できます。 このサービスは、オペレーティング・システム・レベルとデータ・レベルの両方で暗号化を実行できます。つまり、ワークロード内で任意のディレクトリー、フォルダー、またはファイルを暗号化/復号できます。

このサービスを組み込んだ形でインスタンスを注文することも、後から既存のインスタンスにこのサービスを追加することもできます。

詳しくは、以下のトピックを参照してください。
* [HyTrust DataControl on {{site.data.keyword.cloud_notm}} のコンポーネントと考慮事項](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htdc_considerations)
* [HyTrust DataControl on {{site.data.keyword.cloud_notm}} の管理](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managinghtdc)

### IBM Spectrum Protect Plus on IBM Cloud
{: #relnotes_v23-spp}

現行リリースでは、新しくデプロイされるすべてのインスタンスで、IBM Spectrum Protect&trade; Plus V10.1.1 がデフォルトのバックアップ・サービスとしてインストールされます。 IBM Spectrum Protect Plus V10.1.1 の新機能について詳しくは、[IBM Spectrum Protect Plus の更新](https://www.ibm.com/support/knowledgecenter/en/SSNQFQ_10.1.1/spp/r_techchg_spp.html){:new_window}を参照してください。

## 新規資料および更新された資料
{: #relnotes_v23-new-docs}

デプロイメントの後に IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} にストレージを追加する手順を 1 つ 1 つ説明した新しい developerWorks レシピが提供されています。 詳しくは、[デプロイメント後の IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} へのストレージの追加](https://developer.ibm.com/recipes/tutorials/how-to-increase-vsnap-storage-for-ibm-spectrum-protect-plus-on-ibm-cloud-post-deployment/)を参照してください。

## ユーザー・インターフェースの更新と向上
{: #relnotes_v23-ui}

ユーザー・インターフェースが更新され、以下の拡張機能が備えられました。
* **一貫性**: ユーザー・インターフェースは {{site.data.keyword.cloud_notm}} 上の他のサービスと一貫性のある外観を提供するようになりました。
* **アクセスの容易さ**: VMware オファリングに {{site.data.keyword.cloud_notm}} **Catalog** から直接アクセスできるようになりました。
* **合理化されて簡単になった注文の操作環境**: VMware インスタンスの注文とアドオン・サービスのデプロイを単一のインターフェースで行えるようになりました。 また、同じインターフェース上で見積もりコストがすぐに計算されて表示されるので、予算に基づいて構成を調整できます。
* ビジネス・パートナーであるユーザーは、インスタンスの注文時やクラスターの追加時にライセンス持ち込み (BYOL) オプションを使用できません。
* ユーザー・インターフェースで適切な設定を選択できるように、エラー・メッセージとツールチップにさまざまな改良が加えられました。

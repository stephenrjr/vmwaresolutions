---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# IBM Cloud Private Hosted の要求 - 非推奨
{: #managing_icp}

このトピック内の情報は非推奨になっています。 IBM Cloud Private Hosted に関する最新の情報は、[IBM Cloud Private Hosted の概要](icp_overview.html)を参照してください。
{:deprecated}

{{site.data.keyword.cloud}} Private Hosted on vCenter Server on {{site.data.keyword.cloud_notm}} は、自動的に {{site.data.keyword.cloud_notm}} Private Hosted を VMware vCenter Server インスタンスにデプロイします。

{{site.data.keyword.cloud_notm}} Private Hosted は、マイクロサービスとコンテナーの機能を {{site.data.keyword.cloud_notm}} 上の VMware 環境で利用できるようにします。 このサービスを利用することで、使い慣れたオンプレミスの VMware と {{site.data.keyword.cloud_notm}} Private の操作モデルとツールを、{{site.data.keyword.cloud_notm}} に拡張できます。

## IBM Cloud Private Hosted の技術仕様
{: #managing_icp-specs}

{{site.data.keyword.cloud_notm}} Private Hosted サービスを要求するための最小要件を以下に示します。

* VMware vCenter Server on {{site.data.keyword.cloud_notm}}。
  **注:** VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle はサポートされていません。
* VMware NSX Advanced または Enterprise エディション
* 3 つの {{site.data.keyword.baremetal_long}}
* Dual Intel Xeon Gold 5120 プロセッサー / 合計 28 コア、2.2 GHz
* 1 サーバーあたり 384 GB RAM
* 8,000 GB (4 IOPS/GB) の共有 NFS ストレージのファイル共有 1 つ
* IBM Cloud Private 仮想プロセッサー・コア・ライセンス 33 個
* データ・バックアップ用に、Veeam on IBM Cloud サービスを推奨。

## IBM Cloud Private Hosted を要求する手順
{: #managing_icp-procedure}

1. [vCenter Server インスタンスの注文](../vcenter/vc_orderinginstance.html)の手順に従って、新規 vCenter Server インスタンスを注文します。 既存のインスタンス用に IBM Cloud Private Hosted を要求することもできます。
  **重要:** 使用する環境が、上記の最小要件を満たしていることを確認してください。
2. IBM Cloud Private のライセンスを持っていることを確認します。
3. vCenter Server インスタンスを使用する準備ができたことを示す確認メッセージを受け取ったら、IBM Cloud Private Hosted を要求する次の手順に進みます。
4. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「開始」**をクリックします。
5. ページをスクロールダウンし、**「追加サービスの注文 (Order additional services)」**の下で、**「IBM Cloud Private Hosted」**カードをクリックします。
6. **「IBM Cloud Private Hosted on vCenter Server on IBM Cloud」**ページの**「IBM Cloud Private Hosted DevOps チームに連絡 (Contact the IBM Cloud Private Hosted DevOps Team)」**ボックスに、要件に関する説明を入力し、**「コンサルテーションを要求」**をクリックします。

{{site.data.keyword.cloud_notm}} Private Hosted DevOps の担当員が、{{site.data.keyword.cloud_notm}} 連絡先情報を使用してお客様に連絡し、サービスを開始できるようにします。

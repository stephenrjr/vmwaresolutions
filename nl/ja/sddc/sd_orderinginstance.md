---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Cloud Foundation インスタンスの注文
{: #sd_orderinginstance}

標準的なコンピュート、ストレージ、ネットワーク構成を備えた統合的ソフトウェア定義データ・センター (SDDC) プラットフォームをデプロイするには、VMware Cloud Foundation インスタンスを注文します。 初回注文時に、災害復旧のための [Zerto on {{site.data.keyword.cloud}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr) などのサービスも追加できます。

## 要件
{: #sd_orderinginstance-req}

以下の作業を完了していることを確認してください。
*  **「設定」**ページで {{site.data.keyword.cloud_notm}} インフラストラクチャーの資格情報を構成する。 詳しくは、[ユーザー・アカウントと設定の管理](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)を参照してください。
*  [Cloud Foundation インスタンスの要件と計画](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning)に記載されている要件と考慮事項を確認した。

インスタンスの注文時およびデプロイ時に設定した値は変更しないでください。 変更すると、インスタンスを使用できなくなる可能性があります。 例えば、パブリック・ネットワークがシャットダウンしたり、プロビジョニング中にサーバーや仮想サーバー・インスタンス (VSI) が Vyatta の内側に移動したり、IBM CloudBuilder VSI が停止したり、削除されたりすることがあります。 また、インスタンスがデプロイされた後は、インスタンス名、ルート・ドメイン・ネーム、サブドメイン・ラベル、ホスト名接頭部を変更しないでください。
{:important}

## システム設定
{: #sd_orderinginstance-sys-settings}

Cloud Foundation インスタンスを注文する際には、以下のシステム設定を指定する必要があります。

### Instance name
{: #sd_orderinginstance-inst-name}

インスタンス名は、次の要件を満たす必要があります。
* 英数字とダッシュ (-) の文字だけを使用できます。
* インスタンス名の先頭は英字、末尾は英数字でなければなりません。
* インスタンス名の最大の長さは 10 文字です。
* インスタンス名はアカウント内で固有である必要があります。

### プライマリーまたはセカンダリー
{: #sd_orderinginstance-primary-secondary}

新規プライマリー・インスタンスを注文するのか、既存のプライマリー・インスタンスのセカンダリー・インスタンスを注文するのかを選択します。

## ライセンス交付の設定
{: #sd_orderinginstance-licensing-settings}

インスタンス内の次の VMware コンポーネントのライセンス・オプションを指定します。  
* vCenter Server ライセンス - Standard
* vSphere ライセンス - Enterprise Plus
* NSX ライセンス - Enterprise
* vSAN ライセンス: Advanced エディションまたは Enterprise エディションを選択

ビジネス・パートナーであるユーザーの場合、vCenter Server ライセンス (Standard エディション)、vSphere ライセンス (Enterprise Plus エディション)、NSX ライセンス、および vSAN ライセンスが自動的に含められて購入されます。 ただし、vSAN ライセンスのエディションは指定する必要があります。

ビジネス・パートナーでないユーザーの場合、**「購入に含める」**を選択してこれらのコンポーネントに IBM 提供 VMware ライセンスを使用することも、**「自分で提供する」**を選択し、所有するライセンス・キーを入力してライセンス持ち込み (BYOL) を適用することもできます。

## ベア・メタル・サーバーの設定
{: #sd_orderinginstance-bare-metal}

### データ・センターの場所
{: #sd_orderinginstance-dc-location}

インスタンスをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。

### Skylake
{: #sd_orderinginstance-skylake}

**「Skylake」**を選択した場合、必要に応じてベアメタル・サーバーの CPU と RAM の組み合わせを選択できます。

表 1. Skylake {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション  | RAM オプション       |
|:------------- |:------------- |
| Dual Intel Xeon Silver 4110 プロセッサー / 合計 16 コア、2.1 GHz | 128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 5120 Processor / 合計 28 コア、2.2 GHz | 128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 6140 Processor / 合計 36 コア、2.3 GHz | 128 GB、192 GB、384 GB、768 GB、1.5 TB |

### Broadwell
{: #sd_orderinginstance-broadwell}

**「Broadwell」**を選択した場合、必要に応じてベアメタル・サーバーの CPU と RAM の組み合わせを選択できます。

表 2. Broadwell {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| デュアル Intel Xeon E5-2620 v4 / 合計 16 コア、2.1 GHz | 128 GB、256 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2650 v4 / 合計 24 コア、2.2 GHz | 128 GB、256 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2690 v4 / 合計 28 コア、2.6 GHz | 128 GB、256 GB、512 GB、768 GB、1.5 TB |
| クワッド Intel Xeon E7-4820 v4 / 合計 40 コア、2.0 GHz | 128 GB、256 GB、512 GB、1 TB、2 TB、3 TB |
| クワッド Intel Xeon E7-4850 v4 / 合計 64 コア、2.1 GHz | 128 GB、256 GB、512 GB、1 TB、2 TB、3 TB |

### ベア・メタル・サーバーの数
{: #sd_orderinginstance-bare-metal-number}

最初のデプロイメント時は、Cloud Foundation インスタンスはベア・メタル・サーバー 4 台で構成されます。 このベア・メタル・サーバーの数は、注文時には変更できません。

## ストレージ設定
{: #sd_orderinginstance-storage}

Cloud Foundation インスタンスの場合は、VMware vSAN ストレージのみを注文できます。

**「Skylake」**または**「Broadwell」**ベアメタル・サーバー構成を選択した場合は、インスタンスの vSAN ストレージをカスタマイズできます。 以下の vSAN 設定を指定します。
* **vSAN 容量ディスクのディスク・タイプとサイズ**: 必要な容量ディスクのオプションを選択します。
* **vSAN 容量ディスクの数**: 追加する容量ディスク数を指定します。
* 容量ディスクを上限の 8 個を超えて追加する場合は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けます。 このオプションでは、合計 10 個の容量ディスクに 2 つの追加の容量ディスク・ベイが提供されますので、より少ない待ち時間とより高い IOPS スループットが求められるワークロードを扱うときに役立ちます。

  **High-Performance Intel Optane** オプションは、Skylake の CPU モデルの Dual Intel Xeon Gold 5120 および Dual Intel Xeon Gold 6140 でのみ使用できます。
  {:note}

* **「Disk Type for vSAN Cache Disks」**および**「Number of vSAN Cache Disks」**の値を確認します。 これらの値は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けたかどうかによって異なります。

## ネットワーク・インターフェースの設定
{: #sd_orderinginstance-network-interface}

Cloud Foundation インスタンスを注文する際には、以下のネットワーク・インターフェース設定を指定する必要があります。

### ホスト名接頭部
{: #sd_orderinginstance-hostname-prefix}

ホスト名接頭部は、次の要件を満たす必要があります。
*  英数字とダッシュ (-) の文字だけを使用できます。
*  ホスト名接頭部の先頭と末尾は英数字である必要があります。
*  ホスト名接頭部の最大長は 10 文字です。

### サブドメイン・ラベル
{: #sd_orderinginstance-subdomain-label}

サブドメイン・ラベルは、次の要件を満たす必要があります。
*  英数字とダッシュ (-) の文字だけを使用できます。
*  サブドメイン・ラベルの先頭は英字、末尾は英数字でなければなりません。
*  サブドメイン・ラベルの最大長は 10 文字です。
*  サブドメイン・ラベルは、アカウント内で固有でなければなりません。

### ドメイン・ネーム
{: #sd_orderinginstance-domain-name}

ルート・ドメイン・ネームは、次の要件を満たす必要があります。
* ドメイン・ネームは、ピリオド (.) で区切られた 2 つ以上のストリングで構成されていなければなりません。
* 最初の文字列は、英字で始まり英数字で終わらなければなりません。
* 最後の文字列を除き、文字列で使用できるのは、英数字とダッシュ (-) のみです。
* 最後の文字列には、英字しか使用できません。
* 最後の文字列の長さは、2 文字から 24 文字までの範囲でなければなりません。

ホストと VM (仮想マシン) の FQDN (完全修飾ドメイン・ネーム) の最大長は 50 文字です。 この最大長に対応するドメイン・ネームにする必要があります。
{:note}

### ネットワーク設定の値の形式
{: #sd_orderinginstance-network-settings-value-format}

次の表に示すように、ドメイン・ネームとサブドメイン・ラベルは、インスタンスのユーザー名とサーバー名を生成するために使用されます。

表 3. ユーザー名、ドメイン・ネーム、およびサーバー名の値の形式

| 名前        | 値の形式      |
  |:------------- |:------------- |
  | ドメイン・ネーム | `<root_domain>` |  
  | 完全修飾 ESXi サーバー名 | `<host_prefix><n>.<subdomain_label>.<root_domain>`。ここで `<n>` は ESXi サーバーのシーケンスです。 最大長は 50 文字です。 |   
  | vCenter Server ログイン・ユーザー名 | `<user_id>@<root_domain>` (Microsoft Active Directory ユーザー) または `administrator@vsphere.local` |
  | vCenter Server FQDN | `vcenter-1.<subdomain_label>.<root_domain>`。 最大長は 50 文字です。 |  
  | SDDC Manager FQDN | `sddcmanager.<subdomain_label>.<root_domain>`。 最大長は 50 文字です。 |
  | シングル・サインオン (SSO) サイト名 | `<subdomain_label>`
  | PSC FQDN | `PSC-<subdomain_label>.<subdomain_label>.<root_domain>`。 最大長は 50 文字です。 |  

  SDDC Manager FQDN をパブリックに解決可能な名前にすることはできません。 パブリックに解決可能な名前にすると、Cloud Foundation インスタンス構成が失敗する恐れがあり、その場合は復旧不能になります。 ドメイン・ネームを指定する前に、[ルート・ドメイン・ネームを選択する際の考慮事項](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_limitations#considerations-when-choosing-a-root-domain-name-for-cloud-foundation-instances)を確認してください。

### VLAN
{: #sd_orderinginstance-vlans}

ネットワーク設定は、**「新規 VLAN を注文」**と**「既存の VLAN を選択」**のどちらを選択するかによって異なります。

インスタンスの注文には、パブリック VLAN 1 つとプライベート VLAN 2 つが必要です。 2 つのプライベート VLAN は各ベア・メタル・サーバーにトランキングされます。

#### 新規 VLAN を注文
{: #sd_orderinginstance-new-vlans}

新規パブリック VLAN 1 つと新規プライベート VLAN 2 つを注文することを選択します。

#### 既存の VLAN を選択
{: #sd_orderinginstance-existing-vlans}

選択した {{site.data.keyword.CloudDataCent_notm}}によっては、既存のパブリック VLAN とプライベート VLAN を使用できることがあります。

既存のパブリック VLAN とプライベート VLAN を再使用することを選択した場合は、それらの VLAN とサブネットを指定します。
  * **パブリック VLAN** は、パブリック・ネットワーク・アクセスに使用されます。
  * **プライベート VLAN** は、{{site.data.keyword.cloud_notm}} 内部のデータ・センターとサービスの間の接続に使用されます。
  * **セカンダリー・プライベート VLAN** は、vSAN などの VMware 機能に使用されます。
  * **プライマリー・サブネット**は、パブリック・ネットワーク・アクセス用に物理ホストに割り当てられます。
  * **プライベート・プライマリー・サブネット**は、管理トラフィック用に物理ホストに割り当てられます。

選択した VLAN のファイアウォール構成が管理用データ・トラフィックをブロックしていないことを確認してください。選択したすべての VLAN が同じポッドに含まれていることを確認してください。複数のポッドの VLAN に ESXi サーバーをプロビジョンすることはできません。
{:important}

## サービス
{: #sd_orderinginstance-addon-services}

Cloud Foundation インスタンスを注文するときに、アドオン・サービスを注文することもできます。 使用可能なサービスについて詳しくは、[Cloud Foundation インスタンス用サービス](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning#services-for-cloud-foundation-instances)を参照してください。

## 注文のサマリー
{: #sd_orderinginstance-order-summary}

選択したインスタンスとアドオン・サービスの構成に基づき、ただちに見積もりコストが生成されて右側のペインに表示されます。 右側のペインの**「料金詳細」**をクリックすると、見積もりの詳細を示す PDF 文書を生成できます。

## Cloud Foundation インスタンスを注文する手順
{: #sd_orderinginstance-procedure}

1. {{site.data.keyword.cloud_notm}} のカタログで、左側のナビゲーション・ペインの**「VMware」**をクリックしてから、**「仮想データ・センター」**セクションの**「Cloud Foundation」**をクリックします。
2. **「VMware Cloud Foundation on IBM Cloud」**ページで、**「作成」**をクリックします。
3. **「Cloud Foundation」**ページで、インスタンス名を入力します。
4. インスタンス・タイプを選択します。
   * 環境の単一インスタンスをデプロイするか、マルチサイト・トポロジーの最初のインスタンスをデプロイする場合は、**「プライマリー・インスタンス」**をクリックします。
   * 高可用性が必要になる場合は、**「セカンダリー・インスタンス」**をクリックし、環境内の既存の (プライマリー) インスタンスにそのインスタンスを接続します。 以下のステップを実行します。
     1. セカンダリー・インスタンスを接続するプライマリー・インスタンスを選択します。
     2. プライマリー・インスタンスが V2.5 以降である場合は、**「プライマリー・インスタンス PSC の管理者パスワード (Administrator Password for the Primary Instance PSC)」**の値を入力します。
     3. プライマリー・インスタンスが V2.4 以前である場合は、**「プライマリー・インスタンス PSC の管理者パスワード (Administrator Password for the Primary Instance PSC)」**フィールドの事前入力値が正しいことを確認します。
5. インスタンスのコンポーネントのライセンス設定を行います。
   *  IBM 提供のライセンスを使用するには、**「購入に含める」**を選択します。
   *  所有しているライセンスを使用するには、**「自分で提供する」**を選択し、ライセンス・キーを入力します。  
6. ベア・メタル・サーバーの設定を次の手順で実行します。
   1. インスタンスをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。
   2. ベア・メタル・サーバー構成を選択し、CPU モデルと RAM サイズを指定します。
7. ストレージ構成を次の手順で実行します。
   1. vSAN 容量ディスクおよびキャッシュ・ディスクのディスク・タイプとディスク数を指定します。
   2. さらにストレージが必要な場合は、**「High-Performance with Intel Optane」**チェック・ボックスを選択します。
8. ネットワーク・インターフェースの設定を行います。
   1. ホスト名接頭部、サブドメイン・ラベル、ルート・ドメイン・ネームを入力します。 セカンダリー・インスタンスの場合、ドメイン・ネームは自動的に入力されます。
   2. VLAN 設定を選択します。
      * 新規のパブリック VLAN とプライベート VLAN を注文する場合は、**「新規 VLAN を注文」**をクリックします。
      * 既存のパブリック VLAN とプライベート VLAN を使用できる場合に再利用するには、**「既存の VLAN を選択」**をクリックし、それらの VLAN とサブネットを指定します。

9. インスタンスにデプロイするアドオン・サービスを、対応するサービス・カードをクリックして選択します。 サービスに構成が必要な場合は、サービス固有の設定を入力し、ポップアップ構成ウィンドウの**「サービスの追加」**をクリックします。 サービスの設定方法について詳しくは、対応するサービス注文トピックを参照してください。

10. **「発注要約」**ペインで、インスタンス構成を確認してから注文を実行します。
    1. インスタンスの設定を確認します。
    2. インスタンスの見積もりコストを確認します。 PDF のサマリーを生成するには、**「料金詳細」**をクリックします。 注文のサマリーを保存または印刷するには、PDF ウィンドウの右上にある**「印刷」**アイコンまたは **「ダウンロード」**アイコンをクリックします。
    3. 課金されるアカウントが正しいことを確認した後、**「下にリストされているアカウントが課金されることを確認しました」**チェック・ボックスを選択します。
    4. 注文に適用される使用条件のリンクをクリックします。 それらの使用条件に同意してから、**「以下に表示されるサード・パーティー・サービス契約を読み、同意します」**チェック・ボックスを選択します。
    5. **「プロビジョン」**をクリックします。

## 結果
{: #sd_orderinginstance-results}

インスタンスのデプロイメントが自動的に開始されます。 注文が処理されていることを示す確認メッセージが表示されます。デプロイメントの状況を確認するには、インスタンスの詳細を表示します。

インスタンスが正常にデプロイされると、[Cloud Foundation インスタンスの技術仕様](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview#technical-specifications-for-cloud-foundation-instances)に記述されているコンポーネントが VMware 仮想プラットフォームにインストールされます。 注文した ESXi サーバーは、デフォルトでは **SDDC-Cluster** としてグループ化されます。 アドオン・サービスを注文した場合は、注文の完了後にサービスのデプロイメントが開始されます。

インスタンスが使用可能になると、インスタンスの状況が**「使用可能」**に変わり、E メールで通知されます。

セカンダリー・インスタンスを注文した場合は、セカンダリー・インスタンスの注文が完了した後に、(セカンダリー・インスタンスにリンクされた) プライマリー・インスタンスの VMware vSphere Web Client が再始動されることがあります。

## 次に行うこと
{: #sd_orderinginstance-next}

注文した Cloud Foundation インスタンスを表示して管理します。

{{site.data.keyword.cloud_notm}} アカウントで作成した {{site.data.keyword.vmwaresolutions_short}} コンポーネントは、{{site.data.keyword.vmwaresolutions_short}} コンソールから管理する必要があります。{{site.data.keyword.slportal}}やその他の手段でコンソール以外から管理することはできません。 {{site.data.keyword.vmwaresolutions_short}} コンソール以外で変更した場合、変更がコンソールと同期されません。
{:important}

**注意:** インスタンスを注文したときに {{site.data.keyword.cloud_notm}} アカウントにインストールされた {{site.data.keyword.vmwaresolutions_short}} コンポーネントを、{{site.data.keyword.vmwaresolutions_short}} コンソール以外で管理すると、環境が不安定になる可能性があります。 これには以下の管理アクティビティーが該当します。

*  コンポーネントの追加、変更、返却、または削除
*  ESXi サーバーの追加または削除によるインスタンス容量の拡張または縮小
*  コンポーネントのパワーオフ
*  サービスの再始動

   {{site.data.keyword.slportal}}での共有ストレージのファイル共有の管理は、上記アクティビティーに該当しません。 これには、共有ストレージのファイル共有の注文、削除 (マウントされている場合はデータ・ストアに影響する可能性があります)、承認、マウントなどのアクティビティーが含まれます。

## 関連リンク
{: #sd_orderinginstance-related}

* [{{site.data.keyword.cloud_notm}} アカウントの登録](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [Cloud Foundation インスタンスの表示](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_viewinginstances)
* [Cloud Foundation インスタンスのクラスターの追加、表示、削除](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-adding-and-viewing-clusters-for-cloud-foundation-instances)
* [Cloud Foundation インスタンスの容量の拡張と縮小](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservers)
* [Cloud Foundation インスタンス用サービスの注文、表示、削除](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservices)
* [Cloud Foundation インスタンスの削除](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_deletinginstance)
* [BYOL に関するよくある質問](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq_byol)

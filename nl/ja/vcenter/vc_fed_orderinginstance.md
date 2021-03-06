---

copyright:

  years:  2016, 2019

lastupdated: "2019-01-25"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# VMware Federal インスタンスの注文

ワークロードのニーズに合わせて最適化できる、柔軟でカスタマイズ可能な VMware 仮想化プラットフォームをデプロイするには、VMware Federal インスタンスを注文します。 VMware Federal インスタンスを使用すると、開かれた管理接続から切り離してデプロイ済みインスタンスを保護することができます。

現時点では、VMware Federal on {{site.data.keyword.cloud}} をサポートしているのは vCenter Server インスタンスのみです。
{:note}

## VMware Federal インスタンスを注文するための要件

以下の作業を完了していることを確認してください。
* **「設定」**ページで {{site.data.keyword.cloud_notm}} インフラストラクチャーの資格情報を構成する。 詳しくは、[ユーザー・アカウントと設定の管理](/docs/services/vmwaresolutions/vmonic/useraccount.html)を参照してください。
* [VMware Federal インスタンスの要件と計画](/docs/services/vmwaresolutions/vcenter/vc_fed_planning.html)の情報を確認する。
* インスタンス名とドメイン・ネームの形式を確認する。 ドメイン・ネームとサブドメイン・ラベルは、インスタンスのユーザー名とサーバー名の生成に使用されます。

表 1. インスタンス名とドメイン・ネームの値の形式

| 名前        | 値の形式      |
  |:------------- |:------------- |
  | ドメイン・ネーム | `<root_domain>` |  
  | vCenter Server ログイン・ユーザー名 | `<user_id>@<root_domain>` (Microsoft Active Directory ユーザー) または `administrator@vsphere.local` |
  | vCenter Server FQDN | `vcenter.<subdomain_label>.<root_domain>`. 最大長は 50 文字です。 |
  | シングル・サインオン (SSO) サイト名 | `<subdomain_label>` |
  | 完全修飾 ESXi サーバー名 | `<host_prefix><n>.<subdomain_label>.<root_domain>`。ここで `<n>` は ESXi サーバーのシーケンスです。 最大長は 50 文字です。 |  
  | PSC FQDN | `psc-<subdomain_label>.<subdomain_label>.<root_domain>`. 最大長は 50 文字です。 |

インスタンスの注文時およびデプロイ時に設定した値は変更しないでください。 変更すると、インスタンスを使用できなくなる可能性があります。 例えば、パブリック・ネットワークがシャットダウンしたり、プロビジョニング中にサーバーや仮想サーバー・インスタンス (VSI) が Vyatta の内側に移動したり、IBM CloudBuilder VSI が停止したり、削除されたりすることがあります。
{:important}

## システム設定

VMware Federal インスタンスを注文する際には、以下のシステム設定を指定する必要があります。

### インスタンス名

インスタンス名は、次の要件を満たす必要があります。
* 英数字とダッシュ (-) の文字だけを使用できます。
* インスタンス名の先頭は英字、末尾は英数字でなければなりません。
* インスタンス名の最大の長さは 10 文字です。
* インスタンス名はアカウント内で固有である必要があります。

### プライマリーまたはセカンダリー

新しいプライマリー・インスタンスを注文します。 現時点では、高可用性のためにセカンダリー・インスタンスをデプロイすることはできません。

## ライセンス交付の設定

IBM では、以下の VMware コンポーネントのライセンスを提供しています。

* vCenter Server 6.5
* vSphere Enterprise Plus 6.5u1
* NSX Service Providers 6.4 (Base、Advanced、または Enterprise エディション)
* (vSAN クラスターの場合) vSAN 6.6 (Advanced または Enterprise エディション)

### 注意

* 最小のライセンス・エディションが、ユーザー・インターフェースに表示されます。 複数のコンポーネント・エディションがサポートされている場合は、必要なエディションを選択できます。 選択した VMware コンポーネントごとに、指定したライセンス・キーが正しいことを確認してください。
* vSphere の場合は、注文時にライセンス料が発生しますが、そのライセンス料は後でアカウントにクレジットされます。

## ベア・メタル・サーバーの設定

ベアメタルの設定は、選択したデータ・センターやベアメタル・サーバーの構成に基づきます。

### データ・センターの場所

インスタンスをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。

### Skylake

ベア・メタル・サーバーの CPU モデルと RAM を指定します。

表 2. Skylake {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| Dual Intel Xeon Silver 4110 プロセッサー / 合計 16 コア、2.1 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 5120 Processor / 合計 28 コア、2.2 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 6140 Processor / 合計 36 コア、2.3 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |

### Broadwell

ベア・メタル・サーバーの CPU モデルと RAM を指定します。

表 3. Broadwell {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| デュアル Intel Xeon E5-2620 v4 / 合計 16 コア、2.1 GHz | 64 GB、128 GB、256 GB、512 GB |
| デュアル Intel Xeon E5-2650 v4 / 合計 24 コア、2.2 GHz | 64 GB、128 GB、256 GB、512 GB |
| デュアル Intel Xeon E5-2690 v4 / 合計 28 コア、2.6 GHz | 64 GB、128 GB、256 GB、512 GB |

### ベア・メタル・サーバーの数

ESXi サーバーの数は、2 台から 20 台の範囲内で構成できます。

すべての ESXi サーバーが同じ構成を共有します。 デプロイメント後には、さらに 4 つのクラスターを追加できます。 vSAN ストレージ設定の場合、初期クラスターとデプロイメント後のクラスターの両方に 4 つの ESXi サーバーが必要です。 最小限の ESXi サーバーについて詳しくは、[2 ノードの vCenter Server インスタンスの可用性は高いですか?](/docs/services/vmwaresolutions/vmonic/faq.html#is-a-two-node-vcenter-server-instance-highly-available-) を参照してください。

## ストレージ設定

ストレージ設定は、選択したベア・メタル・サーバー構成とストレージ・タイプによって異なります。

### vSAN ストレージ

以下の vSAN オプションを指定します。
* **vSAN 容量ディスクのディスク・タイプとサイズ**: 必要な容量ディスクのオプションを選択します。
* **vSAN 容量ディスクの数**: 追加する容量ディスク数を指定します。
* 容量ディスクを上限の 8 個を超えて追加する場合は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けます。 このオプションでは、合計 10 個の容量ディスクに 2 つの追加の容量ディスク・ベイが提供されますので、より少ない待ち時間とより高い IOPS スループットが求められるワークロードを扱うときに役立ちます。

  **High-Performance Intel Optane** オプションは、Skylake の CPU モデルの Dual Intel Xeon Gold 5120 および Dual Intel Xeon Gold 6140 でのみ使用できます。
  {:note}

* **「Disk Type for vSAN Cache Disks」**および**「Number of vSAN Cache Disks」**の値を確認します。 これらの値は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けたかどうかによって異なります。
* **vSAN ライセンス**: vSAN 6.6 ライセンス・エディション (Advanced または Enterprise) を選択します。

### NFS ストレージ

**「NFS Storage」**を選択する場合は、インスタンスにファイル・レベルの共有ストレージを追加し、すべての共有で同じ設定を使用することも、ファイル共有ごとに別々の構成設定を指定することもできます。 以下の NFS オプションを指定します。

ファイル共有の数は 1 から 32 までの範囲で指定する必要があります。
{:note}

* **Configure shares individually**: ファイル共有ごとに異なる構成設定を指定する場合に選択します。
* **Number of Shares**: どのファイル共有でも同じ構成設定を使用する場合に、追加する NFS 共有ストレージのファイル共有の数を指定します。
* **サイズ**: 共有ストレージのニーズを満たす容量を選択します。
* **パフォーマンス**: ワークロードの要件に基づいて、1 GB あたりの IOPS (入出力操作数/秒) を選択します。
* **ADD NFS**: 別々の構成設定を使用する個々のファイル共有を追加する時に選択します。

表 3. NFS パフォーマンス・レベルのオプション

| オプション        | 詳細       |
  |:------------- |:------------- |
  | 2 IOPS/GB | このオプションは、最も汎用的なワークロード用に設計されています。 例えば、小規模なデータベースのホスト、Web アプリケーションのバックアップ、ハイパーバイザーの仮想マシン・ディスク・イメージなどの用途があります。 |
  | 4 IOPS/GB | このオプションは、同時に高い割合のデータがアクティブになる高負荷のワークロード用に設計されています。 例えば、トランザクション・データベースなどの用途があります。 |
  | 10 IOPS/GB | このオプションは、分析などの最も要求の厳しいワークロード・タイプ用に設計されています。 例えば、トランザクションの多いデータベースやその他のパフォーマンス重視のデータベースなどの用途があります。 このパフォーマンス・レベルは、ファイル共有あたり最大 4 TB の容量に制限されています。 |

## ネットワーク・インターフェースの設定

### ホスト名接頭部

ホスト名接頭部は、次の要件を満たす必要があります。
*  英数字とダッシュ (-) の文字だけを使用できます。
*  ホスト名接頭部の先頭と末尾は英数字である必要があります。
*  ホスト名接頭部の最大長は 10 文字です。

### サブドメイン・ラベル

サブドメイン・ラベルは、次の要件を満たす必要があります。
*  英数字とダッシュ (-) の文字だけを使用できます。
*  サブドメイン・ラベルの先頭は英字、末尾は英数字でなければなりません。
*  サブドメイン・ラベルの最大長は 10 文字です。
*  サブドメイン・ラベルは、アカウント内で固有でなければなりません。

### ドメイン・ネーム

ルート・ドメイン・ネームは、次の要件を満たす必要があります。
* ドメイン・ネームは、ピリオド (.) で区切られた 2 つ以上のストリングで構成されていなければなりません。
* 最初の文字列は、英字で始まり英数字で終わらなければなりません。
* 最後の文字列を除き、文字列で使用できるのは、英数字とダッシュ (-) のみです。
* 最後の文字列には、英字しか使用できません。
* 最後の文字列の長さは、2 文字から 24 文字までの範囲でなければなりません。

ホストと VM の完全修飾ドメイン・ネーム (FQDN) の最大長は 50 文字です。 この最大長に対応するドメイン・ネームにする必要があります。
{:note}

### DNS 構成

インスタンスのドメイン・ネーム・システム (DNS) 構成を選択します。

* **Active Directory/DNS 用の単一のパブリック Windows VSI**: Microsoft Active Directory (AD) 用の単一の Microsoft Windows Server VSI。ホストと仮想マシンが登録されたインスタンスの DNS として機能します。これがデプロイされて参照可能になります。
* **管理クラスター上の高可用性構成の 2 つの専用 Windows Server VM**: V2.3 以降のリリースでは、2 つの Microsoft Windows 仮想マシンがデプロイされるので、セキュリティーと堅牢性が向上します。

2 つの Microsoft Windows 仮想マシンを使用するようにインスタンスを構成する場合は、2 つの Microsoft Windows Server 2012 R2 ライセンスを提供する必要があります。 Microsoft Windows Server 2012 R2 Standard エディションのライセンスと Microsoft Windows Server 2012 R2 Datacenter エディションのライセンスのいずれかまたは両方を使用してください。
{:important}

現時点では、各ライセンスは単一の物理サーバーにのみ割り当てることが可能で、最大 2 つの物理プロセッサーをカバーします。 1 つの Standard エディション・ライセンスを使用すると、2 プロセッサーのサーバーで 2 台の仮想化 Microsoft Windows 仮想マシンを実行できます。 したがって、ライセンスは 2 つ必要になります。2 つの異なるホストに 2 つの Microsoft Windows 仮想マシンがデプロイされるからです。

仮想マシンは 30 日以内に有効にしてください。

Windows ライセンスの注文方法について詳しくは、[Windows Server 2012 R2 の資料](https://www.microsoft.com/en-us/licensing/product-licensing/windows-server-2012-r2.aspx#tab=2)を参照してください。

## 注文のサマリー

選択したインスタンス構成に基づいて、見積もりコストがすぐに生成され、右側のペインの**「注文の要約」**セクションに表示されます。 右側のペインの下部の**「料金詳細」**をクリックすると、見積もりの詳細を示す PDF 文書を生成できます。

## VMware Federal インスタンスを注文する手順

1. {{site.data.keyword.cloud_notm}} のカタログで、左側のナビゲーション・ペインの**「VMware」**をクリックしてから、**「仮想データ・センター」**セクションの**「vCenter サーバー」**をクリックします。
2. **「VMware vCenter Server on IBM Cloud」**ページで、**「vCenter サーバー」**カードをクリックし、**「作成」**をクリックします。
3. **「vCenter サーバー」**ページで、インスタンス名を入力します。
4. **「プライマリー・インスタンス」**をクリックして、環境内に単一インスタンスをデプロイします。
5. VMware NSX ライセンス・エディションを指定します。
6. ベア・メタル・サーバーの構成を次の手順で実行します。
   1. インスタンスをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。
   2. **「Skylake」**または**「Broadwell」**の CPU モデルと **RAM** の容量を選択します。
7. ストレージ構成を次の手順で実行します。
   * **「vSAN Storage」**を選択した場合は、容量ディスクおよびキャッシュ・ディスクのディスク・タイプ、ディスク数、vSAN ライセンス・エディションを指定します。 さらにストレージが必要な場合は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けます。
   * **「NFS Storage」**を選択し、すべてのファイル共有に同じ設定を追加して構成する場合は、**「Number of Shares」**、**「Size」**、**「Performance」**を指定します。
   * **「NFS Storage」**を選択し、ファイル共有を個別に追加して構成する場合は、**「Configure shares individually」**を選択し、ファイル共有ごとに、**「Add NFS」**ラベルの横にある**「+」**アイコンをクリックして、**「Size」**と**「Performance」**を選択します。 少なくとも 1 つのファイル共有を選択する必要があります。
8. ネットワーク・インターフェース構成を行います。
   1. ホスト名接頭部、サブドメイン・ラベル、ルート・ドメイン・ネームを入力します。
   2. DNS 構成を選択します。
9. **「発注要約」**ペインで、インスタンス構成を確認してから注文を実行します。
   1. インスタンスの設定を確認します。
   2. 注文に適用される使用条件のリンクをクリックして、インスタンスを注文する前にそれらの条件に同意することを確認する必要があります。
   3. **「コストの計算」**のコスト・リンクをクリックして、インスタンスの見積もりコストを確認します。 注文のサマリーを保存または印刷するには、PDF ウィンドウの右上にある**「印刷」**アイコンまたは **「ダウンロード」**アイコンをクリックします。
   4. **「プロビジョン」**をクリックします。

## 結果

インスタンスのデプロイメントが自動的に開始されます。 注文が処理されていることを示す確認メッセージが表示されます。デプロイメントの状況を確認するには、インスタンスの詳細を表示します。

インスタンスが正常にデプロイされると、[{{site.data.keyword.cloud_notm}} インスタンスの技術仕様](/docs/services/vmwaresolutions/vcenter/vc_fed_overview.html#technical-specifications-for-vmware-federal-on-ibm-cloud-instances)に記述されているコンポーネントが VMware 仮想プラットフォームにインストールされます。注文した ESXi サーバーは、デフォルトでは **cluster1** としてグループ化されます。

インスタンスが使用可能になると、インスタンスの状況が**「使用可能」**に変わり、E メールで通知されます。

## 次に行うこと

注文した VMware Federal インスタンスを表示し、管理して、保護します。

{{site.data.keyword.cloud_notm}} アカウントで作成した {{site.data.keyword.vmwaresolutions_short}} コンポーネントは、{{site.data.keyword.vmwaresolutions_short}} コンソールから管理する必要があります。{{site.data.keyword.slportal}}やその他の手段でコンソール以外から管理することはできません。
{{site.data.keyword.vmwaresolutions_short}} コンソール以外で変更した場合、変更がコンソールと同期されません。
{:important}

**注意:** インスタンスを注文したときに {{site.data.keyword.cloud_notm}} アカウントにインストールされた {{site.data.keyword.vmwaresolutions_short}} コンポーネントを、{{site.data.keyword.vmwaresolutions_short}} コンソール以外で管理すると、環境が不安定になる可能性があります。 これには以下の管理アクティビティーが該当します。
*  コンポーネントの追加、変更、返却、または削除
*  ESXi サーバーの追加または削除によるインスタンス容量の拡張または縮小
*  コンポーネントのパワーオフ

   {{site.data.keyword.slportal}}での共有ストレージのファイル共有の管理は、上記アクティビティーに該当しません。 これには、共有ストレージのファイル共有の注文、削除 (マウントされている場合はデータ・ストアに影響する可能性があります)、承認、マウントなどのアクティビティーが含まれます。

### 関連リンク

* [{{site.data.keyword.cloud_notm}} アカウントの登録](/docs/services/vmwaresolutions/vmonic/signing_softlayer_account.html)
* [VMware Federal インスタンスの表示](/docs/services/vmwaresolutions/vcenter/vc_fed_viewinginstance.html)
* [VMware Federal インスタンスの容量の拡張と縮小](/docs/services/vmwaresolutions/vcenter/vc_fed_addingremovingservers.html)
* [VMware Federal インスタンスのクラスターの追加、表示、削除](/docs/services/vmwaresolutions/vcenter/fed_addviewdeleteclusters.html)
* [VMware Federal インスタンスの保護](/docs/services/vmwaresolutions/vcenter/vc_fed_securinginstance.html)
* [VMware Federal インスタンスの削除](/docs/services/vmwaresolutions/vcenter/vc_fed_deletinginstance.html)
* [IBM サポートへのお問い合わせ](/docs/services/vmwaresolutions/vmonic/trbl_support.html)

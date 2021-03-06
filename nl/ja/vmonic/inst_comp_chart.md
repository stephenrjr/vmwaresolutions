---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

subcollection: vmware-solutions


---

# オファリングの比較表
{: #inst_comp_chart}

次の表で、VMware vCenter Server インスタンス、VMware vCenter Server with Hybridity Bundle インスタンス、VMware vSphere クラスターの機能サポートの違いを確認してください。

表 1.vCenter Server、vCenter Server with Hybridity Bundle、vSphere クラスターでサポートされる機能

| 機能 | vCenter Server | vCenter Server with Hybridity | VMware vSphere |
|:--- |:--- |:--- |:--- |
| {{site.data.keyword.IBM}} の高度な自動化機能による起動 <sup>1</sup> | はい | はい | いいえ。自己構築および自己構成 |
| ストレージ・オプション | vSAN または NFS (ファイル・レベルの共有ストレージ) | vSAN または NFS <sup>2</sup> | vSAN または NFS |
| 初期クラスター内の ESXi サーバーの数 | vSAN の場合は 4、NFS の場合は 2 以上 (3 を推奨) | 4 | 既存のクラスターを拡張する場合は 1、新しい vSAN クラスターの場合は 4、NFS を使用する新しいクラスターの場合は 3 以上 |
| ESXi サーバーの最大数 <sup>3</sup> | 1 クラスターあたり 59 | 1 クラスターあたり 59 | 1 クラスターあたり 60 |
| クラウド自動化マルチサイト・デプロイメント |V2.0 以降でデプロイされた新しいインスタンスでサポート | サポートあり | サポートあり。 自動構成は含まない |
| ESXi サーバーの追加 | サポートあり | サポートあり | サポートあり。 自動構成は含まない |
| ESXi サーバーの削除 | サポートあり | サポートあり | サポートあり。 自動構成は含まない |
| マルチクラスター・サポート | 最大数は VMware のサイズ設定についてのガイドラインによる | 最大数は VMware のサイズ設定についてのガイドラインによる | サポートあり。 自動構成は含まない |
| クライアント管理による VMware スタックの更新とパッチ適用 | クライアント管理による更新:<br/>ネイティブ VMware ツール (VMware Update Manager) | クライアント管理による更新:<br/>ネイティブ VMware ツール (VMware Update Manager) | クライアント管理による更新:<br/>ネイティブ VMware ツール (VMware Update Manager) |
| バックアップとリストア | IBM Spectrum Protect Plus または Veeam の手動使用 | IBM Spectrum Protect Plus または Veeam の手動使用 | バックアップとリストアのソリューションは含まれない |
| ソフトウェア定義ネットワーキング | NSX Base、Advanced、Enterprise | NSX Advanced または Enterprise | NSX Standard、Base、Enterprise。 自動構成は含まない |
| vSphere と vSAN の BYOL | クラスター単位で完全にサポート | サポートなし | サポートあり |
| vCenter と NSX の BYOL | インスタンス単位で完全にサポート | サポートなし | サポートあり |
| NSX ライセンス・アップグレード・オプション | NSX Base から Advanced または Enterprise へのアップグレード、NSX Advanced から Enterprise へのアップグレードが可能。 vCenter Server with Hybridity Bundle へのアップグレードが可能。 | NSX Advanced から Enterprise へのアップグレードが可能  | なし |
| vSAN ライセンス・エディション | vSAN Advanced または Enterprise | vSAN Advanced または Enterprise | vSAN Advanced または Enterprise  |
| アドオン・サービス | HCX on {{site.data.keyword.cloud_notm}} 以外サポートあり。 vCenter Server with Hybridity Bundle へのアップグレードが可能。 | HCX on {{site.data.keyword.cloud_notm}} を含めてサポートあり。 | このソリューションの自動化によってはサポートされませんが、独自のソフトウェアを持ち込んでインストールできます。 |

## メモ
{: #inst_comp_chart-notes}

<sup>1</sup> 設計の検証とデプロイメント時の検証に基づきます。

<sup>2</sup> 新規 vCenter Server with Hybridity のインスタンスとクラスターについては、vSAN のみ。 デプロイメント後に NFS ストレージを追加できます。

<sup>3</sup> vSAN クラスターの ESXi サーバー数は最大 64 台まで増やすことができます。 詳しくは、[ESXi サーバーに関するよくある質問](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq_esxi)の_クラスターには ESXi サーバーをいくつ追加できますか?_ を参照してください。

## 関連リンク
{: #inst_comp_chart-related}

* [よくある質問](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [vCenter Server の概要](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [vCenter Server Hybridity の概要](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_overview)
* [VMware vSphere の概要](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_vsphereclusteroverview)
* [vCenter Server の部品構成表](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_bom)
* [VMware vSphere の部品構成表](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_bom)

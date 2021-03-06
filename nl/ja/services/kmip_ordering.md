---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# KMIP for VMware on IBM Cloud の注文 - 非推奨
{: #kmip_ordering}

現行バージョンの KMIP for VMware on IBM Cloud は推奨されていません。 詳しくは、[IBM サポートへのお問い合わせ](../vmonic/trbl_support.html)を参照してください。
{:deprecated}

KMIP for VMware on {{site.data.keyword.cloud}} サービスを注文するには、そのサービスを組み込む形で新しいインスタンスを注文するか、そのサービスを既存のインスタンスに追加します。

## 新しいインスタンスでの KMIP for VMware on IBM Cloud の注文
{: #kmip_ordering-new}

以下のいずれかの方法を使用して、新しいインスタンスで KMIP for VMware on {{site.data.keyword.cloud_notm}} を注文できます。
* {{site.data.keyword.vmwaresolutions_short}} コンソールから新しいインスタンスを注文する時に、**「サービス」**セクションで**「KMIP for VMware on IBM Cloud」**を選択します。
* {{site.data.keyword.cloud_notm}} カタログから**「KMIP for VMware on IBM Cloud」**を選択し、サービス設定を指定し、**「Add to New Instance」**を選択します。

## 既存のインスタンスでの KMIP for VMware on IBM Cloud の注文
{: #kmip_ordering-existing}

以下のいずれかの方法を使用して、既存のインスタンスに KMIP for VMware on {{site.data.keyword.cloud_notm}} サービスを追加できます。
* {{site.data.keyword.vmwaresolutions_short}} コンソールから、サービスを追加する対象のインスタンスを表示し、左側のナビゲーション・ペインにある**「サービス」**をクリックし、**「追加」**をクリックします。
* {{site.data.keyword.cloud_notm}} カタログから**「KMIP for VMware on IBM Cloud」**を選択し、サービス設定を指定し、**「Add to Existing Instance」**を選択します。

## KMIP for VMware on IBM Cloud サービスの構成
{: #kmip_ordering-config}

このサービスを注文する際には、以下の設定を行います。

### サービス地域
{: #kmip_ordering-service-region}

KMIP for VMware {{site.data.keyword.cloud_notm}} サービス・インスタンスをホストする {{site.data.keyword.cloud_notm}} の地域を選択します。

{{site.data.keyword.cloud_notm}} は、可用性の高い KMIP for VMware on {{site.data.keyword.cloud_notm}} サービス・エンドポイントを、サービスが使用可能な各地域で維持管理しています。

### クライアント SSL 証明書
{: #kmip_ordering-ssl}

vCenter Server では、鍵管理サーバー (KMS) クラスターを構成する必要があります。 選択した地域のエンドポイントは、クライアント SSL 証明書によって KMS に安全に接続できます。 各地域のエンドポイントについては、次の表を参照してください。 これらのエンドポイントでは、{{site.data.keyword.vmwaresolutions_short}} チームによって維持される自己署名証明書が使用されます。 証明書のサムプリントは、`a9 d0 ff 15 df 85 10 6b 61 88 fe 2e 8b d3 1a af 48 c8 a0 7a` です。

表 1. KMIP for VMware on {{site.data.keyword.cloud_notm}} サービス・エンドポイントの地域

| 地域         | エンドポイント               |
|:---------------|:-----------------------|
| ドイツ        |  `161.156.68.107:5696` |
| シドニー         |  `130.198.73.134:5696` |
| 英国 |  `158.175.93.122:5696` |
| 米国南部       |  `169.60.185.42:5696`  |

この設定を初期構成時に行うかどうかは任意です。 このフィールドをブランクにしておいてもかまいません。インスタンスがデプロイされると、vCenter Server で KMS のクライアント証明書が認識されるからです。 ただし、vCenter Server が KMS に正常に接続できるように、インスタンスのデプロイ後に証明書を入力する必要があります。

### サービス ID の API キー
{: #kmip_ordering-api-key}

IBM Key Protect Service インスタンスへのアクセスに使用する {{site.data.keyword.cloud_notm}} サービス ID の API 鍵を入力します。

### Key Protect インスタンス
{: #kmip_ordering-key-protect}

**「Retrieve」**をクリックして、利用可能な IBM Key Protect Service インスタンスのリストを取得し、鍵管理に使用するインスタンスを選択します。

### カスタマー・ルート・キー
{: #kmip_ordering-root-key}

**「Retrieve」**をクリックして、選択した IBM Key Protect インスタンスに保管されているカスタマー・ルート・キーを取得します。

## 関連リンク
{: #kmip_ordering-related}

* [KMIP for VMware on {{site.data.keyword.cloud_notm}} の概要](kmip_considerations.html)
* [Cloud Foundation インスタンス用サービスの注文、表示、削除](../sddc/sd_addingremovingservices.html)
* [vCenter Server インスタンスのサービスの注文、表示、削除](../vcenter/vc_addingremovingservices.html)
* [vCenter Server with Hybridity Bundle インスタンスのサービスの注文、表示、削除](../vcenter/vc_hybrid_addingremovingservices.html)
* [{{site.data.keyword.cloudaccesstrailshort}}events](../vmonic/at-events.html)
* [IBM Key Protect for {{site.data.keyword.cloud_notm}}](../../keymgmt/index.html)
* [vSphere セキュリティについて](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [FAQ](../vmonic/faq.html)
* [IBM サポートへのお問い合わせ](../vmonic/trbl_support.html)

---

copyright:

  years:  2016, 2018

lastupdated: "2018-05-03"

---

# ユーザー・アカウントと設定の管理

{{site.data.keyword.vmwaresolutions_full}} は、{{site.data.keyword.slapi_short}} 呼び出しを介して {{site.data.keyword.cloud_notm}} インフラストラクチャーと対話します。 {{site.data.keyword.slapi_short}} に安全にアクセスするには、{{site.data.keyword.cloud_notm}} アカウントの資格情報を {{site.data.keyword.vmwaresolutions_short}} ユーザー・アカウントに関連付ける必要があります。

**注**: {{site.data.keyword.cloud_notm}} アカウントは、以前は IBM SoftLayer アカウントと呼ばれていました。

{{site.data.keyword.vmwaresolutions_short}} コンソールで、各種イベントの E メール通知を受け取るかどうかを指定することもできます。

## 始める前に

* {{site.data.keyword.vmwaresolutions_short}} ユーザー・アカウントに関連付けることができる {{site.data.keyword.cloud_notm}} アカウントは 1 つだけです。
* 使用する {{site.data.keyword.cloud_notm}} アカウントは、特定の要件を満たしている必要があります。 詳しくは、[{{site.data.keyword.cloud_notm}} アカウントの要件](slaccountrequirement.html)を参照してください。
* {{site.data.keyword.cloud_notm}} アカウントの API キーが変更された場合は、{{site.data.keyword.vmwaresolutions_short}} ユーザー・アカウントのキーを更新する必要があります。

   **重要**: **「設定」**ページに保存されている API キーが最新の正確なキーであることを確認してください。
   そうしないと、API キーの検証を必要とする操作が失敗する可能性があります。

{{site.data.keyword.vmwaresolutions_short}} アカウントに {{site.data.keyword.cloud_notm}} アカウントを関連付けるには、{{site.data.keyword.vmwaresolutions_short}} コンソールの**「設定」**ページで {{site.data.keyword.cloud_notm}} アカウントの資格情報を入力します。

{{site.data.keyword.cloud_notm}} アカウントを関連付けると、コンソールは自動的に {{site.data.keyword.cloud_notm}} アカウント資格情報を取得し、{{site.data.keyword.cloud_notm}} 上の VMware 環境と対話します。

## 手順

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「設定」**をクリックします。
2. 新たにイベントが発生したときに E メールで通知を受け取るには、**「E メール通知を有効にする」**チェック・ボックスを選択します。
3. 新たにイベントが発生したときにコンソールで通知を受け取るには、**「コンソール通知を有効にする」**チェック・ボックスを選択します。
4. **「IBM Cloud インフラストラクチャーの資格情報」**領域に {{site.data.keyword.cloud_notm}} アカウントのユーザー名を入力し、コンソールの指示に従って {{site.data.keyword.slapi_short}} キーを入力します。
5. **「資格情報の保存」**をクリックします。

## 結果

これ以降、{{site.data.keyword.cloud_notm}} インフラストラクチャーとの対話を必要とするアクションには、ここで保管した {{site.data.keyword.cloud_notm}} アカウント資格情報が使用されます。 E メール通知またはコンソール通知を有効にしたインスタンス・イベントがある場合、それらのイベントが発生すると、E メールまたはコンソールのメッセージで通知されます。

## 関連リンク

* [よくある質問](faq.html)
* [Cloud Foundation インスタンスの注文](../sddc/sd_orderinginstance.html)
* [vCenter Server インスタンスの注文](../vcenter/vc_orderinginstance.html)
* [通知](notifications.html)
* [SoftLayer API](../../../customer-portal/cpapi.html){:new_window}
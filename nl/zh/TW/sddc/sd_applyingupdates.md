---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 將更新套用至 Cloud Foundation 實例
{: #sd_applyingupdates}

{{site.data.keyword.vmwaresolutions_full}} 主控台會定期偵測並列出您可套用至 VMware 虛擬環境的可用軟體更新。

可用的更新是實例的軟體更新清單中的記錄，可立即套用或排定稍後進行。更新是一個組合，包含一個以上用來更新 IBM 管理元件及 VMware 元件的套件。

由於已啟用自動更新，因此不再列出 IBM CloudDriver 更新。新增 ESXi 伺服器、新增叢集，以及訂購服務等的動作會自動將實例更新至最新版本。如需自動更新的相關資訊，請參閱 [2.5 版的版本注意事項](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-relnotes_v25)中的 *IBM CloudDriver 備援* 小節。
{:note}

## 開始之前
{: #sd_applyingupdates-prereq}

在您嘗試套用更新之前，請按一下向下箭頭來展開更新項目，並驗證下列資訊：
* 更新的版本。您必須依最早到最新的時間順序來套用更新。套用最新的更新之前，請確定已套用所有先前的更新。例如，嘗試套用 2.5 版更新之前，您必須套用 2.4 版更新。
* 是否需要關閉時間。
* 完成更新的總估計時間。
* 更新對 VMware 虛擬環境的影響。表 1 顯示不同的更新層次對於系統有何影響。
* 更新詳細資料。

表 1. 更新層次及影響

<table>
  <tr>
    <th>更新層次</th>
    <th>影響</th>
  </tr>
  <tr>
    <td>低</td>
    <td>此更新不會影響任何系統。您不需要在排定的關閉時間套用它。</td>
  </tr>
  <tr>
    <td>中</td>
  <td>此更新可能會影響部分系統。建議您在排定的關閉時間套用它。</td>
  </tr>
    <tr>
    <td>重大</td>
  <td>此更新會影響部分或所有系統。您必須在排定的關閉時間套用它。</td>
  </tr>
</table>

## 套用 Cloud Foundation 實例更新的程序
{: #sd_applyingupdates-procedure}

1. 從 {{site.data.keyword.vmwaresolutions_short}} 主控台中，按一下左導覽窗格中的**資源**。
2. 在 **Cloud Foundation 實例**表格中，按一下要更新的實例。
3. 在**摘要**頁面上，驗證所有實例詳細資料都已正確顯示。然後，按一下左導覽窗格上的**基礎架構**，以驗證**基礎架構**頁面上的詳細資料。如果未顯示詳細資料，這可能表示因為防火牆規則或其他網路問題的緣故，而有 IBM CloudDriver 虛擬伺服器實例 (VSI) 連線問題。請先解決問題，再繼續下一步，否則更新可能會失敗。
4. 在左導覽窗格上，按一下**更新及修補程式**。
5. 按一下向下箭頭來展開您要套用的更新，然後完成下列其中一個步驟：
   *  若要立即啟動更新，請按一下更新項目之**動作**直欄中的溢位功能表圖示，然後按一下**立即更新**。
   *  若要排定未來的更新，請按一下更新項目之**動作**直欄中的溢位功能表圖示，然後按一下**排定更新**。選取您要啟動更新的日期、時間及時區。按一下**確定**。
6. 如果您要在多站台部署配置中套用 Cloud Foundation 實例的更新，則會顯示標題為**更新所需的步驟**的區段，其中列出多站台部署中所有實例所需的更新作業。您必須對每個步驟按一下**套用更新**，來依序完成步驟。您必須先等待上一步完成，再開始下一步。

## 結果
{: #sd_applyingupdates-results}

1. 啟動更新作業之前，會完成實例的性能檢查。如果性能檢查失敗，則會通知您，讓您可以在套用更新之前修正問題。
2. 在包括 VMware 元件更新的更新期間，可能需要從 ESXi 伺服器移轉 VM，才能進入維護模式。如果 VM 已有本端資料儲存庫，或已裝載 CD-ROM，則可能會阻礙 VM 移轉。
3. 在佈建新的環境期間，{{site.data.keyword.vmwaresolutions_short}} 會建立用於實例管理（包括套用更新）的 **automationuser** ID。請不要變更此使用者 ID 的密碼。變更密碼可能會導致更新失敗。

4. 在您套用更新之後，軟體更新狀態清單中會出現一筆記錄，您可以在其中檢視更新的詳細進度及狀態。更新順利完成時，已安裝的軟體更新清單中會出現一筆記錄。

  若要擷取更新工作的最新狀態，請按一下頁面右上方的重新整理圖示。
  {:tip}

5. 如需更新狀態的相關資訊，請參閱下表。

   表 2. 更新狀態的詳細資料

    <table>
      <tr>
        <th>狀態</th>
        <th>詳細資料      </th>
      </tr>
      <tr>
        <td>可用</td>
        <td>更新可供套用。在套用所有先前的更新之前，您無法選取可用的更新。</td>
      </tr>
      <tr>
        <td>進行中</td>
      <td>更新工作已起始，但尚未完成。在現行更新工作完成之前，您無法套用任何其他更新。</td>
      </tr>
        <tr>
        <td>已安裝</td>
      <td>更新工作已完成。會更新 VMware 平台的對應元件。</td>
      </tr>
        <tr>
        <td>失敗</td>
      <td>更新工作失敗。主控台會報告更新失敗的錯誤。請先檢閱錯誤並修正報告的問題，再重新套用更新。</td>
      </tr>
          <tr>
        <td>已排定</td>
      <td>已排定稍後執行更新工作。更新工作會在您排定的時間自動啟動。</td>
      </tr>
          <tr>
        <td>不明</td>
      <td>無法取得更新工作的狀態。請與 IBM 支援中心聯絡，以取得協助。</td>
      </tr>
    </table>

6. 如果更新處理程序在特定步驟失敗，請[與 IBM 支援中心聯絡](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)以取得協助。將會建議您解決問題的方式，並引導您從失敗的步驟重新啟動升級。

## 相關鏈結
{: #sd_applyingupdates-related}

* [Cloud Foundation 概觀](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview)
* [Veeam on {{site.data.keyword.cloud_notm}} 概觀](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations)
* [與 IBM 支援中心聯絡](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [常見問題](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)

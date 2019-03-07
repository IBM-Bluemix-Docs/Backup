---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 從備份還原
{: #simplerestore}

請使用這些步驟，以 {{site.data.keyword.backup_full}} 來完成「檔案」還原。若要還原系統映像檔，請遵循 [Windows BMR](restore-bmr-system-volume-image.html) 指示。

## 啟動 {{site.data.keyword.backup_notm}} 入口網站
{: #startWebCCsimple}

請記得啟動您的 {{site.data.keyword.BluVPN}} 連線來存取 {{site.data.keyword.BluSoftlayer_full}} 專用網路。否則，{{site.data.keyword.backup_notm}} 入口網站鏈結將無法運作。
{:important}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取要還原之檔案所在的伺服器。按一下箭頭，以顯示 {{site.data.keyword.backup_notm}} 入口網站鏈結。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站**，以在瀏覽器中啟動 {{site.data.keyword.backup_notm}} 入口網站用戶端。

## 還原資料

1. 在左側的導覽窗格中，按一下**所有代理程式**。
2. 按一下「代理程式」來顯示工作。
3. 按一下包含您想要之資料的「工作」。
4. 按一下**執行還原**。
5. 選取還原來源。
6. 選取備份版本。
7. 輸入加密密碼。
8. 按**下一步**繼續。
9. 選取您要包含之檔案和目錄旁邊的勾選框，然後按一下**包含**以儲存您的選項。
10. 您可以使用出現的視窗來進一步過濾您的選取項目，或按一下**確定**，依原狀使用您選取的項目。在您包含檔案和目錄選項之後，就無法在資料檔窗格中選取那些檔案。它們會顯示在右側的備份集窗格中。

   您可以重複步驟 10，以新增更多檔案或移除先前新增的檔案（方法為使用**排除**）。您也可以使用**移除**，從**備份集**窗格中刪除任何明細行項目。
   {:tip}

11. 在依您想要的方式配置備份集之後，請按**下一步**繼續。
12. 在下一個窗格中保留預設值，或依您的喜好設定自訂還原，然後按一下**執行還原**。
13. 當**處理程序詳細資料**畫面上的「狀態」顯示**還原已完成**時，表示已還原檔案。

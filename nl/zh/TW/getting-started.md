---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}_
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# 入門指導教學
{: #gettingstarted}

備份可確保您的資料安全地儲存在裝置外部，而且在遺失的情況也受到保護。{{site.data.keyword.backup_full}} 是一種以代理程式為基礎的自動化備份系統，可透過 {{site.data.keyword.backup_notm}} 入口網站的瀏覽器型管理公用程式進行管理。{{site.data.keyword.backup_notm}} 提供方法讓使用者在 {{site.data.keyword.BluSoftlayer_full}} 網路的一個以上資料中心內的伺服器之間備份資料。管理者可以將備份設定為遵循每日、每週或自訂排程，且排程是以完整系統、特定目錄或甚至個別檔案為目標。額外的外掛程式確保與 Microsoft Exchange 和 Microsoft SQL 這類軟體以及其他類型的協力廠商軟體相容，並在必要時讓使用者完成 Bare Metal Restore。{:shortdesc}

## 開始之前
{: #prereqs}

您必須有有效的授權才能使用 IBM Cloud Backup。您可以使用兩種方式來購買 {{site.data.keyword.backup_notm}} 服務。

- [訂購伺服器時購買備份](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver)。
- [以升級方式購買備份](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade)。

如需訂購及定價的相關資訊，請參閱[佈建 {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering)。

## 安裝 {{site.data.keyword.backup_notm}} 代理程式

下列作業系統可支援「{{site.data.keyword.backup_notm}} 代理程式」。

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

請遵循適合您作業系統的指示：
- [在 Linux 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [在 Windows 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [在 Windows 2016 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## 存取 {{site.data.keyword.backup_notm}} 入口網站（先前稱為 WebCC）

{{site.data.keyword.backup_notm}} 入口網站可用來與 {{site.data.keyword.BluSoftlayer_full}} 所提供之任何 {{site.data.keyword.backup_notm}} 服務互動。{{site.data.keyword.backup_notm}} 入口網站是一種瀏覽器型用戶端，其執行於 {{site.data.keyword.BluSoftlayer_full}} 專用網路，可供完全控制任何 {{site.data.keyword.backup_notm}} 服務，包括配置和還原。

1. 透過 VPN 存取「專用網路」。

   無法透過公用網路存取 {{site.data.keyword.backup_notm}} 入口網站。必須先建立 VPN 連線。
   {:important}
2. 在 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window} 中，存取「備份儲存空間」畫面。
3. 按一下想要查看之 {{site.data.keyword.backup_notm}} 服務列上的任何位置，來展開視圖。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**，以在瀏覽器中啟動入口網站用戶端。

## 配置備份代理程式和備份排程

在您訂購 {{site.data.keyword.backup_notm}} 並在伺服器上安裝代理程式之後，即可開始建立資料備份。請遵循下列步驟來配置代理程式及保留排程。

1. 登入 {{site.data.keyword.backup_notm}} 入口網站。
2. 按一下**所有代理程式** > **未配置的代理程式**。
3. 按一下**這是我想要配置的新代理程式**鏈結。逐步執行處理程序，並輸入下列資訊：
   1. 代理程式配置 - 提供代理程式說明，並按**下一步**。
   2. 工作類型選取 - 輸入工作名稱、工作說明和備份來源類型，然後按**下一步**。
   3. 選取 - 選取目錄並按一下**包含...**。
   4. 選項 - 提供密碼
   5. 排程 - 按一下**新增**以建立排程，並按**下一步**。
   6. 選取預設儲存庫，並按一下**確定**。
   7. 按一下**儲存**。
4. 建立保留排程。
   1. 選取**編輯** > **代理程式設定**。
   2. 按一下**新增**。
   3. 完成您的保留詳細資料。
   4. 按一下**確定**。
   5. 按一下**儲存**。

              如需「保留方案」的相關資訊，請參閱[常見問題](faqs.html)。
        {:tip}

## 執行第一個備份工作

1. 登入 {{site.data.keyword.backup_notm}} 入口網站。
2. 按一下**所有代理程式**，然後選取您已配置的代理程式。
3. 按一下**執行備份**。
4. 確認「目的地」，並選取保留方案。
5. 按一下**啟動備份**。您可以在處理程序執行時檢視備份詳細資料。
6. 當備份完成時，請按一下**關閉**。

如需相關資訊，請參閱[在 Linux 上配置簡單的檔案層次備份](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)。
{:tip}

## 在主控台中存取及檢視 {{site.data.keyword.backup_notm}} 儲存空間詳細資料

您隨時可以在 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}和 {{site.data.keyword.slportal}} 上檢視服務的儲存空間詳細資料。可檢視的詳細資料包括與所選取 {{site.data.keyword.backup_notm}} 服務相關聯的密碼、儲存空間位址及用量。

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間**，然後從清單中選取**備份**。
2. 按一下您要檢視其儲存空間詳細資料的儲存庫列的任何位置。從這個視圖中，看不到「密碼」。
3. 按一下**密碼**欄位旁邊的**顯示**勾選框，以檢視所選取 {{site.data.keyword.backup_notm}} 服務的密碼。

在 {{site.data.keyword.slportal}} 內對 {{site.data.keyword.backup_notm}} 密碼所做的變更，會對服務本身進行。若要重設密碼，請遵循[變更備份服務的密碼](/docs/infrastructure/Backup?topic=Backup-changePassword)中的步驟。
{:important}

## 取得更多線上說明

{{site.data.keyword.backup_notm}} 入口網站的系統有完整的文件說明，並且可在  {{site.data.keyword.backup_notm}} 入口網站中存取應用程式的支援。按一下位在**說明**右上角之藍色圓圈中的白色問號。按一下左側導覽列中的任何文章或主題，以檢視相關資訊。
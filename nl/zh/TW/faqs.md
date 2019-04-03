---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# 常見問題
{: #faqs}

## 可以備份哪些類型的應用程式？
{: faq}

{{site.data.keyword.backup_full}} 可以用來備份各種應用程式。{{site.data.keyword.BluSoftlayer_full}} 也有針對所備份的一些較常見軟體系統提供軟體代理程式，包括：

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

這裡列出的外掛程式僅與 Windows 伺服器相容，但 Oracle 或 VMware 外掛程式除外。每個代理程式都可以免費作為備份服務的附加程式提供。

<hr>

## 可以備份資料的頻率為何？
{: faq}

在 {{site.data.keyword.backup_notm}} 中，可以手動進行備份，也可以將備份排定為單一實例或循環執行。循環備份可以每日、每週、每月進行，或是根據自訂排程進行，且可以隨時更新或取消。

每日或每小時執行數次的高頻率備份可能導致備份工作毀損。毀損發生的原因是因為備份儲存庫沒有足夠的時間執行必要的背景維護作業。備份工作會優先於維護作業。因此，當頻繁進行備份時，儲存庫會繼續執行備份工作，而導致安全集的數目增加。
{:note}

<hr>

## 保留方案如何運作？
{: faq}

{{site.data.keyword.backup_notm}} 容許資料保留，視您想要回復至多久以前而定。**每日**保留方案會保留資料七天、**每週**方案會保留資料一個月，而**每月**方案會保留資料一年。在每個期間結束時，會轉出最舊的資料集，而所進行的第一個「差異備份」會變成最舊的可用還原點。

您可以修改預設保留方案，並且可以建立自訂的保留方案。不過，IBM 建議使用預設保留作為起點。當您建立新的保留方案或修改現有保留時，請確定未選取「保存」選項。不支援保存。
{:tip}

<hr>

## 何謂差異技術？
{: faq}

第一個備份是「種子」（完整備份）、下一個及後續備份為「差異」備份（亦即，僅限變更），但它們相等於並仍可視為「完整備份」。亦即，您可以從其中還原所有或任何檔案。使用此技術，會在每個階段作業建立「完整備份」，但它可以在儲存庫上節省大量空間，並減少完成每個後續備份所需的時間量。

<hr>

## 備份安全嗎？
{: faq}

依預設，所有線上 (OTW) 加密都是利用 AES 256 位元加密來進行加密。您也可以選擇使用 AES 256 位元，以加密格式儲存資料。

您必須記住您的加密密碼。沒有您的密碼，就無法還原您的資料。如果您遺失密碼，則無法取回您的資料。
{:important}

壓縮比例容許零壓縮至最大比例壓縮，視檔案類型而定，可能壓縮從 20% 到 30% 之間任何程度。

<hr>

## 系統狀態備份會儲存哪些資訊？
{: faq}

系統狀態備份包括但不限於 COM + 類別登錄資料庫、登錄、開機檔、系統檔案、效能計數器。這一切視您的系統而定。系統檔案會由於系統的作業系統及服務套件而有所不同。通常會有數千個之多。當您將這些 DLL 包含在備份中時，MS Windows 會建立這些 DLL 的動態清單。藉由包括系統檔案，您可以從毀損的系統檔案回復，或如果您不小心移除某些服務套件，或想要使用 Bare Metal Restore 進行回復時，也可以進行回復。您可以回復為備份的狀態，而不需要從安裝套件重新安裝作業系統，然後個別安裝每個服務套件。

沒有使用者資料檔會內含在「系統狀態備份」中。系統狀態備份工作必須配置為獨立式工作。「系統狀態備份」工作中不可包含任何其他資料來源。
{:important}

<hr>

## 開啟檔案會發生什麼情況？
{: faq}

依預設，基本用戶端具有最先進的技術，可處理在作業系統上執行的大部分開啟檔案。

<hr>

## 我可以在何處找到定價資訊？
{: faq}

如需相關資訊，請參閱 [Backup storage ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 及 [EVault on IBM Cloud: Pricing ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/backup/pricing){:new_window}。

<hr>

## 可以增加或減少 {{site.data.keyword.backup_notm}} 容量，而不危及備份嗎？
{: faq}

您可以透過 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window} 來增加或減少儲存庫的大小。對容量的修改不會影響儲存庫中所儲存資料的完整性。如需相關資訊，請參閱[擴充容量](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity)。

<hr>

## 超出 {{site.data.keyword.backup_notm}} 容量時，會發生什麼情況？
{: faq}

即使已達到先前購買之容量的限制，您仍然可以儲存並擷取您的備份。不過，在下一次的計費對帳單中，將會針對所使用的每個額外 GB，向您收取額外費用。

<hr>

## 如何在 {{site.data.keyword.backup_notm}} 入口網站中設定通知，讓我知道備份是否失敗？
{: faq}

您可以在「進階」標籤上設定通知。請在 {{site.data.keyword.backup_notm}} 入口網站的**快速鏈結**中尋找相關指示。

<hr>

## 使用 BMR 外掛程式時，是否可以從單一磁碟移至 RAID 陣列？

是，可以。不過，因為 RAID 陣列會導致大小減少，所以您需要選取大容量的裝置。

<hr>

## 使用 BMR 外掛程式時，將映像檔還原至比原始磁區更大的磁碟會怎麼樣？
{: faq}

如果您將映像檔還原到比原始磁區更大的磁碟，則會取消配置剩下的空間。因此，例如，當您有一個 500 GB 磁碟並將其資料還原到 1 TB 磁碟時，則最後會有 500 GB 取消配置的磁碟空間。使用 Windows 2008，您可以使用內建磁碟公用程式來增加主要分割區。不過，Windows 2003 沒有類似的內建功能，因此您必須以其他方式配置空間。

<hr>

## BMR 是否可以用來進行定期備份？
{: faq}

BMR 備份不是磁碟映像檔，而是系統磁區映像檔備份系統。此系統並非預期用於定期備份，而是與其搭配使用。  

<hr>

##BMR 是否可以用來進行資料庫備份？
{: faq}

資料庫備份必須與一般 {{site.data.keyword.backup_notm}} 方法分開執行。BMR 並不會取代 SQL 或 Oracle 外掛程式的需求。雖然 BMR 使用 VSS 技術來備份開啟檔案，但無法永遠保證備份的檔案為交易一致。這些特殊化應用程式類型的建議是您建立兩個備份工作：一個用於備份作業系統及應用程式二進位檔，另一個用於應用程式資料。

<hr>

## 哪種類型的還原工作可以與 BMR 搭配執行？

您可以執行整個系統還原，也可以從備份中挑選個別檔案來進行還原。BMR 備份工作可以取代您的現行檔案備份工作。還原處理程序是在作業系統內執行，就像傳統備份工作一樣。

<hr>

## BMR 具有開啟檔案備份功能嗎？
{: faq}

BMR 具有開啟檔案備份功能。不過，BMR 並不會取代 SQL 或 Oracle 外掛程式的需求。請按一下[這裡](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin)，以取得 MSSQL 外掛程式安裝指示。

<hr>

## BMR 還原需要多少磁碟空間和時間？
{: faq}

從預設安裝所進行的備份使用大約 6 GB。這類還原在 1 GB 埠上大約需要 15 分鐘。此程序也會受到專用埠速度影響。如果您需要更快速的備份及還原，可能需要增加埠速度。

<hr>

## VSS（磁區陰影複製服務）的功用為何？
{: faq}

SQL Server 外掛程式的現行版本會使用 VSS（磁區陰影複製服務）來完成備份。使用 VSS，SQL Server 外掛程式會有效地備份 SQL 資料庫，即使是跨磁區的 SQL 資料庫。當應用程式繼續寫入磁區時，可以完成備份。SQL Server 外掛程式提供資料庫內和跨資料庫的資料一致性。VSS 容許同時執行多個備份。

<hr>

## 是否仍支援 32 位元版本的 EVault for Windows 8？
{: faq}

否。2017 年 3 月，32 位元版本備份軟體代理程式與 Windows Server 2008 Standard 及 Datacenter Edition 已一同淘汰。

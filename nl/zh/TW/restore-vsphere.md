---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere, backups

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 還原 vSphere 資料
{: #VRARestore}

當 VM 在 vSphere 環境中受到保護時，您可以使用「vSphere 回復代理程式」來還原 [vSphere VM](#restoreVMs) 以及[還原檔案和資料夾](#restoreFFVRA)。

## 還原 vSphere VM
{: #restoreVMs}

1.	在導覽列上，按一下**電腦**。網格會列出可用的電腦。
2.	尋找含有您要還原之 VM 的 vSphere 環境，按一下該列以展開其視圖。
3.	按一下**工作**。
4.	尋找含有您要還原之 VM 的備份工作，然後按一下工作之**選取動作**功能表中的**還原**。
5.	在**選擇您要還原的內容**對話框中，選取**虛擬機器**。
6.	按一下**繼續**。「還原」對話框即會顯示最新的工作安全集。
    * 若要還原另一個來源中的資料，請按一下**來源裝置**清單中的來源（儲存庫）。
    *	若要從較舊的安全集中還原，請按一下**瀏覽安全集**按鈕。在出現的行事曆中，按一下您要從中還原的安全集的日期。
7.	在**要還原的項目**畫面中，選取您要還原的每個 VM。
8.	在**加密密碼**欄位中，鍵入資料加密密碼。
9.	在**目的地資料儲存庫**清單中，按一下已還原 VM 的資料儲存庫。
10.	選取下列其中一個選項，將 VM 還原至已選取的資料儲存庫：
  * **僅將所有選取的「虛擬機器」還原至已選取的資料儲存庫。**
  * **只有在「虛擬機器」的原始資料儲存庫無法使用時，才還原至已選取的資料儲存庫。** 如果備份的 VM 包含多個位於兩個以上資料儲存庫的 VMDK，而且一個以上的資料儲存庫無法使用，則整個 VM 會還原至已選取的資料儲存庫。

  如果您將 VM 或範本還原至 vCenter，而且原始 VM 存在，則 VM 會還原為原始 VM 的複本，且會使用下列名稱：<VMname>-vra-restored-<Date>。如果原始 VM 已開啟電源、關閉電源或暫停，則 VM 會還原為複本。如果原始 VM 已開啟電源，並且使用靜態 IP 位址，則當還原的複製 VM 開啟電源時，您可能會遇到 IP 位址衝突。
  {:note}

13.	在**目的地主機**清單中，按一下您要在其中登錄 VM 的主機。此清單只顯示可存取已選取的資料儲存庫的主機。
14.	選取下列其中一個選項，向已選取的主機登錄還原的 VM：
  * **僅向已選取的主機登錄所有選取的「虛擬機器」。**
  * **只有在「虛擬機器」的原始主機無法使用時，才向已選取的主機登錄。**
15.	若要在 VM 還原之後開啟其電源，請選取**還原之後開啟 VM 的電源**。
16.	在**效能選項**中，保存預設值。
17.	按一下**執行還原**。

## 還原檔案和資料夾
{: #restoreFFVRA}

您可以使用 vSphere Recovery Agent (VRA)，從受保護的 Windows VM 中還原檔案和資料夾。您可以同時從多個 VM 中還原檔案和資料夾。您無法使用 VRA 從 Linux VM 還原檔案和資料夾。
{:important}

在檔案和資料夾的還原期間，已選取 VM 中的磁區會裝載為 VRA 執行所在之機器上的磁碟機。然後，您可以共用部分或全部已裝載的磁碟機，讓使用者可以複製這些磁碟機中的檔案和資料夾。您也可以登入 VRA 機器，並且複製已裝載磁碟機中的檔案和資料夾。

磁碟上的檔案和資料夾可供 VRA 系統的任何使用者存取，包括非管理使用者。如果您擔心安全問題，請保護代理程式機器並防止使用者從本端登入機器。
{:tip}

1. 在導覽列上，按一下**電腦**。網格會列出可用的電腦。
2. 尋找含有您要還原之 VM 的 vSphere 環境，按一下該列以展開其視圖。
3. 按一下**工作**。
4. 尋找含有您要還原之 VM 的備份工作，然後按一下工作之**選取動作**功能表中的**還原**。
5. 在**選擇您要還原的內容**對話框中，選取**檔案和資料夾**。
6. 按一下**繼續**。「還原」對話框即會顯示最新的工作安全集。
  * 若要還原另一個資源中的資料，請按一下「來源裝置」清單（儲存庫）中的來源。
  * 若要從較舊的安全集中還原，請按一下「瀏覽安全集」按鈕。在出現的行事曆中，按一下您要從中還原的安全集的日期。在行事曆右側，按一下您要從中還原的特定安全集。
7. 在**要還原的項目**畫面中，選取含有您要還原之檔案或資料夾的 VM。
8. 在**加密密碼**欄位中，輸入資料加密密碼。
9. 在**閒置時間**欄位中，輸入閒置的分鐘數，在此期間之後，共用磁碟機會自動解除共用。閒置時間的範圍從 2 - 180 分鐘不等。

    只要複製新資料，磁碟機就不會解除共用。如果您多次從共用磁碟機複製相同的資料，則系統可能逾時，因為未讀取到新資料。
    {:note}

10.	在**效能選項**中，選取「使用所有可用的頻寬」。
11.	按一下**執行還原**。
12. 已選取 VM 中的已還原磁區會對映為 VRA 執行所在之機器上的磁碟機，並可在「還原裝載」資料夾中使用。請執行下列其中一個步驟。
  * 複製對映磁碟機中您要還原的檔案和資料夾。
  * 與其他使用者共用一部以上對映磁碟機。然後，使用者可以存取 UNC 共用，並且複製他們想要還原的檔案和資料夾。
  * 從 VRA 機器上的「還原裝載」資料夾中共用一個以上目錄。然後，使用者可以存取 UNC 共用，並且複製他們想要還原的檔案和資料夾。
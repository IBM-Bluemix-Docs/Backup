---

copyright:
  years: 1994, 2019
lastupdated: "2019-09-27"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Restoring from a backup
{: #simplerestore}

Use these steps to complete a File restore with {{site.data.keyword.backup_full}}. To restore a system image, follow the [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR) instructions.
{:shortdesc}

## Starting WebCC
{: #startWebCCsimple}

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.cloud}} private network. The WebCC link doesn't work otherwise.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Storage** > **Cloud Backup** to display the servers with backup service.
3. Select the server where the files to be restored are located. Click the arrow to reveal the WebCC link.
4. Click **WebCC** to start the WebCC client in your browser.

## Restoring your data

1. On the navigation, click **Computers**. The computers page shows the registered computers and environments. Expand the server that you want to restore to a previous state.
2. Click **Jobs** to load the job options.
3. lick **Select job Task** and click **Restore from Another Computer**.
4. Confirm the vault, computer and job information and click **Okay**.
5. Enter the encryption password of the previous backup.
6. The Restore Options window appears. By default, it displays the most recent safeset. To choose a different date, click the Calendar Tab and view other safesets.
9. Select the files and directories that you want to include. Then, click **Include** to save your choices.

   Default restore options place the files in their original location, and if files exists in the destination folder with the same name folder, the incoming file is re-named. These options can be changed and alternate restore location can be selected from Restore Destination options.
   {:note}
10. When your restore set is configured the way that you want it, click **Apply Now**.
12. Then, click **Run Restore**.
13. The files are restored when the Status displays **Restore completed** on the **Process Details** screen.

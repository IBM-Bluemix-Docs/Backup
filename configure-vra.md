---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuring VRA backup jobs
{: #ConfigureVRA}

After the VMware vSphere  environment is added in the {{site.data.keyword.backup_notm}} Portal, you can create a backup job that specifies which virtual machines (VMs) to back up, and where to save the backup data. To back up the data, you can run the backup job manually or schedule the backup job to run.

You must configure vault settings and vCenter information before you can add a backup job.
{:important}

## Starting {{site.data.keyword.backup_notm}} portal
{: #startWebCCVRA}

You need to be connected to the {{site.data.keyword.BluSoftlayer_full}} private network to be able to start {{site.data.keyword.backup_notm}} portal.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**.<br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup services.
3. Select the server where the files to be backed up are located. Click the right-pointing expansion arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the portal client in your browser.

   If {{site.data.keyword.backup_notm}} portal doesn't start, you might have a problem with your VPN connection. You might also see a message that says the form you’re sending isn’t secure. It is expected - proceed by sending the form.
   {:tip}

## Adding a vSphere backup job

1. On the navigation, click **Computers**. The computers page shows the registered computers and environments.
2. Click **Jobs**.
3. In the Select job Task menu, click **Create New VMware vCenter Job**.
4. Specify the following information.
   * In the **Name** field, type a name for the backup job.
   * In the **Description** field, optionally type a description for the backup job.
   * In the **Destination** list, select the vault where you want to save the backup data.
   * In the **Password** and **Confirm Password** fields, type an encryption password. You can also type a password hint in the Password Hint field.
   A vault appears in the list only if it is assigned to the user, or if the user added it to the computer’s Vault Settings.<br/>
   For new backup jobs, the encryption method is AES 256 bit. Existing jobs can have other encryption methods.
   {:note}

5.	In the **Include in Backup** field, take one or more of the following steps until the Backup Set field shows the VMs that you want to include in the backup job.

   * To add specific VMs to the backup job, select each VM, and then click **Include**.
   * To exclude specific VMs from the backup job, select each VM, and then click **Exclude**.
   * To add VMs to the backup job by name, check the Virtual Machines box, and then click **Include**.
   * To remove an inclusion or exclusion record from the Backup Set box, click **Delete** next to the record.

6. Click **Apply Now** to consolidate and simplify records in the Backup Set box, if changes need to be applied.
7. Click **Create Job**.

## Setting up a schedule

After the backup job is created, you can add one or more schedules for running the job automatically.

1. When you click **Create Job**, the Schedule window appears and gives you an option to set up a custom schedule for the backup job.

   By default Daily retention is selected for the job. Retention and Job schedule can be changed in this window, and multiple Retention schemes can also be assigned to the backup job.
   {:note}
2. Click **Save** to save the new schedule. The new job shows up under the Computers tab in Jobs section. The Last backup status shows that the job never ran. The scheduled backup job runs automatically at the scheduled time.

## Running a scheduled job

Scheduled backup jobs can also be executed immediately.

1. Click **Select Action** and select **Run Job**. The Run Job window appears and gives you information about the Destination Vault and Retention scheme that are assigned to the job.

   If multiple vaults and retention schemes are assigned to the job, these options can be changed in the Run job window by clicking the Destination and Retention Scheme menu options.
   {:note}
2. Click **start Backup job** to execute the backup job immediately. The progress window shows you the status of backup job and when the job is finished the job status changes from "Never Run" to "Completed".

To see the status of the last backup job that ran, click the Jobs tab. All job logs can be accessed from the action menu. Click **Action** and select **History/Logs**.
{:tip}

For more information about restoring VMs or Files and folders, see [Restoring vSphere data](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
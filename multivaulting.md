---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Multi-vaulting
{: #multivault}

Multi-vaulting is the ability for a client to connect a server to more than one vault location. It provides redundancy and peace of mind because backups are available even if one site fails.
{:shortdesc}

**Key points**

1. Multiple vaults can be managed through the same {{site.data.keyword.backup_notm}} portal and they are handled the same way. The only difference is that you have different vault choices.
2. Plug-in licensing is on a per vault basis - for example, if you purchased the MSSQL plug-in for a vault in Washington DC, it doesn't work on the Seattle vault.
3. The new vault needs to be manually added to the {{site.data.keyword.backup_notm}} portal after each purchase.



**{{site.data.keyword.backup_notm}} Vault Director locations**

Multi-vaulting is available across all data centers and there's no geographical limitation in selecting a remote vault. When vaults are configured correctly, all the configured vaults appear in vault settings.

Backing up to remote data center locations can take longer than backups to the same data center where your server is located.
{:note}

## Adding a Remote Vault to an Account

You must add the new remote vault to the account before a new backup location can be added in the {{site.data.keyword.backup_notm}} portal.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Devices**
3. Locate and click the link for the server in question.
4. Under **Device Details**, click **Storage**.
5. When the Storage section opens up, scroll down to **{{site.data.keyword.backup_notm}}**, and click **Add**.
6. In the **Order {{site.data.keyword.backup_notm}}** window, select the remote vault location by clicking its entry in the pull-down list.
7. Select the size of the storage, then click **Continue**
8. Check the **I have read the Master...** box and click **Place Order**.

The newly ordered vault is automatically added to the account. If not, contact Sales for help.

When the ordering process is complete, go to the **Storage** > **Backup** to see the new vault that is listed.

## Adding an Extra Vault in {{site.data.keyword.backup_notm}} portal

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Storage** > **Cloud Backup** to display the servers with backup service.
3. Select the server that you want to be able to back up to multiple vaults. Click the arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click the **{{site.data.keyword.backup_notm}} portal Login** link to start the portal client in your browser.

   {{site.data.keyword.backup_notm}} portal is only accessible through {{site.data.keyword.BluVPN}}.
   {:tip}
5. In the navigational pane, click **All Agents**.
6. Click **Edit** and select **Vault Settings**.
7. In the **Vault Settings** window, click **Add**.
8. In the **New Vault** window,
  1. In the Vault Profile menu, choose **Enter Vault Settings** to create a new entry. Don't update the existing entry, it doesn't work.
  2. The vault name can't be the same as the other vault name. Try adding a `-2` tag to the end of it. <br/>

     The vault name field has a 15 character limit.
     {:important}
  3. The IP address field is populated with the {{site.data.keyword.backup_notm}} director location information. For example, `ev-director301.service.softlayer.com` has the IP address 10.1.114.46 and is located in WDC.
  4. In the credentials field, enter the account ID, the {{site.data.keyword.backup_notm}} user name for the selected vault, and the password for the selected vault.
  5. Click **Save Changes**.

In a few seconds, the new vault is usable. If you get a connection failure, check your settings, and try again. Keep in mind that adding an extra vault presents you with an extra destination to choose for a job. It doesn't automatically run jobs against both vaults. You need to set up jobs to use the extra vault. For more information, see the [Getting Started Tutorial](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).

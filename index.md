---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Provisioning {{site.data.keyword.backup_notm}}
{: #ordering}

You can purchase {{site.data.keyword.backup_notm}} service in two ways.

- [Purchase backups when you Order a Server](#purchasingwithserver).
- [Purchase backups as an Upgrade](#purchasingasupgrade).

For more information about pricing, see [{{site.data.keyword.backup_notm}} storage ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/backup-and-restore){:new_window} and [{{site.data.keyword.backup_notm}} on IBM Cloud ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/backup/pricing){:new_window}.

## Purchasing {{site.data.keyword.backup_notm}} when you order a server
{: #purchasingwithserver}

1. Log in to the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/catalog){:new_window} or the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}
2. Order a monthly bare metal server. For more information about ordering bare metal servers, see [Building a custom Bare Metal Servers](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Select quantity, billing option. Enter host and domain names. You can choose any host name and domain that you like.

      {{site.data.keyword.backup_notm}} service isn't available when you're ordering an hourly billed server. However, the service can be added later as an upgrade.
      {:tip}
   2. Select location.
   3. Select Server configuration and OS Image type. You can also choose multiple add-ons.
   4. Under the **Storage Disks** section, click **Add-ons** and select **{{site.data.keyword.backup_notm}}**. Choose the option that matches what you need.
   5. Under **Network Interface**, select the Uplink Port Speed and any add-ons that you want.
3. On the right, review your order summary.
4. After you reviewed the terms and conditions, check the **I have read and agree to the Third-Party Service Agreements** box.
5. Click **Provision**. You are redirected to a screen with your provisioning order number. You can print the screen because it's also your provisioning order receipt.

   You can also save this order without purchasing by clicking **Save as Quote**.
   {:tip}

A series of emails is sent to your administrator: Acknowledgment of the provisioning order, Provisioning order approval and processing, and Provisioning complete. The Provisioning complete email includes a link to your *Device Details* page, that you can access after you log in to {{site.data.keyword.cloud_notm}}. You can also log directly in to the {{site.data.keyword.slportal}}.

### Confirming the {{site.data.keyword.backup_notm}} purchase
1. In the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/){:new_window}, click the **menu** icon on the upper left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Device** > **Device List**.
2. Locate the new server that you ordered.
  - If you see a clock icon next to the url, you need to wait to continue with the {{site.data.keyword.backup_notm}} purchase confirmation. You can refresh the page to see an updated status on your new server. When the clock icon is no longer present, you can proceed with the next steps to confirm the {{site.data.keyword.backup_notm}} service purchase.
  - When the clock icon is no longer showing for your server, click the link (the server's url) to go to the **Device Details** page.
3. Click the **Storage** tab to display the {{site.data.keyword.backup_notm}} information.
4. Inspect the {{site.data.keyword.backup_notm}} section, and verify that the size that was selected during the purchase process is displayed.

## Purchasing {{site.data.keyword.backup_notm}} as an upgrade
{: #purchasingasupgrade}

### Select a server on which to install {{site.data.keyword.backup_notm}}

1. Log in to the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Select **Devices** > **Device List** from the main menu. Find the device for which you want to add the backup service.
3. Click the Device name to go to the **Device Details** page.

### Adding (purchasing) {{site.data.keyword.backup_notm}} service
1. Click the **Storage** tab, and scroll down to locate the {{site.data.keyword.backup_notm}} section.
2. Click the **Add** link.
3. In the window, select a location, and select a size.
4. Select Payment type, and click **Continue**
5. Enter the **Promo Code** if you have one, and click **Recalculate**.
6. Review your order, and click the link to read the terms and conditions.
7. Click the check box if you agree with the terms and conditions.
7. Click **Place Order**.

### Confirming the {{site.data.keyword.backup_notm}} upgrade purchase
1. Refresh the **Device Details** page, and ensure that the **Storage** tab is selected.
2. Inspect the {{site.data.keyword.backup_notm}} section and verify that the size that was selected during the purchase process is displayed.

   If the backup storage size continues to show a capacity of zero, a second page refresh might be needed.
   {:tip}

When you're ready, go ahead and install the software agent on the server and set up your backup schedule in the {{site.data.keyword.backup_notm}} portal. For more information, see [Getting started tutorial](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started).

---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Learn about the Bare Metal Restore plug-in
{: #BMRplugin}

Bare Metal Restore is a disaster recovery solution. You can use BMR to restore your server from a bare metal state after a disaster, such as an operating system or hardware failure, occurred. With BMR, you can quickly restore the system image from a safe, secure location that is managed by {{site.data.keyword.cloud}}.

BMR is a Microsoft Windows only product on physical servers. It is not available for virtual servers. Bare Metal Restores for Linux distributions aren't supported. BMR is only supported by Backup Agent 8.30 or earlier versions. (30 June 2018).
{:important}

## Capabilities provided
{: #BMRcapabilities}

- Restore your system to a select point-in-time.
- Restore your system from image or file-based backups.
- Restore your system from backups that are stored on the {{site.data.keyword.backup_notm}}.
- Start a recovery transaction that you can use to restore your data without a bootable system.

## Installing the BMR plug-in
{: #installingBMR}

The plug-in is installed during the Windows Agent installation. The plug-in can be installed at the same time as the Agent or it can be installed later, by rerunning the installation with the **Modify** selection.

## Configuring BMR backup job
{: #configBMRplugin}

For more information, see [Configuring BMR backup jobs](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## Restoring a BMR system volume image
{: #restoringBMimage}
For more information, see [Restoring a BMR system volume image](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Downloading the user guide
{: #BMRUserGuide}

Connect to the {{site.data.keyword.cloud}} network with {{site.data.keyword.BluVPN}} so that you can access and download the user guide from the [Downloadable {{site.data.keyword.backup_notm}} Documentation](http://downloads.service.softlayer.com/evault/Documentation/){: external}

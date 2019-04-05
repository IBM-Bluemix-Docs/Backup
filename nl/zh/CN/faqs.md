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


# 常见问题
{: #faqs}

## 可以备份哪类应用程序？
{: faq}

{{site.data.keyword.backup_full}} 可用于对各种应用程序进行备份。{{site.data.keyword.BluSoftlayer_full}} 还为一些已备份的较常见的软件系统提供软件代理程序，其中包括

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

此处列出的插件仅与 Windows 服务器兼容，但 Oracle 或 VMware 插件除外。每个代理程序都作为备份服务的附加组件免费提供。

<hr>

## 备份数据的频率如何？
{: faq}

在 {{site.data.keyword.backup_notm}} 门户网站中，可以手动进行备份，也可以将备份安排为单个实例备份或周期性备份。周期性备份可以每天、每周、每月或按定制安排执行，并且可以随时更新或取消。

每天或每小时多次运行的高频率备份可能会导致备份作业损坏。发生损坏的原因是备份保险库运行所需后台维护任务的时间不足。备份作业优先于维护任务。因此，以高频率完成备份后，保险库会继续运行备份作业，导致了安全集数量的不断增加。
{:note}

<hr>

## 保留方案如何工作？
{: faq}

{{site.data.keyword.backup_notm}} 支持保留数据，具体保留时间取决于您希望回滚多长时间。**每日**保留方案会将数据保留 7 天，**每周**方案将数据保留 1 个月，**每月**方案将数据保留 1 年。在每个周期结束时，最旧的数据集会被淘汰，所执行的第一个“增量备份”会变成最旧的可用复原点。

您可以修改缺省保留方案，也可以创建定制保留方案。但是，IBM 建议使用缺省保留作为起始点。创建新的保留方案或修改现有保留时，确保未选中“归档”选项。不支持归档。
{:tip}

<hr>

## 什么是增量技术？
{: faq}

第一个备份是“种子”（完整的完全备份），接下来的后续备份是“增量”（即，仅备份更改），但增量备份等效于且仍被视为“完全备份”。也就是说，您可以从增量备份复原全部或任意文件。利用此技术，每个会话都会创建“完全备份”，但可节省保险库中的大量空间，并缩短完成每个后续备份所需的时间量。

<hr>

## 备份安全吗？
{: faq}

缺省情况下，所有线上 (OTW) 加密都使用 AES 256 位加密进行加密。您还可以选择使用 AES 256 位的加密格式存储数据。

您必须记住加密密码。没有密码就无法复原数据。如果丢失了密码，将无法恢复数据。
{:important}

压缩比率支持执行零压缩到最大比率压缩；根据文件类型，最大比率压缩可实现 20% 到 30% 范围内的任意压缩比率。


<hr>

## 系统状态备份中存储哪些信息？
{: faq}

系统状态备份包括但不限于 COM + 类注册数据库、注册表、引导文件、系统文件和性能计数器。这完全取决于您的系统。系统文件因系统操作系统和 service pack 而有所不同。通常有数千个系统文件。在备份中包含这些 DLL 时，MS Windows 将生成这些 DLL 的动态列表。通过包含系统文件，可以从损坏的系统文件中恢复，也适用于意外卸载了某些 service pack，或希望通过裸机复原进行恢复的情况。可以恢复到备份状态，而不必从安装工具包重新安装操作系统，然后分别安装每个 service pack。

系统状态备份中不包含用户数据文件。必须将系统状态备份作业配置为独立作业。“系统状态”备份作业中不能包含其他任何数据源
{:important}

<hr>

## 开放文件有什么变化？
{: faq}

缺省情况下，基本客户机采用最先进的技术来处理操作系统上运行的大多数开放文件。

<hr>

## 何处可找到有关定价的信息？
{: faq}

有关更多信息，请参阅 [Backup storage ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [EVault on IBM Cloud: Pricing ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/backup/pricing){:new_window}。

<hr>

## 是否可以在不影响备份的情况下增大或减小 {{site.data.keyword.backup_notm}} 容量？
{: faq}

可以通过 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window} 来增大或减小保险库的大小。对容量的修改不会影响保险库中存储的数据的完整性。有关更多信息，请参阅[扩展容量](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity)。

<hr>

## 超过了 {{site.data.keyword.backup_notm}} 容量时会发生什么情况？
{: faq}

即使已达到您先前购买的容量的限制，也仍可保存和检索备份。但是，您将对在接下来的计费结算表中使用的每个额外的 GB 支付额外的费用。

<hr>

## 如何在 {{site.data.keyword.backup_notm}} 门户网站中设置通知，以便了解我的备份是否失败？
{: faq}

可以在“高级”选项卡上设置通知。请按照在 {{site.data.keyword.backup_notm}} 门户网站中的**快速链接**中找到的指示信息执行操作。

<hr>

## 在使用 BMR 插件时，我们可以从单个磁盘迁移到 RAID 阵列吗？

可以，支持此迁移。但是，由于 RAID 阵列会导致容量大小减少，因此需要选择大容量设备。

<hr>

## 在使用 BMR 插件时，将映像复原到比原始卷更大的磁盘会出现什么情况？
{: faq}

如果将映像复原到比原始卷更大的磁盘，那么会释放剩余的空间。例如，如果您有一个 500-GB 驱动器，并将其数据复原到 1-TB 磁盘，那么将释放 500 GB 的磁盘空间。对于 Windows 2008，可以使用内置磁盘实用程序来增大主分区。但是，在 Windows 2003 中没有类似的内置功能，因此您必须以另一种方式分配空间。

<hr>

## 可以将 BMR 用于定期备份吗？
{: faq}

BMR 备份不是磁盘映像备份系统，而是系统卷映像备份系统。此系统的目的不是用于定期备份，但是可以与定期备份一起使用。  

<hr>

##可以将 BMR 用于数据库备份吗？
{: faq}

数据库备份必须与标准 {{site.data.keyword.backup_notm}} 备份方法分开执行。BMR 并不能取代对 SQL 或 Oracle 插件的需求。尽管 BMR 使用 VSS 技术来备份开放文件，但不一定能保证备份的文件保持事务一致性。针对这些类型的专用应用程序的建议是创建两个备份作业：一个用于备份操作系统和应用程序二进制文件，另一个用于备份应用程序数据。

<hr>

## 可以使用 BMR 运行哪种复原作业？

可以执行整个系统复原，也可以从备份中选择个别文件进行复原。BMR 备份作业可以替换当前文件备份作业。复原过程可以在操作系统内部完成，就像传统的备份作业一样。

<hr>

## BMR 具有开放文件文件备份功能吗？
{: faq}

BMR 具有开放文件备份功能。但是，BMR 并不能取代对 SQL 或 Oracle 插件的需求。单击[此处](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin)以获取 MSSQL 插件安装指示信息。

<hr>

## BMR 复原需要多大磁盘空间和多长时间？
{: faq}

通过缺省安装进行备份大约使用 6 GB。此类复原在 1-GB 端口上大约需要 15 分钟。此过程还受专用端口速度的影响。如果需要更快的备份和复原，可能需要提高端口速度。

<hr>

## VSS（卷影复制服务）是用来做什么的？
{: faq}

当前版本的 SQL Server 插件使用 VSS（卷影复制服务）来完成备份。通过使用 VSS，SQL Server 插件可有效备份 SQL 数据库，甚至支持备份跨卷的 SQL 数据库。备份期间，应用程序可继续写入卷。SQL Server 插件在数据库内和数据库之间提供数据一致性。VSS 允许多个备份同时运行。

<hr>

## 用于 Windows 8 的 32 位版本 EVault 是否仍受支持？
{: faq}

否。32 位版本的备份软件代理程序已于 2017 年 3 月随 Windows Server 2008 Standard Edition 和 Datacenter Edition 一起引退。

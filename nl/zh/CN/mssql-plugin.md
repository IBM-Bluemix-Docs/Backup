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

# 安装 SQL Server 插件
{: #MSSQLplugin}

SQL Server 插件随 Windows 代理程序一起安装在 SQL 数据库主机上。通过 {{site.data.keyword.backup_notm}} 门户网站，可以配置作业，将 SQL 数据库备份到安全的远程保险库，以及复原 SQL 数据库。

**提供的功能**

- 可以运行完整数据库备份、含事务日志的完整数据库备份或者仅限事务日志的备份。
- 可以同时运行多个备份。
- 可以将 SQL 数据库复原到同一个 SQL 实例，也可以复原到其他 SQL 实例。
- 可以使用原始数据库名称复原数据库，覆盖现有数据库，以及使用“不恢复”选项进行复原。

有关更多信息，请参阅[主要功能](#main-featues)部分。

## 订购插件
{: #orderingSQLPlugin}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择帐户，然后单击**订购插件**。
4. 选择 **{{site.data.keyword.backup_notm}} 插件 - MSSQL**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中此框以指示您已阅读并接受第三方服务协议。
8. 单击**下订单**。

## 安装 MSSQL 插件
{: #installSQLPlugin}

要安装插件，请运行代理程序安装工具包。该插件在**定制安装**页面上显示为选项。

在为 Microsoft Windows 服务器安装 MSSQL 插件之前，请在 `services.msc` 中停止两个 {{site.data.keyword.backup_notm}} 服务。
{:tip}

1. 浏览至 `c:\installs\evault` 文件夹，然后运行具有更高修订版号的 .exe 文件。
2. 在语言屏幕上，单击**确定**。
3. 在欢迎屏幕上，单击**下一步**。
4. 选择**修改安装**，然后单击**下一步**。
5. 选择**保留不变**，然后单击**下一步**。
6. 在定制安装屏幕上，选择已购买的每个插件。
7. 选择**此功能部件将安装在...**，然后单击**下一步**。
8. 选择**保留我当前的注册**，然后单击**下一步**。
9. 单击**安装**。
10. 安装后，请进行检查以确保这两个服务都已启用并且正在运行。
11. 如果 {{site.data.keyword.backup_notm}} 门户网站能够查看和访问数据库，说明安装成功。

## 下载用户指南
{: #SQLUserGuide}

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} 中下载用户指南。

## 主要功能
{: #main-features}

- 能够使用通配符（星号和问号）指定要在 SQL Server 备份作业中包含和排除的数据库的名称。作业运行时，将自动包括或排除名称与备份作业过滤器相匹配的新数据库。
- 能够使用 64 位代理程序和 SQL Server 插件来保护“AlwaysOn 可用性组”中的辅助数据库。
- 能够共享包含 SharePoint 2010/2013 内容数据库的 SQL 安全集，以用于 Granular Restore for Microsoft SharePoint 应用程序。共享安全集后，可使用 Granular Restore 应用程序来复原站点集合、Web 站点、列表、库、文件夹、列表项或文档。
- 支持对跨卷上的数据库进行增量友好型备份。
- 能够使用单个安排条目以完全恢复模型来保护数据库。此选项允许保护数据库和管理单个安排条目中事务日志的截断。
- SQL Server 插件支持“完整”备份、“完整（含事务日志）”备份和“事务日志”备份（更新后的术语与 SQL Server 术语保持一致）。该应用程序继续支持“一次过复原”功能，该功能支持客户选择时间点“事务日志”备份。{{site.data.keyword.backup_notm}} 将复原完整数据库以及将数据库复原到所选时间点所需的所有事务日志。
- 备份作业可以包含同一个 SQL Server 实例中的一个或多个数据库。可以创建单独的作业，从可以根据需要同时运行的其他 SQL Server 实例备份其他数据库。
- 能够使用“不恢复”来复原数据库，以通过 SQL Server Management Studio 提供更多恢复选项。
- 备用复原选项支持复原到文件，这允许数据库管理者通过 SQL System Manager 安装数据库。
- 备用复原包含将一个数据库的复原定向到另一个数据库的功能，即便逻辑数据库名称不匹配也可执行。对于不匹配的对象，该插件将在实例的缺省数据库位置中创建数据库。
- 64 位 SQL Server 2008 R2 (SP1) 和 SQL Server 2012 上支持透明数据加密 (TDE)。
- 如果 SQL Server 主机丢失，那么可以安装 SQL Server 软件，然后可以复原数据库。（必须先复原主数据库。）
- 启动备份后，即会执行备份，不管数据库服务是否在运行。
- 支持复原到原始数据库名称（覆盖或不覆盖现有数据库）、覆盖性复原现有数据库或复原到磁盘上的文件。

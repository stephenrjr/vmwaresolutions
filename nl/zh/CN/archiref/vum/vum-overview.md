---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

# VMware Update Manager 概述
{: #vum-overview}

VMware Update Manager (VUM) 使用多阶段过程来升级 vSphere 对象以及应用补丁或扩展。通过此过程，能以最少的系统停机时间顺利更新。在查看此过程之前，需要先了解以下术语：
* **库存对象** - vCenter 中的对象，例如虚拟机、虚拟设备或 vSphere ESXi 主机。
* **基线** - 基线包含由一个或多个补丁、扩展、Service Pack、错误修订或升级构成的集合，可以分类为补丁、扩展或升级基线。基线分为两类：主机和 VM/VA；这两类都包含 VMware 提供的预定义基线，也都可以根据需要添加定制基线：
  - 预定义的主机基线：
    - 关键主机补丁
    - 非关键主机补丁

  - 预定义的 VM/VA 基线：
    - VA 升级到最新版本
    - VM 硬件升级以匹配主机
    - VMware Tools 升级以匹配主机

* **基线组** - 一组无冲突的基线，其中组合了不同类型的基线，所有这些基线会作为整体，并根据这些基线来扫描和修复库存对象。如果基线组包含升级和补丁或扩展基线，那么将首先运行升级。
* **扫描** - 扫描是根据基准或基准组来评估库存对象的过程。
* **编译打包** - 编译打包可确保在修复之前将补丁和扩展下载到 vSphere ESXi 主机，这是可选步骤，但可最大程度地缩短主机处于维护模式的时间。
* **修复** - 修复是 VUM 对库存对象应用补丁、扩展和升级的过程。

因此，VUM 过程如下所示：
* 根据基线或基线组扫描一个库存对象或对象组以确定一致性。
* 复查后，可以选择在修复前对补丁和扩展进行编译打包。

下载升级、主机补丁、扩展和相关元数据是预定义的自动过程，可对其进行修改。缺省情况下，根据可配置的定期时间间隔，VUM 会与 VMware 或第三方来源联系，以收集有关可用升级、补丁或扩展的以下信息：

* 有关所有 ESXi 5.5 和 ESXi 6.x 补丁的元数据，无论是否在您的环境中有此类版本的主机。
* 有关 ESXi 5.5 和 ESXi 6.x 补丁的元数据以及有关来自第三方供应商 URL 地址的扩展的元数据。
* 针对 ESXi 5.5 和 ESXi 6.x 主机的通知、警报和补丁召回。
* 有关虚拟设备升级的元数据。

VUM 支持召回用于在运行 ESXi 5.0 或更高版本的主机的补丁。如果发布的补丁存在问题或潜在问题，那么将召回该补丁。扫描 VMware vCenter Server on {{site.data.keyword.cloud}} 实例中的主机后，如果在特定主机上已安装召回的补丁，VUM 将向您发出警报。不能在使用 VUM 的主机上安装召回的补丁。VUM 还会从补丁存储库中删除所有召回的补丁。在发布了解决问题的补丁后，VUM 会将新补丁下载到其补丁存储库。如果您已安装有问题的补丁，VUM 将通知您已发布修订，并提示您应用新补丁。

VUM 客户机界面提供了两个主视图：
*	管理视图
*	一致性视图

##	管理视图
{: #vum-overview-admin-view}

“管理”视图可通过导航至**主页** > **Update Manager**，然后选择 Update Manager 实例的 IP 地址进行访问。在“管理”视图中，可以执行以下任务：
*	配置 Update Manager 设置
*	创建和管理基线与基线组
*	查看 Update Manager 事件
*	查看补丁存储库和可用的虚拟设备升级
*	查看和检查通知
*	导入 ESXi 映像

##	一致性视图
{: #vum-overview-compliance-view}

所选库存对象的“一致性”视图可通过导航至**主机和集群**或 **VM 和模板**，然后单击 **Update Manager** 选项卡进行访问。在 Update Manager 的“一致性”视图中，可以执行以下任务：
*	查看每个所选库存对象的一致性和扫描结果
*	将基线和基线组连接到所选库存对象，以及从所选库存对象拆离基线和基线组
*	扫描所选库存对象
*	将补丁或扩展编译打包到主机
*	修复所选库存对象

## 相关链接
{: #vum-overview-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} 解决方案体系结构](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} 数字技术互动](https://ibm-dte.mybluemix.net/vmware)（演示）

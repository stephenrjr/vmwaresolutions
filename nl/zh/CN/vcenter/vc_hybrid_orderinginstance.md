---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 订购 vCenter Server with Hybridity Bundle 实例
{: #vc_hybrid_orderinginstance}

要部署灵活且可定制的 VMware 虚拟化平台，以最适合您的工作负载需求，请订购 VMware vCenter Server on {{site.data.keyword.cloud}} with Hybridity Bundle 实例。vCenter Server with Hybridity Bundle 实例订单中包含 VMware Hybrid Cloud Extension (HCX) 许可，并授权您使用 VMware HCX on {{site.data.keyword.cloud_notm}} 服务。您还可以添加服务，例如用于灾难恢复的 [Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)。

## 订购 vCenter Server with Hybridity Bundle 实例的需求
{: #vc_hybrid_orderinginstance-req}

确保已完成以下任务：
*  已在**设置**页面上配置 {{site.data.keyword.cloud_notm}} 基础架构凭证。有关更多信息，请参阅[管理用户帐户和设置](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)。
*  已查看[针对 vCenter Server with Hybridity Bundle 的需求和规划](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_planning)中的信息。
* 已复查实例和域名格式。域名和子域标签用于生成实例的用户名和服务器名称。

表 1. 实例和域名的值格式

|名称|值格式|
  |:------------- |:------------- |
  |域名| `<root_domain>` |  
  |vCenter Server 登录用户名|`<user_id>@<root_domain>`（Microsoft Active Directory 用户）或 `administrator@vsphere.local`|
  | vCenter Server（具有嵌入式 PSC）FQDN|`vcenter-<subdomain_label>.<subdomain_label>.<root_domain>`。最大长度为 50 个字符。|
  |Single Sign-On (SSO) 站点名称| `<subdomain_label>` |
  |标准 ESXi 服务器名称| `<host_prefix><n>.<subdomain_label>.<root_domain>`，其中 `<n>` 是 ESXi 服务器的序列。最大长度为 50 个字符。|

不要修改在实例订购或部署期间设置的任何值。这样做可能会使您的实例不可用。例如，如果公用网络关闭，如果服务器和虚拟服务器实例 (VSI) 在供应期间移至 Vyatta 后，或者如果 IBM CloudBuilder VSI 停止或被删除。
{:important}

## 系统设置
{: #vc_hybrid_orderinginstance-sys-settings}

订购 vCenter Server with Hybridity Bundle 实例时，必须指定以下系统设置。

### 实例名称
{: #vc_hybrid_orderinginstance-inst-name}

实例名称必须满足以下需求：
* 只允许使用字母数字字符和短划线 (-) 字符。
* 实例名称必须以字母字符开头并以字母数字字符结尾。
* 实例名称的最大长度为 10 个字符。
* 实例名称在您的帐户中必须唯一。

### VMware vSphere 许可证
{: #vc_hybrid_orderinginstance-vsphere-license}

选择是订购 vSphere Enterprise Plus 6.7u1 还是订购 vSphere Enterprise Plus 6.5u2。

vSphere Enterprise Plus 6.7u1 仅可用于 Broadwell 和 Skylake {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}。
{:note}

### 主实例或辅助实例
{: #vc_hybrid_orderinginstance-primary-secondary}

选择是订购新的主实例还是为现有主实例订购辅助实例。

## 许可证设置
{: #vc_hybrid_orderinginstance-licensing-settings}

vCenter Server with Hybridity Bundle 实例订单中包含以下 VMware 许可证。您必须指定 NSX 和 vSAN 许可证的版本。

* vCenter Server 6.5
* vSphere Enterprise Plus 6.5 或 6.7
* NSX Service Providers 6.4（Advanced Edition 或 Enterprise Edition）
* vSAN 6.6（Advanced Edition 或 Enterprise Edition）

### 注意
{: #vc_hybrid_orderinginstance-attention}

* vCenter Server with Hybridity Bundle 实例不支持自带许可证。
* 用户界面上指示了最低许可证版本。如果支持不同的组件版本，那么可以选择所需的版本。

## 裸机服务器设置
{: #vc_hybrid_orderinginstance-bare-metal-settings}

裸机设置基于您选择的 {{site.data.keyword.CloudDataCent_notm}} 以及裸机服务器配置。

对于 vSAN 配置，初始集群和部署后集群都需要 4 个 ESXi 服务器。所有 ESXi 服务器共享相同的配置。部署后，可以再添加四个集群。

### 数据中心位置
{: #vc_hybrid_orderinginstance-dc-location}

选择要托管实例的 {{site.data.keyword.CloudDataCent_notm}}。

### Skylake
{: #vc_hybrid_orderinginstance-skylake}

选择 **Skylake** 时，可以根据需要为裸机服务器选择 CPU 和 RAM 组合。

表 2. Skylake {{site.data.keyword.baremetal_short}} 的选项

| CPU 模型选项   |RAM 选项|
|:------------- |:------------- |
|双 Intel Xeon Silver 4110 处理器 / 共 16 个核心，2.1 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 5120 处理器 / 共 28 个核心，2.2 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|

### Broadwell
{: #vc_hybrid_orderinginstance-broadwell}

选择 **Broadwell** 时，可以根据需要为裸机服务器选择 CPU 和 RAM 组合。

表 3. Broadwell {{site.data.keyword.baremetal_short}} 的选项

| CPU 模型选项   |RAM 选项|
|:------------- |:------------- |
|四核 Intel Xeon E7-4820 V4 / 共 40 个核心，2.0 GHz|128 GB、256 GB、512 GB、1 TB、2 TB、3 TB|
|四核 Intel Xeon E7-4850 V4 / 共 64 个核心，2.1 GHz|128 GB、256 GB、512 GB、1 TB、2 TB、3 TB|

### 裸机服务器的数量
{: #vc_hybrid_orderinginstance-bare-metal-number}

* 订购的所有服务器的配置都相同。
* 可以订购 4 到 20 个服务器。

## 存储设置
{: #vc_hybrid_orderinginstance-storage-settings}

vCenter Server with Hybridity Bundle 实例订单中包含 VMware vSAN 6.6。请指定以下 vSAN 选项：
* **vSAN 容量磁盘的磁盘类型和大小**：选择与所需容量磁盘相应的选项。
* **vSAN 容量磁盘数**：指定要添加的容量磁盘数。
* 如果要添加的容量磁盘数超过 10 个的限制，请选中**高性能 Intel Optane** 框。此选项用于提供两个额外的容量磁盘托架，总共可容纳 12 个容量磁盘；此选项对于需要更短等待时间和更高 IOPS 吞吐量的工作负载而言非常有用。

  **高性能 Intel Optane** 选项仅可用于 Skylake CPU 型号。
{:note}

* 查看 **vSAN 高速缓存磁盘的磁盘类型**和 **vSAN 高速缓存磁盘数**值。这些值依赖于是否选中了**高性能 Intel Optane** 框。

## 网络接口设置
{: #vc_hybrid_orderinginstance-network-interface-settings}

订购 vCenter Server with Hybridity Bundle 实例时，必须指定以下网络接口设置。

### 主机名前缀
{: #vc_hybrid_orderinginstance-host-name-prefix}

  主机名前缀必须满足以下需求：
  *  只允许使用字母数字字符和短划线 (-) 字符。
  *  主机名前缀必须以字母数字字符开头和结尾。
  *  主机名前缀的最大长度为 10 个字符。

### 子域标签
{: #vc_hybrid_orderinginstance-subdomain-label}

子域标签必须满足以下需求：
*  只允许使用字母数字字符和短划线 (-) 字符。
*  子域标签必须以字母字符开头并以字母数字字符结尾。
*  子域标签的最大长度为 10 个字符。
*  子域标签在您的帐户中必须唯一。

### 域名
{: #vc_hybrid_orderinginstance-domain-name}

根域名必须满足以下需求：
* 域名必须包含两个或更多用句点 (.) 分隔的字符串。
* 第一个字符串必须以字母字符开头并以字母数字字符结尾。
* 除了最后一个字符串外，其他所有字符串都只能包含字母数字和短划线 (-) 字符。
* 最后一个字符串只能包含字母字符。
* 最后一个字符串的长度必须在 2 到 24 个字符范围内。

主机和 VM（虚拟机）的 FQDN（标准域名）的最大长度为 50 个字符。域名必须符合此最大长度。
{:note}

### 公用或专用网络
{: #vc_hybrid_orderinginstance-public-private-network}

网络接口卡 (NIC) 启用设置基于您选择的是**公用和专用网络**还是**仅专用网络**。

如果选择**仅专用网络**选项：
* 未供应 VMware NSX Edge 服务网关 (ESG)（包括管理服务 ESG 和客户管理的 ESG）。
* 以下附加组件服务（需要公共 NIC）不可用：
  * F5 on {{site.data.keyword.cloud_notm}}
  * Fortigate Security Appliance on {{site.data.keyword.cloud_notm}}
  * Fortigate Virtual Appliance on {{site.data.keyword.cloud_notm}}

### 订购新的 VLAN
{: #vc_hybrid_orderinginstance-new-vlans}

选择**订购新的 VLAN** 可订购一个新的公用 VLAN 和两个新的专用 VLAN。

订购实例时，需要包含一个公用 VLAN 和两个专用 VLAN。两个专用 VLAN 用于中继到每个裸机服务器中。

### 选择现有 VLAN
{: #vc_hybrid_orderinginstance-existing-vlans}

根据选择的 {{site.data.keyword.CloudDataCent_notm}}，可能会有现有公用和专用 VLAN 可用。

订购实例时，需要包含一个公用 VLAN 和两个专用 VLAN。两个专用 VLAN 用于中继到每个裸机服务器中。

选择**选择现有 VLAN** 可复用现有公用 VLAN 和专用 VLAN，并可从可用的 VLAN 和子网中进行选择。

* 确保所选 VLAN 上的防火墙配置不会阻止管理数据流量。
* 确保选择的所有 VLAN 都在同一 pod 中，因为 ESXi 服务器不能在混合 pod VLAN 上进行供应。
{:important}

### DNS 配置
{: #vc_hybrid_orderinginstance-dns-config}

为实例选择域名系统 (DNS) 配置：

* **一个用于 Active Directory/DNS 的公共 Windows VSI**：一个用于 Microsoft Active Directory (AD) 的 Microsoft Windows Server VSI，充当在其中注册主机和 VM 的实例的 DNS，已部署并且可进行查找。
* **管理集群上两个高可用性专用 Windows Server VM**：部署了两个 Microsoft Windows 虚拟机，以帮助增强安全性和稳健性。

如果将实例配置为使用两个 Microsoft Windows VM，那么必须提供两个 Microsoft Windows Server 2016 许可证。使用 Microsoft Windows Server 2016 Standard Edition 许可证和/或 Microsoft Windows Server 2016 Datacenter Edition 许可证。
{:important}

每个许可证只能分配给一个物理服务器，并且最多包含两个物理处理器。一个 Standard Edition 许可证支持每个双处理器服务器运行两个虚拟化的 Microsoft Windows VM。因此，需要两个许可证，因为两个 Microsoft Windows VM 会部署在两个不同的主机中。

您有 30 天的时间来激活 VM。

有关订购 Windows Server 2016 许可证的更多信息，请参阅 [Windows Server 2016 入门](https://docs.microsoft.com/en-us/windows-server/get-started/server-basics){:new_window}。

## 服务设置
{: #vc_hybrid_orderinginstance-addon-services}

订购 vCenter Server with Hybridity Bundle 实例时，还可以订购其他服务。有关服务的更多信息，请参阅 [vCenter Server with Hybridity Bundle 实例的可用服务](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices#available-services-for-vcenter-server-with-hybridity-bundle-instances)。

## 订单摘要
{: #vc_hybrid_orderinginstance-order-summary}

根据为实例和附加组件服务选择的配置，估算成本会立即生成并显示在右侧窗格的**订单摘要**部分中。单击右侧窗格底部的**定价详细信息**可生成提供估算详细信息的 PDF 文档。

## 订购 vCenter Server with Hybridity Bundle 实例的过程
{: #vc_hybrid_orderinginstance-procedure}

1. 在 {{site.data.keyword.cloud_notm}}“目录”中，单击左侧导航窗格中的 **VMware**，然后单击**虚拟数据中心**部分中的 **vCenter Server**。
2. 在 **VMware vCenter Server on IBM Cloud** 页面上，单击 **vCenter Server with Hybridity Bundle** 卡，然后单击**创建**。
3. 在 **vCenter Server** 页面上，输入实例名称。
5. 选择 vSphere 版本。
4. 选择实例类型：
   * 单击**主实例**以在环境中部署单个实例，或者在多站点拓扑中部署第一个实例。
   * 单击**辅助实例**以将该实例与环境中的现有（主）实例连接以获取高可用性，并完成以下步骤：
     1. 选择要与辅助实例连接的主实例。
     2. 对于主实例 V2.8 或更高版本，请输入主实例的 vCenter Server 管理员密码。
     3. 对于主实例 V2.7 或更低版本，请输入主实例的 PSC 管理员密码。
6. 选择 NSX 许可证版本和 vSAN 许可证版本。
7. 完成裸机服务器设置。
  1. 选择要托管实例的 {{site.data.keyword.CloudDataCent_notm}}。
  2. 选择 **Skylake** 或 **Broadwell** CPU 型号以及 **RAM** 量。
8. 填写存储配置。指定容量和高速缓存磁盘的磁盘类型以及磁盘数。如果需要更多存储器，请选中**高性能 Intel Optane** 框。
9. 完成网络接口配置。
  1. 输入要供应的实例的主机名前缀、子域标签和根域名。
  2. 选择网络设置**公用和专用网络**或**仅专用网络**。
  3. 选择 VLAN 配置。
     *  如果要订购新的公用和专用 VLAN，请单击**订购新的 VLAN**。
     *  如果要复用可用的现有公用和专用 VLAN，请单击**选择现有 VLAN**，然后选择公用 VLAN、主子网、专用 VLAN、专用主子网和辅助专用 VLAN。
  4. 选择 DNS 配置。
10. 完成对包含的 HCX on {{site.data.keyword.cloud_notm}} 服务的配置。有关如何为该服务提供设置的更多信息，请参阅[订购 VMware HCX on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_ordering#vmware-hcx-on-ibm-cloud-configuration) 中的 _VMware HCX on IBM Cloud 配置_部分。
11. 通过单击相应的服务卡，选择要部署到实例中的附加组件服务。如果服务需要配置，请完成特定于服务的设置，然后单击相应卡上的**添加服务**。  
有关如何为服务提供设置的更多信息，请参阅相应的服务订购主题。

12. 在**订单摘要**窗格上，验证实例配置，然后再下订单。
   1. 复查实例的设置。
   2. 复查实例的估算成本。单击**定价详细信息**以生成 PDF 摘要。要保存或打印订单摘要，请单击 PDF 窗口右上角的**打印**或**下载**图标。
   3. 单击订单适用条款的链接，并在订购实例之前确认您同意这些条款。
   4. 单击**供应**。

## 结果
{: #vc_hybrid_orderinginstance-results}

实例部署会自动启动。您将收到说明订单正在处理的确认，并且您可以通过查看实例详细信息来检查部署的状态。

成功部署实例后，[vCenter Server with Hybridity Bundle 实例的技术规范](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_overview#specs)中描述的组件已安装在 VMware 虚拟平台上。缺省情况下，订购的 ESXi 服务器将分组为 **cluster1**。如果订购了附加组件服务，那么这些服务的部署将在订单完成后启动。

实例准备就绪可供使用后，该实例的状态会更改为**可供使用**，并且您将收到通过电子邮件发送的通知。

订购辅助实例时，在完成辅助实例订单后，可能会重新启动主实例（链接到辅助实例）的 VMware vSphere Web Client。

## 后续步骤
{: #vc_hybrid_orderinginstance-next}

查看和管理订购的 vCenter Server with Hybridity Bundle 实例。

您只能在 {{site.data.keyword.vmwaresolutions_short}} 控制台中管理在 {{site.data.keyword.cloud_notm}} 帐户中创建的 {{site.data.keyword.vmwaresolutions_short}} 组件，而不能在 {{site.data.keyword.slportal}} 中或在该控制台外部通过其他任何方法对这些组件进行管理。如果在 {{site.data.keyword.vmwaresolutions_short}} 控制台外部更改这些组件，那么这些更改与控制台不同步。
{:important}

**注意**：在 {{site.data.keyword.vmwaresolutions_short}} 控制台外部管理任何 {{site.data.keyword.vmwaresolutions_short}} 组件（在订购实例时安装到 {{site.data.keyword.cloud_notm}} 帐户中）可能会使环境变得不稳定。这些管理活动包括：
*  添加、修改、返回或除去组件
*  通过添加或除去 ESXi 服务器来扩展或收缩实例容量
*  关闭组件电源
*  重新启动服务

   这些活动的例外情况包括在 {{site.data.keyword.slportal}} 中管理共享存储器文件共享。此类活动包括：订购、删除（如果已安装，可能会影响数据存储）、授权和安装共享存储器文件共享。

## 相关链接
{: #vc_hybrid_orderinginstance-related}

* [注册 {{site.data.keyword.cloud_notm}} 帐户](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [查看 vCenter Server with Hybridity Bundle 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_viewinginstances)
* [vCenter Server with Hybridity Bundle 实例的多站点配置](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_multisite)
* [添加和查看 vCenter Server with Hybridity Bundle 实例的集群](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingviewingclusters)
* [扩展和收缩 vCenter Server with Hybridity Bundle 实例的容量](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservers)
* [订购、查看和除去 vCenter Server with Hybridity Bundle 实例的服务](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices)
* [删除 vCenter Server with Hybridity Bundle 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_deletinginstance)

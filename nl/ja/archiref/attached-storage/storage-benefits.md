---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-13"

subcollection: vmware-solutions


---

# vCenter Server の接続ストレージについて
{: #storage-benefits}

接続ストレージは、VMware vCenter Server on {{site.data.keyword.cloud}} オファリングの拡張機能です。 VMware vCenter Server on {{site.data.keyword.cloud_notm}} の接続ストレージ・ソリューション・アーキテクチャーに、このソリューションの各コンポーネントと、設計での各コンポーネントの構成概要が詳しく示されます。

vCenter Server の設計について詳しくは、[ソリューションの概要](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_overview)を参照してください。

## vCenter Server の接続ストレージの主な利点
{: #storage-benefits-key-benefits}

接続ストレージは VMware 環境に必須のものではありませんが、共有ストレージ・デバイスとして使用すると、ユーザーの IT 運用に多くのメリットがあります。 共有ストレージ・デバイスを使用すると、次の表に示す vSphere 機能を有効にすることにより、高可用性、分散リソース・スケジューラー、効率的なストレージ容量の使用、簡素化された管理を実現できます。

表 1. vCenter Server の接続ストレージの機能説明

| 機能 | 説明 |
|:------- |:----------- |
| vSphere Distributed Resource Scheduler およびリソース・プール | この機能は、ロード・バランシングおよび仮想マシン (VM) の配置によってリソースの抽象化と柔軟な管理を可能にします。 リソース・プールは階層にグループ化され、使用可能な CPU とメモリー・リソースを階層的に分離するために使用されます。 |
| vSphere High Availability | この機能は、クラスターに存在する VM とホストの高可用性を (VM をプールすることで) 実現します。 クラスター内のホストはモニターされます。 障害が発生すると、障害が発生したホストの VM が別のホストで再起動されます。 |
| vSphere データ・ストア・クラスター | この機能は、データ・ストアの集合に対して、共有リソースと共有管理インターフェースを利用できるようにします。 |
| vSphere フォールト・トレランス | この機能は、停止時間や中断時間を無くして、完全なホスト障害が発生した場合でも、VM の継続的可用性を保証します。 |

## 関連リンク
{: #storage-benefits-related}

* [ソリューションの概要](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_overview)

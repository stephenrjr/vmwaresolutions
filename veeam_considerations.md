---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-02"

---

# Components and considerations for Veeam on IBM Cloud

The Veeam on IBM® Cloud service seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. This service can provide recovery points and time objectives of less than 15 minutes upon configuration for your applications and data. By using this service, you can directly control both the backup and restore of all virtual machines for your infrastructure from the Veeam console.

This service is available only to V1.8 and later instances.

You can order an instance with the Veeam on IBM Cloud service included. For more information, see:
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Veeam on IBM Cloud service into your existing instances after initial deployment. For more information, see:
* [Ordering and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

## Veeam on IBM Cloud components

The following components are ordered and included in the Veeam on IBM Cloud service:
* One Windows Server 2016 VSI with a primary private IP address and 1 GbE interface
* IBM Cloud Endurance block storage of the size and performance that you select when you order the service

## Considerations when installing Veeam on IBM Cloud

* The management components that are backed up by the Veeam on IBM Cloud service include the VMware vCenter Server, the Platform Services Controller (PSC), the IBM CloudDriver, and VMware SDDC Manager (applies to Cloud Foundation instances only).
* The configurations of the ESXi servers are not backed up by the Veeam on IBM Cloud service.
* By default, the configurations of the NSX Controller and the NSX Edge are backed up daily by using the NSX Manager with up to 14 points of restoration. For a full restore of the NSX configurations, you must create a Bluemix Support ticket, because the backups of the NSX configurations are saved on the storage that is internal to {{site.data.keyword.vmwaresolutions_full}}. For more information on managing the NSX configuration backups by using NSX Manager, see the [VMware technical instructions](https://pubs.vmware.com/NSX-6/index.jsp#com.vmware.nsx.admin.doc/GUID-72EFCAB1-0B10-4007-A44C-09D38CD960D3.html).
* The repository for the storage and the Veeam server are in the original pod and data center. Because of that, the performance of the backup operations for remote clusters might deteriorate.

## Considerations when removing Veeam on IBM Cloud

Before you remove the Veeam on IBM Cloud service, note that removal of this service will stop all backups (including the backup of the management VMs) and will delete all the previous backups (the deletion is irreversible). If the management VMs are corrupted subsequently, they cannot be restored.

## Related links

* [Managing Veeam on IBM Cloud](managingveeam.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
* [FAQ](../vmonic/faq.html)
* [Veeam website](https://www.veeam.com/){:new_window}
* [Veeam Help Center](https://www.veeam.com/documentation-guides-datasheets.html){:new_window}
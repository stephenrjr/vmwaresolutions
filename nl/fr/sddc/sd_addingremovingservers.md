---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Extension et réduction de capacité pour des instances Cloud Foundation
{: #sd_addingremovingservers}

Vous pouvez accroître ou réduire la capacité de votre instance VMware Cloud Foundation en fonction de vos besoins métier en ajoutant ou en supprimant des serveurs ESXi.

Une instance Cloud Foundation peut comporter jusqu'à cinq clusters, dont l'un est celui par défaut. Chaque cluster initial peut avoir jusqu'à 51 serveurs ESXi et les clusters supplémentaires jusqu'à 59 serveurs.

## Ajout de serveurs ESXi à des instances Cloud Foundation
{: #sd_addingremovingservers-adding}

### Avant d'ajouter des serveurs ESXi
{: #sd_addingremovingservers-adding-prereq}

* N'ajoutez pas de serveurs ESXi depuis le client Web VMware vSphere. Les modifications apportées sur le client Web VMware vSphere ne sont pas synchronisées avec la console {{site.data.keyword.vmwaresolutions_full}}.
* La plateforme de base que vous avez commandée dispose par défaut de 4 serveurs ESXi. Vous pouvez développer la plateforme jusqu'à un maximum de 32 serveurs ESXi. Cependant, le nombre de serveurs {{site.data.keyword.baremetal_short}} que vous pouvez ajouter à la fois est le suivant :
   * Pour les configurations **Petite** et **Grande**, vous pouvez ajouter de 1 à 10 serveurs ESXi à la fois.
   * Pour les configurations **Skylake** et **Broadwell**, vous pouvez ajouter 1 à 20 serveurs ESXi à la fois.

## Procédure d'ajout de serveurs ESXi
{: #sd_addingremovingservers-adding-procedure}

1. A partir de la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Ressources** dans le panneau de navigation de gauche.
2. Dans le tableau **Instances Cloud Foundation**, cliquez sur l'instance dont vous désirez accroître la capacité.
3. Cliquez sur **Infrastructure** dans le panneau de navigation de gauche.
4. Dans le tableau **CLUSTERS**, cliquez sur le cluster auquel vous désirez ajouter des serveurs ESXi.
5. Dans la section **Serveurs ESXi**, cliquez sur **Ajouter**.
6. Dans la fenêtre **Ajouter un serveur**, indiquez le nombre de serveurs que vous voulez ajouter, passez en revue le coût estimé, puis cliquez sur **Ajouter**.

### Résultats après l'ajout de serveurs ESXi
{: #sd_addingremovingservers-adding-results}

1. Un bref délai peut être observé sur la console entre le passage du statut **Prêt à l'emploi** au statut **Modification en cours**. Laissez l'opération s'exécuter complètement avant d'apporter d'autres modifications à l'instance.
2. Un courrier électronique vous avise de l'ajout de vos serveurs ESXi.
3. Si vous ne voyez pas les serveurs ESXi ajoutés dans la liste du cluster, consultez vos courriers électroniques ou les notifications de la console pour obtenir plus de détails sur la cause de l'échec.

## Retrait de serveurs ESXi dans des instances Cloud Foundation
{: #sd_addingremovingservers-removing}

### Avant de retirer des serveurs ESXi
{: #sd_addingremovingservers-removing-prereq}

* Ne retirez pas de serveurs ESXi depuis le client Web VMware vSphere. Les modifications apportées sur le client Web VMware vSphere ne sont pas synchronisées avec la console {{site.data.keyword.vmwaresolutions_short}}.
* La plateforme de base que vous avez commandée dispose par défaut de 4 serveurs ESXi. Vous pouvez supprimer les serveurs ESXi que vous avez ajoutés. Vous ne pouvez pas supprimer les serveurs ESXi par défaut.
* Avant de retirer des serveurs ESXi avec le service F5 on {{site.data.keyword.cloud_notm}} ou FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} installé, vous devez faire migrer les machines virtuelles F5 BIG-IP et FortiGate vers un autre serveur ESXi que celui sur lequel elles sont hébergées.
* Avant de retirer des serveurs ESXi sur lesquels le service IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} est installé, vérifiez qu'aucune opération de sauvegarde ou de restauration n'est active. En effet, les opérations actives, qu'elles aient échoué ou qu'elles soient en cours, pourraient empêcher le retrait des serveurs ESXi.

## Procédure de retrait de serveurs ESXi
{: #sd_addingremovingservers-removing-procedure}

1. A partir de la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Ressources** dans le panneau de navigation de gauche.
2. Dans le tableau **Instances Cloud Foundation**, cliquez sur l'instance dont vous désirez réduire la capacité.
3. Cliquez sur **Infrastructure** dans le panneau de navigation de gauche.
4. Dans le tableau **CLUSTERS**, cliquez sur le cluster sur lequel vous désirez retirer des serveurs ESXi.
6. Dans la section **Serveurs ESXi**, sélectionnez les serveurs que vous désirez supprimer et cliquez sur **Retirer**.

### Résultats après le retrait de serveurs ESXi
{: #sd_addingremovingservers-removing-results}

1. Un bref délai peut être observé sur la console entre le passage du statut **Prêt à l'emploi** au statut **Modification en cours**. Laissez l'opération s'exécuter complètement avant d'apporter d'autres modifications à l'instance.
2. Un courrier électronique vous avise du retrait de vos serveurs ESXi.
3. Les serveurs ESXi sont complètement récupérés par l'infrastructure {{site.data.keyword.cloud_notm}} à la fin de son cycle de facturation, lequel est généralement de 30 jours.

   Les serveurs ESXi retirés vous sont facturés jusqu'à échéance du cycle de facturation d'{{site.data.keyword.cloud_notm}}.
   {:note}

## Liens connexes
{: #sd_addingremovingservers-related}

* [Nomenclature de Cloud Foundation](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_bom)
* [Ajout, affichage et suppression de clusters pour des instances Cloud Foundation](/docs/services/vmwaresolutions/services?topic=vmware-solutions-sd_addingviewingclusters#sd_addingviewingclusters)
* [Place a host in maintenance mode](http://pubs.vmware.com/vsphere-60/index.jsp?topic=%2Fcom.vmware.vsphere.resmgmt.doc%2FGUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){:new_window}
* [Enhanced vMotion Compatibility (EVC) processor support](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1003212){:new_window}

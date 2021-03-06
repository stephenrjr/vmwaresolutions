---

copyright:

  years:  2016

lastupdated: "2016-12-12"

subcollection: vmware-solutions


---

# Notes sur l'édition pour la version 1.2
{: #relnotes_v12}

Cette édition inclut de nouvelles fonctionnalités, des améliorations d'utilisation et des corrections d'erreur. Pour obtenir la liste des erreurs rectifiées dans les différentes éditions, des problèmes connus concernant le produit et des astuces relatives à l'utilisation d'{{site.data.keyword.vmwaresolutions_full}}, voir [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Mises à jour de composant
{: #relnotes_v12-comp}

La nouvelle version de VMware ESXi est vSphere 6.0 u2 p03, mise à jour depuis ESXi 6.0 u2 dans l'édition précédente.

## Association de comptes IBMid et Bluemix
{: #relnotes_v12-ibm-id}

{{site.data.keyword.vmwaresolutions_full}} est fourni en tant que solution d'infrastructure dans le catalogue IBM Bluemix®. Vous devez associer le compte **IBMid** à un compte Bluemix afin d'utiliser votre compte **IBMid** pour vous connecter à la console {{site.data.keyword.vmwaresolutions_short}}.

Pour plus d'informations, voir les rubriques suivantes :
* [Initiation](/docs/services/vmwaresolutions?topic=vmware-solutions-getting-started)
* [Traitement des incidents liés à l'accès à Bluemix](/docs/account?topic=account-accessing){:new_window}

## Reprise après incident Zerto
{: #relnotes_v12-zerto}

Vous pouvez commander des instances VMware Cloud Foundation et des instances VMware vCenter Server avec la reprise après incident Zerto déjà incluse. Vous pouvez également ajouter la reprise après incident Zerto à vos instances Cloud Foundation et vCenter Server dans la page des détails de l'instance.

Pour plus d'informations, voir les rubriques suivantes :
* [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Affichage des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_viewinginstances)
* [Reprise après incident Zerto](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)

## Informations de tarification
{: #relnotes_v12-price}

Vous pouvez désormais afficher et passer en revue le coût estimé des instances commandées avant de passer la commande. Une fois que vous avez sélectionné vos composants pour l'instance que vous commandez, le coût total et la tarification détaillée de tous les composants s'affichent sur la page **Récapitulatif**.

Pour plus d'informations, voir [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance).

## Améliorations du processus de commande d'instance
{: #relnotes_v12-inst-order}

Les améliorations notables suivantes ont été apportées au processus de commande d'instance :
* Pour les instances Cloud Foundation comme pour les instances vCenter Server, de nouvelles vérifications de validation ont été instaurées afin de garantir que le compte utilisateur SoftLayer® que vous utilisez dispose des autorisations requises, que le spanning VLAN est activé et que la clé d'API appropriée est fournie. Si l'une des exigences n'est pas satisfaite, vous recevez des instructions directement sur l'interface utilisateur pour régler les problèmes.
*  Pour les instances vCenter Server, l'odre dans lequel vous sélectionnez les composants de l'instance est optimisé de sorte que seul les centres de données disposants du matériel et des serveurs ESXi dont vous avez besoin soient affichés. Cette modification réduit le risque d'erreurs ultérieures.

Pour plus d'informations, voir [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance).

## Notifications par courrier électronique supplémentaires
{: #relnotes_v12-email}

Vous recevez désormais une notification par courrier électronique lorsque de nouveaux serveurs ESXi sont ajoutés à vos instances et lorsque des serveurs ESXi existants sont supprimés. De plus, vous êtes averti par courrier électronique lorsqu'une instance est supprimée. Les paramètres de notification sont activés par défaut. En fonction de vos préférences, vous pouvez définir sur la page **Paramètres** les notifications que vous voulez recevoir.

Pour plus d'informations, voir [Paramètres et comptes utilisateur](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).

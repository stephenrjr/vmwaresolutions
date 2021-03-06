---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# Demande d'IBM Cloud Private Hosted - Obsolète
{: #managing_icp}

Les informations de cette rubrique seront bientôt obsolètes. Pour des informations plus à jour sur IBM Cloud Private Hosted, voir [Présentation d'IBM Cloud Private Hosted](icp_overview.html).
{:deprecated}

{{site.data.keyword.cloud}} Private Hosted on vCenter Server on {{site.data.keyword.cloud_notm}} déploie automatiquement {{site.data.keyword.cloud_notm}} Private Hosted sur vos instances VMware vCenter Server.

Le service {{site.data.keyword.cloud_notm}} Private Hosted fournit la puissance des microservices et des conteneurs à votre environnement VMware sur {{site.data.keyword.cloud_notm}}. Grâce à ce service, vous pouvez déployer le même modèle opérationnel et les mêmes outils VMware et {{site.data.keyword.cloud_notm}} locaux dans {{site.data.keyword.cloud_notm}}.

## Spécifications techniques pour IBM Cloud Private Hosted
{: #managing_icp-specs}

La configuration minimale requise pour pouvoir demander le service {{site.data.keyword.cloud_notm}} Private Hosted est la suivante :

* VMware vCenter Server on {{site.data.keyword.cloud_notm}}.
  **Remarque :** VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle n'est pas pris en charge.
* VMware NSX Advanced ou Enterprise edition
* Trois {{site.data.keyword.baremetal_long}}
* Processeur Dual Intel Xeon Gold 5120/28 coeurs au total, 2,2 GHz
* 384 Go de mémoire RAM par serveur
* Un partage de fichiers de stockage NFS partagé avec 8 000 Go et 4 IOPS/Go
* 33 licences de coeur de processeur virtuel IBM Cloud Private
* Pour la sauvegarde des données, le service Veeam on IBM Cloud est recommandé.

## Procédure de demande d'IBM Cloud Private Hosted
{: #managing_icp-procedure}

1. Commandez une nouvelle instance vCenter Server en suivant les étapes décrites dans [Commande d'instances vCenter Server](../vcenter/vc_orderinginstance.html). Vous pouvez également demander IBM Cloud Private Hosted pour une instance existante.
  **Important :** assurez-vous que votre environnement répond à la configuration minimale décrite précédemment.
2. Assurez-vous que vous disposez des autorisations d'utilisation pour IBM Cloud Private.
3. Après avoir reçu la confirmation que votre instance vCenter Server est prête à l'emploi, procédez comme suit pour demander IBM Cloud Private Hosted :
4. A partir de la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Initiation** dans le panneau de navigation de gauche.
5. Faites défiler la page et sous **Commander des services supplémentaires**, cliquez sur la carte **IBM Cloud Private Hosted**.
6. Sur la page **IBM Cloud Private Hosted on vCenter Server on IBM Cloud**, dans la zone **Contactez l'équipe DevOps d'IBM Cloud Private Hosted**, entrez une description de vos exigences et cliquez sur **Demander un rendez-vous**.

Un représentant {{site.data.keyword.cloud_notm}} Private Hosted DevOps vous contacte à l'aide de vos informations de contact {{site.data.keyword.cloud_notm}} et vous aide à démarrer.

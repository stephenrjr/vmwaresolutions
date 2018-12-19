---

copyright:

  years:  2016, 2018

lastupdated: "2018-11-13"

---

# Mise en réseau et infrastructure IBM Cloud

## Virtual Routing and Forwarding (VRF)

Les comptes {{site.data.keyword.cloud}} peuvent également être configurés en tant que comptes VRF (Virtual Routing and Forwarding). Un compte VRF permet de fournir des fonctionnalités similaires à VLAN spanning et ainsi d'activer le routage automatique entre les blocs d'adresses IP de sous-réseau. Tous les comptes dotés de connexions Direct Link doivent être convertis en ou créés en tant que compte VRF.

## Direct Link

{{site.data.keyword.cloud_notm}} Direct Link Connect offre un accès privé à votre infrastructure {{site.data.keyword.cloud_notm}},  ainsi qu'à d'autres clouds liés à votre fournisseur de services réseau, via votre centre de données {{site.data.keyword.CloudDataCent_notm}} local. Cette option est idéale pour la création d'une connectivité multi-cloud dans un environnement individuel.

Nous connectons des clients au réseau privé {{site.data.keyword.cloud_notm}} Private grâce à une topologie de bande passante partagée. A l'instar de tous les produits Direct Link, vous pouvez ajouter le routage mondial, qui active le trafic de réseau privé vers tous les emplacements {{site.data.keyword.cloud_notm}}. 

## Réseaux privés virtuels

### VPN strongSwan

Le service VPN IPSec strongSwan fournit un canal de communication de bout en bout sécurisé sur Internet, basé sur l'ensemble de protocoles IPSec (Internet Protocol Security) aux normes de l'industrie.

### Hybridité (HCX)

Le service VMware vCenter Server on {{site.data.keyword.cloud_notm}} Hybridity Bundle peut en toute transparence étendre les réseaux des centres de données locaux dans {{site.data.keyword.cloud_notm}}, ce qui permet de faire migrer les machines virtuelles vers et depuis {{site.data.keyword.cloud_notm}} sans aucune conversion ni modification. 

## Structure physique

L'infrastructure physique nécessaire pour déployer une instance de production {{site.data.keyword.cloud_notm}} Private (ICP) sur un cluster VMware vCenter Server on {{site.data.keyword.cloud_notm}} requiert la spécification minimale suivante : 

Tableau 1. Spécification vCenter Server pour ICP

| Déploiement NFS  |  Déploiement vSAN |
:--|:----:|:----:
Nombre de serveurs |  3 |  4
UC | 28 coeurs 2,2 GHz | 28 coeurs 2,2 GHz
Mémoire | 384 Go | 384 Go
Stockage | Gestion : 2000 Go 2 IOPS/Go, Charge de travail : 2000 Go 4 IOPS/Go, 4000 Go 4 IOPS/Go ICP | Min 960 Go SSD x 2

En plus de la configuration matérielle {{site.data.keyword.cloud_notm}} Private requise, vous devez créer des volumes persistants dans l'environnement ICP pour stocker les données de journal et la base de données Cloud Automation Manager (CAM). CAM prend en charge tous les types de volume persistant pris en charge par ICP, mais les deux configurations de stockage recommandées pour CAM sont NFS et GlusterFS.

## Structure virtuelle

Figure 1. Structure du déploiement vCenter Server et ICP
![Structure du déploiement vCenter Server et ICP](vcscar-icp.svg)

Dans l'instance vCenter Server, l'instance ICP est déployée avec une passerelle NSX Edge Services Gateway (ESG) dédiée et un routeur logique distribué (DLR). L'installation ICP est chargée dans le sous-réseau VXLAN qui est défini dans les composants ci-dessus.

La passerelle ESG est configurée avec une règle NAT source (SNAT) pour autoriser le trafic sortant, activant ainsi la connectivité Internet pour télécharger les prérequis ICP et la connectivité à GitHub et Docker, ou un proxy Web peut être utilisé pour fournir la connectivité Internet. La passerelle ESG est également configurée pour fournir l'accès aux services DNS et NTP.

La passerelle ESG est également configurée avec une règle NAT de destination (DNAT) vers les adresses IP virtuelles maître/proxy ICP à partir du réseau {{site.data.keyword.cloud_notm}} 10.x jusqu'à l'environnement VXLAN.

### Liens connexes

* [Présentation de vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle](../vcs/vcs-hybridity-intro.html)
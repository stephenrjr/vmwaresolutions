---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-20"

subcollection: vmware-solutions


---

# Requisiti e pianificazione per le istanze vCenter Server
{: #vc_planning}

Esamina i seguenti requisiti prima di ordinare le tue istanze VMware vCenter Server. Pianifica la tua istanza in base all'ubicazione del {{site.data.keyword.CloudDataCent}}, ai requisiti di capacità del tuo carico di lavoro e ai requisiti di servizi aggiuntivi.

## Requisiti dell'account IBM Cloud
{: #vc_planning-account-req}

L'account {{site.data.keyword.cloud_notm}} che utilizzi deve soddisfare determinati requisiti. Per ulteriori informazioni, vedi [Requisiti per l'account {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-slaccountrequirement).

## Disponibilità dei data center IBM Cloud
{: #vc_planning-dc-availability}

La distribuzione di vCenter Server ha requisiti rigorosi sull'infrastruttura fisica. Pertanto, puoi distribuire le istanze solo nei {{site.data.keyword.CloudDataCents_notm}} che soddisfano i requisiti. Per la distribuzione di vCenter Server sono disponibili i seguenti {{site.data.keyword.CloudDataCents_notm}}:

Tabella 1. {{site.data.keyword.CloudDataCents_notm}} disponibili per le istanze vCenter Server

| {{site.data.keyword.CloudDataCent_notm}} | Ubicazione | Regione | Opzioni server |
|:----------------------|:---------|:-------|:---------------|
| AMS03 | Amsterdam | Europa | Skylake, Broadwell |
| CHE01 | Chennai | Asia-Pacifico | Skylake, Certificato SAP, Broadwell |
| DAL09 | Dallas | Nord America meridionale | Skylake, Certificato SAP, Broadwell |
| DAL10 | Dallas | Nord America meridionale | Skylake, Certificato SAP, Broadwell |
| DAL12 | Dallas | Nord America meridionale | Skylake, Certificato SAP, Broadwell |
| DAL13 | Dallas | Nord America meridionale | Skylake, Certificato SAP, Broadwell |
| FRA02 | Francoforte | Europa | Skylake, Certificato SAP, Broadwell |
| FRA04 | Francoforte | Europa | Skylake, Certificato SAP, Broadwell |
| FRA05 | Francoforte | Europa | Skylake, Broadwell |
| HKG02 | Hong Kong | Asia-Pacifico | Skylake, Broadwell |
| LON02 | Londra | Europa | Skylake, Broadwell |
| LON04 | Londra | Europa | Skylake, Certificato SAP, Broadwell |
| LON05 | Londra | Europa | Skylake, Broadwell |
| LON06 | Londra | Europa | Skylake, Certificato SAP, Broadwell |
| MEL01 | Melbourne | Asia-Pacifico | Skylake, Certificato SAP, Broadwell |
| MEX01 | Queretaro | Nord America meridionale | Skylake, Certificato SAP, Broadwell |
| MIL01 | Milano | Europa | Skylake, Certificato SAP, Broadwell |
| MON01 | Montreal | Nord America orientale | Skylake, Certificato SAP, Broadwell |
| OSL01 | Oslo | Europa | Skylake, Broadwell |
| PAR01 | Parigi | Europa | Skylake, Broadwell |
| SAO01 | San Paolo | Sud America | Skylake, Certificato SAP, Broadwell |
| SEO01 | Seul | Asia-Pacifico | Skylake, Certificato SAP, Broadwell |
| SJC03 | San Jose | Nord America occidentale | Skylake, Broadwell |
| SJC04 | San Jose | Nord America occidentale | Skylake, Broadwell |
| SNG01 | Singapore | Asia-Pacifico | Skylake, Broadwell |
| SYD01 | Sydney | Asia-Pacifico | Skylake, Broadwell |
| SYD04 | Sydney | Asia-Pacifico | Skylake, Certificato SAP, Broadwell |
| TOK02 | Tokyo | Asia-Pacifico | Skylake, Certificato SAP, Broadwell |
| TOR01 | Toronto | Nord America orientale | Skylake, Certificato SAP, Broadwell |
| WDC04 | Washington, DC | Nord America orientale | Skylake, Certificato SAP, Broadwell |
| WDC06 | Washington, DC | Nord America orientale | Skylake, Certificato SAP, Broadwell |
| WDC07 | Washington, DC | Nord America orientale | Skylake, Certificato SAP, Broadwell |

A seconda della disponibilità e della fornitura di inventario, i {{site.data.keyword.CloudDataCents_notm}} potrebbero visualizzare un indicatore di stato nella console {{site.data.keyword.vmwaresolutions_short}} per aiutarti a pianificare le tue distribuzioni.

Tabella 2. Indicatori di stato per i {{site.data.keyword.CloudDataCents_notm}} quando ordini le istanze vCenter Server

| Stato | Dettagli sullo stato |
|:------------------------------|:--------------------------------------------------|
| Coming Soon                   | Il {{site.data.keyword.CloudDataCent_notm}} non è attualmente disponibile. |
| Temporarily Out of Inventory  | Il {{site.data.keyword.CloudDataCent_notm}} al momento non ha disponibilità. |
| Limited Inventory             | Il {{site.data.keyword.CloudDataCent_notm}} ha una disponibilità limitata e l'ordine potrebbe non essere completato. |

## Backup dei componenti di gestione
{: #vc_planning-backup-mgmt-components}

Sei responsabile del mantenimento e della verifica della disponibilità di tutti i componenti dell'istanza. Si consiglia vivamente di pianificare il backup o l'alta disponibilità di tutti i componenti di gestione. Per ulteriori informazioni, vedi [Backup dei componenti](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_backingup).

## Servizi per le istanze vCenter Server
{: #vc_planning-addon-services}

Puoi ordinare servizi aggiuntivi per la tua istanza in base alle tue esigenze, ad esempio il ripristino di emergenza. Per ulteriori informazioni, vedi [Ordine, visualizzazione e rimozione dei servizi per le istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices).

I servizi sono supportati per il vCenter Server con istanze NSX-T.
{:note}

## Considerazioni sulla capacità
{: #vc_planning-capacity-considerations}

Per ulteriori informazioni relative alle considerazioni sulla capacità, vedi [Ridimensionamento della capacità](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_scaling).

## Link correlati
{: #vc_planning-related}

* [Panoramica di vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [Ordine di istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Espansione e contrazione della capacità per le istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservers)
* [Ordine, visualizzazione e rimozione dei servizi per le istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices)

---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-30"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Note sulla release per la V2.5
{: #relnotes_v25}

Questa release include nuove funzioni, aggiornamenti dei componenti, miglioramenti dell'usabilità e correzioni di bug. Per un elenco di problemi risolti nelle diverse release, problemi noti con il prodotto e suggerimenti per l'utilizzo di {{site.data.keyword.vmwaresolutions_full}}, vedi [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Correzione Spectre e Meltdown
{: #relnotes_v25-spectre}

{{site.data.keyword.vmwaresolutions_short}} ha rilasciato patch da VMware in risposta alle vulnerabilità note come Spectre e Meltdown (CVE-2017-5753, CVE-2017-5715 e CVE-2017-5754).

* CVEID: [CVE-2017-5753](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)
* CVEID: [CVE-2017-5715](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715)
* CVEID: [CVE-2017-5754](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)

## Aggiornamento dei componenti NSX
{: #relnotes_v25-nsx}

Questa release installa VMware NSX for vSphere 6.4.1 per le nuove distribuzioni di VMware vCenter Server on {{site.data.keyword.cloud_notm}}, VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle e NetApp ONTAP Select.

## Rimozione della configurazione di backup predefinita
{: #relnotes_v25-default-backup}

{{site.data.keyword.vmwaresolutions_short}} offre due servizi aggiuntivi integrati per il backup: IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}} e Veeam on {{site.data.keyword.cloud_notm}}. Con questi servizi, puoi pianificare e fornire il ripristino sia della tua infrastruttura di gestione che del tuo carico di lavoro. Inoltre, IBM Resiliency Services fornisce servizi gestiti per i backup Veeam.

A partire dalla release della V2.5, i servizi IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} e Veeam on {{site.data.keyword.cloud_notm}}, quando distribuiti, non preconfigurano più il backup di alcuna VM. Con questa modifica, puoi garantire una corretta configurazione di tutti gli aspetti dei lavori di backup, compresi pianificazione, periodo di conservazione, utilizzo della deduplicazione, monitoraggio e avvisi e gestione delle chiavi di crittografia. Inoltre, la VM IBM CloudDriver non è più configurata come file server persistente per i backup NSX.

Sei responsabile della configurazione, della gestione e del monitoraggio di tutti i componenti software, inclusi il backup e la disponibilità dei carichi di lavoro e dell'infrastruttura di gestione. Per ulteriori informazioni, vedi [Backup dei componenti](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_backingup#backing-up-components).

Questa modifica non influisce sulle istanze distribuite prima della V2.5 su cui è installato il servizio IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} o Veeam on {{site.data.keyword.cloud_notm}}.
{:note}

## Resilienza di IBM CloudDriver
{: #relnotes_v25-cloud-driver}

Per le istanze distribuite o di cui è stato eseguito l'upgrade alle release della V2.5 o successive, il componente IBM CloudDriver non è più configurato come VM (Virtual Machine) all'interno del cluster vSphere. Viene invece distribuito, secondo necessità, come VSI (Virtual Server Instance) dell'infrastruttura {{site.data.keyword.cloud_notm}} con il codice di {{site.data.keyword.cloud_notm}} for VMware più recente per operazioni come la distribuzione di ulteriori nodi, cluster o servizi. Inoltre, IBM CloudDriver viene modificato per comunicare con il piano di gestione {{site.data.keyword.cloud_notm}} utilizzando la rete privata {{site.data.keyword.cloud_notm}}. Con questa modifica, le regole NAT (network address translation) e di firewall NSX ESG (Edge Services Gateway) che consentono a IBM CloudDriver di comunicare in uscita alla rete pubblica vengono rimosse.

Alcuni servizi aggiuntivi come F5 on {{site.data.keyword.cloud_notm}}, FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} e Zerto on {{site.data.keyword.cloud_notm}} richiedono ancora l'accesso alla rete pubblica, quindi l'ESG NSX di gestione rimane distribuito in tutte le istanze.

## Gestione di utenti e accesso con abilitazione IAM
{: #relnotes_v25-iam}

A partire dalla release della V2.5, {{site.data.keyword.vmwaresolutions_short}} è integrato con IBM IAM (Identity and Access Management) per fornire un approccio unificato per la gestione degli account e dell'accesso degli utenti all'interno del tuo account {{site.data.keyword.cloud_notm}}. Per cui:
* Puoi ora aggiungere più utenti al tuo account {{site.data.keyword.cloud_notm}} per la collaborazione e puoi gestirne l'accesso a servizi e risorse di cui viene eseguito il provisioning nel tuo account assegnando loro differenti ruoli di accesso alla piattaforma.  
* Le istanze distribuite nelle release della V2.5 e successive vengono collegate direttamente all'account utente utilizzato durante l'ordine dell'istanza.
* Le istanze distribuite nelle release della V2.4 e precedenti, possono essere migrate a un account {{site.data.keyword.cloud_notm}} specificato e gestite utilizzando IAM.

Per ulteriori informazioni, consulta i seguenti argomenti:
* [Come invitare gli utenti ad accedere a servizi e risorse](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-iamuserinvite)
* [Gestione dell'accesso utente con IAM](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-iam#iam)

## Modifiche ad account e gruppi di utenti per le istanze VMware vCenter Server e VMware Cloud Foundation
{: #relnotes_v25-user-acct}

Il gruppo di utenti **ic4v-vCenter** è stato creato sul server Microsoft Active Directory e aggiunto alle autorizzazioni globali su vCenter Server e ai gruppi di utenti per NSX Manager. Il gruppo contiene l'account utente di **automazione** per le istanze vCenter Server e gli account utente specifici del servizio per le istanze vCenter Server e Cloud Foundation.

Non modificare le autorizzazioni globali del gruppo **ic4v-vCenter** nella pagina **Utenti e gruppi** del client web VMware vSphere. Ciò potrebbe influire sulle operazioni di gestione.

Per le istanze Cloud Foundation, utilizza l'ID utente host **customerroot** al posto dell'ID utente host **root**.

Per le istanze vCenter Server, continua a utilizzare l'ID utente host **root**. L'ID utente host **ic4vroot** è stato creato solo per utilizzo da parte di IBM.

Per ulteriori informazioni sugli account utente, vedi [Considerazioni sulla modifica delle risorse vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vcenter_chg_impact).

## Aggiornamenti per i servizi aggiuntivi
{: #relnotes_v25-services}

### IBM Cloud Private Hosted (aggiornato il 30 agosto 2018)
{: #relnotes_v25-scp-hosted}

Il servizio {{site.data.keyword.cloud_notm}} Private Hosted on vCenter Server on {{site.data.keyword.cloud_notm}} è ora disponibile per le istanze vCenter Server distribuite nella (o con upgrade alla) V2.5 o release successive.

{{site.data.keyword.cloud_notm}} Private Hosted porta la potenza dei microservizi e dei contenitori al tuo ambiente VMware su {{site.data.keyword.cloud_notm}}. Con questo servizio, puoi estendere lo stesso modello operativo e gli stessi strumenti VMware e {{site.data.keyword.cloud_notm}} Privato con cui hai dimestichezza da una situazione in loco a {{site.data.keyword.cloud_notm}}.

Puoi richiedere questo servizio dopo che hai ordinato la tua istanza di vCenter Server.

### IBM Spectrum Protect Plus on IBM Cloud
{: #relnotes_v25-spp}

A partire dalla release della V2.5, il servizio IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} viene distribuito come due VM separate in base alle procedure consigliate, con una VM che esegue il server IBM Spectrum Protect Plus e l'altra VM che esegue il server vSnap e il proxy VADP.

Puoi ora ordinare fino a 10 archivi dati di backup, consentendo fino a 120 TB di archiviazione di backup. Le VM vSnap e VADP sono dimensionate in base alla dimensione dell'archiviazione di backup da te selezionata e alle informazioni contenute in [IBM Spectrum Protect Plus Blueprints](https://www.ibm.com/developerworks/community/wikis/home?lang=en#!/wiki/Tivoli%20Storage%20Manager/page/IBM%20Spectrum%20Protect%20Plus%20Blueprints).

### KMIP for VMware on IBM Cloud
{: #relnotes_v25-kmip}

Un nuovo endpoint è ora disponibile in Germania per il servizio KMIP for VMware on {{site.data.keyword.cloud_notm}}.

## Documentazione nuova e aggiornata
{: #relnotes_v25-new-docs}

### Documentazione sull'archiviazione collegata
{: #relnotes_v25-docs-storage}

Il documento tecnico relativo all'architettura collegata per vCenter Server on IBM Cloud è ora disponibile nella sezione *Riferimento* della documentazione dell'utente. Per ulteriori informazioni, vedi [Attached storage for vCenter Server on IBM Cloud](/docs/services/vmwaresolutions/archiref/attached-storage?topic=vmware-solutions-storage-benefits).

### Specifiche tecniche
{: #relnotes_v25-docs-tech-specs}

Le specifiche tecniche per tutti i tipi di istanze e i tipi di servizio sono ora disponibili nella documentazione dell'utente e collegate dall'interfaccia utente. Per ulteriori informazioni, vedi l'argomento di panoramica appropriato per l'istanza e il servizio.

### Documentazione dei servizi
{: #relnotes_v25-docs-services}

Le informazioni sui servizi sono state migliorate per identificare facilmente il supporto del servizio in base al numero di release in cui è stato reso disponibile.

Per ulteriori informazioni, consulta i seguenti argomenti:

* [Servizi disponibili per le istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices#available-services-for-vcenter-server-instances)
* [Servizi disponibili per le istanze vCenter Server with Hybridity Bundle](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices#available-services-for-vcenter-server-with-hybridity-bundle-instances)

## Aggiornamenti e miglioramenti dell'interfaccia utente
{: #relnotes_v25-ui}

L'interfaccia utente è aggiornata e fornisce i seguenti miglioramenti:

* Se hai un account dell'infrastruttura {{site.data.keyword.cloud_notm}} (SoftLayer) collegato al tuo account {{site.data.keyword.cloud_notm}}, puoi ora fare clic sul nuovo pulsante **Recupera** nella pagina **Impostazioni** per ottenere automaticamente il nome utente e la chiave API per il tuo account dell'infrastruttura {{site.data.keyword.cloud_notm}} (SoftLayer).
* È stata aggiunta una nuova scheda **Cronologia distribuzione** nel riquadro di navigazione a sinistra della pagina dei dettagli dell'istanza che ti consente di verificare la cronologia di distribuzione di un'istanza.
* Sono disponibili vari messaggi di errore e miglioramenti delle descrizioni a comparsa per aiutarti a selezionare le impostazioni appropriate nell'interfaccia utente.

---

copyright:

  years:  2016, 2018

lastupdated: "2018-04-16"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Notas sobre a liberação para V2.1
{: #relnotes_v21}

Esta liberação inclui novos recursos, atualizações de componentes, aprimoramentos de usabilidade e correções de bug. Para obter uma lista de problemas corrigidos em diferentes liberações, problemas conhecidos com o produto e dicas para usar o {{site.data.keyword.vmwaresolutions_full}}, consulte o [{{site.data.keyword.vmwaresolutions_short}}dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Correção para Spectre e Meltdown
{: #relnotes_v21-spectre}

O {{site.data.keyword.vmwaresolutions_short}} liberou correções do VMware em resposta às vulnerabilidades conhecidas como Spectre e Meltdown (CVE-2017-5753, CVE-2017-5715 e CVE-2017-5754).

* CVEID: [CVE-2017-5753](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)
* CVEID: [CVE-2017-5715](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715)
* CVEID: [CVE-2017-5754](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)

## VMware HCX on IBM Cloud
{: #relnotes_v21-hcx}

O serviço HCX on {{site.data.keyword.cloud_notm}} está disponível para instâncias do VMware Cloud Foundation e do VMware vCenter Server que estão executando o vSphere 6.5 e que são implementadas em ou têm upgrade feito para a V2.1 ou liberações mais recentes. Esse serviço pode ampliar continuamente as redes de seus data centers locais para o {{site.data.keyword.cloud_notm}}, permitindo a migração bidirecional de máquinas virtuais (MVs) entre seus data centers locais e o {{site.data.keyword.cloud_notm}}, sem nenhuma mudança. Ao estabelecer uma ponte de camada 2, o HCX usa otimização, deduplicação, compactação e criptografia de WAN para migrar com mais rapidez e segurança os dados em um Link direto ou um túnel VPN. A migração em massa de MVs é compatível com versões anteriores com o VMware vSphere 5.1 ou superior. Se você usar o vSphere 6.0 ou superior no local, será possível efetuar vMotion em tempo real (ligado) em MVs do local para um {{site.data.keyword.CloudDataCent_notm}}. Não é necessário ter o VMware NSX instalado em seu data center ao usar o HCX.

É possível pedir instâncias do Cloud Foundation ou do vCenter Server com o serviço HCX on {{site.data.keyword.cloud_notm}} incluído quando você pede a sua instância ou incluir esse serviço em suas instâncias existentes posteriormente na guia **Serviços** na página de detalhes da instância.

É possível também pedir uma instância do HCX local para licenciamento e ativação da instalação do HCX local.

Para obter mais informações, veja os tópicos a seguir:
* [Considerações para o HCX no {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions?topic=vmware-solutions-hcx_considerations#hcx_considerations)
* [Gerenciando o HCX no {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managinghcx)
* [Considerações para instâncias do HCX locais](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_considerations)
* [Pedindo instâncias do HCX locais](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_orderingserviceinstances)

## Modelo mais flexível do Bring Your Own License para o VMware Cloud Foundation e o vCenter Server
{: #relnotes_v21-byol}

Bring Your Own License (BYOL) ou comprar o licenciamento de assinatura fornecido pela IBM ao criar um novo cluster estão agora disponíveis para instâncias V2.1 e mais recentes do VMware Cloud Foundation e instâncias do VMware vCenter Server. Essas opções permitem usar sua chave de componente existente ou alugar a licença da IBM. Antes da V2.1, não seria possível comprar o licenciamento fornecido pela IBM para um componente específico do VMware se você usasse BYOL. Atualmente, apenas o VMware vSphere e o VMware vSAN estão disponíveis para licenciamento por cluster.

Além disso, quando você incluir nós em um cluster licenciado com sua chave, o console solicitará o fornecimento de uma nova chave de licença se o número de nós exceder a capacidade principal.

Para obter mais informações, veja os tópicos a seguir:

* [Incluindo, visualizando e excluindo clusters para instâncias do vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)
* [Pergunta mais frequente sobre BYOL](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq_byol)

## Atualizações de componentes de serviço Zerto on IBM Cloud
{: #relnotes_v21-zerto}

Para o serviço Zerto on {{site.data.keyword.cloud_notm}} implementado em instâncias V2.1 e mais recentes do Cloud Foundation e instâncias vCenter Server, o Zerto Virtual Replication 5.5u2 é provisionado. Os virtual replication appliances (VRAs) do Zerto são agora implementados no armazenamento de dados de gerenciamento (vSAN ou Endurance), em vez de no armazenamento local de dados por motivos de desempenho. Se você tiver VRAs existentes, considere migrar seu armazenamento para o armazenamento de dados de gerenciamento para obter melhor desempenho.

Para obter mais informações, consulte [Visão geral do Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr).

## Atualizações para instâncias do VMware vCenter Server
{: #relnotes_v21-vcs}

### NetworkMTU as definições de configuração
{: #relnotes_v21-mtu}

Para V2.1 ou liberações mais recentes, as novas instâncias do vCenter Server são pedidas com a configuração Distributed Virtual Switch (DVS) público como MTU 1500 (padrão). Para obter mais informações, veja _Definições de configuração de MTU de rede_ em [Lista de materiais do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_bom).

### Aplicação automática de correções e atualizações do VMware ESXi em hosts
{: #relnotes_v21-esxi-patches}

Em instâncias do VMware vCenter Server V2.0 e anterior, as correções não foram aplicadas automaticamente em hosts ESXi que foram incluídos em um cluster.

Em instâncias V2.1 e mais recente, a automação aplica correções a novos hosts ESXi para que o nível de correção corresponda ao nível de correção no momento que a instância inicial foi fornecida. Você é responsável por aplicar manualmente todas as correções e atualizações futuras.
Quando as correções e atualizações do VMware são disponibilizadas em liberações futuras, a automação varre os hosts ESXi de suas instâncias existentes e envia um lembrete por e-mail para aplicar as correções e atualizações mais recentes manualmente.

Para obter mais informações, veja [Aplicando atualizações em instâncias do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_applyingupdates).

### Estimativas de preço para upgrades de licença do VMware NSX
{: #relnotes_v21-nsx-license}

Agora é possível ver uma estimativa de preço antes de enviar um pedido para fazer upgrade para a edição Advanced ou Enterprise do VMware NSX. A precificação é baseada no número de hosts ESXi na instância do vCenter Server. Essa compra muda somente a chave de licença do NSX e faz upgrade de sua edição Base do VMware NSX para a edição Advanced ou Enterprise. A compra não faz upgrade da versão de software NSX.

Para obter mais informações, veja [Visão geral do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview).

### O máximo de servidores por cluster aumenta a partir de 32
{: #relnotes_v21-max-clusters}

Para o cluster padrão em uma instância, é possível implementar ou expandir até 51 servidores. Para todos os clusters subsequentes em uma instância, é possível implementar ou expandir até 59 servidores. Para obter mais informações, consulte [Incluindo, visualizando e excluindo clusters para instâncias do vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters).

Esse recurso está disponível somente para instâncias que são implementadas na V2.1 e mais recente. As instâncias submetidas a upgrade para a V2.1 por meio de liberações anteriores à V2.1 não têm essa opção.
{:note}

### Opções de configuração do IBM Cloud Bare Metal Server customizadas pelo usuário
{: #relnotes_v21-bare-metal}

Agora, a configuração de Bare Metal Servers customizada oferece o Dual Intel Xeon Gold 6140 com 36 núcleos no total, 2,3 GHz.

Para obter mais informações, veja os tópicos a seguir:
* [Visão geral do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [Pedindo instâncias do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)

### Configurações de compartilhamento de arquivos NFS individuais
{: #relnotes_v21-nfs}

Agora é possível configurar compartilhamentos de arquivos NFS individualmente. Selecione o tamanho do arquivo e o nível de desempenho para cada compartilhamento de arquivo individual ou selecione o mesmo tamanho de arquivo e nível de desempenho para todos os compartilhamentos de arquivos que você pedir.

Para obter mais informações, veja os tópicos a seguir:
* [Visão geral do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [Pedindo instâncias do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Incluindo, visualizando e excluindo clusters para instâncias do vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)

## Atualizações e aprimoramentos da interface com o usuário
{: #relnotes_v21-ui}

São feitas melhorias em toda a interface com o usuário:

* A opção **Pedir instância** não está mais disponível na área de janela de navegação esquerda. Clique em **Introdução** para concluir as etapas para pedir uma instância.
* O campo **Prefixo do subdomínio** da página **Básico** ao pedir uma instância foi renomeada para **Rótulo do subdomínio**.
* Além de visualizar a estimativa de custo na página **Resumo** ao pedir uma instância primária ou secundária do vCenter Server ou do Cloud Foundation, agora é possível calcular uma estimativa de custo em qualquer página à medida que você fornece os detalhes para o pedido de instância.
* A navegação da trilha de navegação é incluída na página **Recursos** como um método alternativo de navegação, reduzindo, assim, o número de etapas que são necessárias para acessar as páginas pai.
* Várias mensagens de erro e aprimoramentos de dicas de ferramenta estão disponíveis para ajudá-lo na seleção da configuração apropriada na interface com o usuário.

## Documentação nova e atualizada
{: #relnotes_v21-new-docs}

Uma nova orientação do developerWorks está disponível com instruções passo a passo sobre como conectar armazenamento dedicado a implementações existentes do {{site.data.keyword.vmwaresolutions_full}} que usam o NetApp ONTAP Select on {{site.data.keyword.cloud_notm}}. Para obter mais informações, veja [Etapas para anexar o armazenamento dedicado ao VMware Solutions on IBM Cloud](https://developer.ibm.com/recipes/tutorials/steps-to-attach-dedicated-storage-to-existing-ic4v-deployments-on-ibm-cloud/).

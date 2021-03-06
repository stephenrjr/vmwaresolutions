---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-04"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Visão geral do FortiGate Virtual Appliance on IBM Cloud
{: #fortinetvm_considerations}

O serviço FortiGate Virtual Appliance on {{site.data.keyword.cloud}} implementa um par de FortiGate Virtual Appliances em seu ambiente, o que pode ajudá-lo a reduzir o risco ao implementar controles de segurança crítica em sua infraestrutura virtual.

É possível instalar múltiplas instâncias desse serviço, conforme necessário. É possível gerenciar esse serviço usando o FortiOS Web Client ou a interface da linha de comandos por meio de SSH.

Este serviço está disponível somente para instâncias implementadas na V2.0 ou liberações mais recentes. A versão do serviço atual que está instalada é 6.0.3.
{:note}

## Especificações técnicas para o FortiGate Virtual Appliance on IBM Cloud
{: #fortinetvm_considerations-specs}


Os componentes a seguir são pedidos e incluídos no serviço FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}:

### Máquinas virtuais
{: #fortinetvm_considerations-specs-vms}

* Todas as opções incluem um par altamente disponível (HA) de máquinas virtuais
* 2, 4 ou 8 vCPUs por máquina virtual, dependendo do tamanho da implementação e do tipo de assinatura
* 4, 6 ou 12 GB de RAM por máquina virtual, dependendo do tamanho da implementação e do tipo de assinatura

### Alta disponibilidade
{: #fortinetvm_considerations-specs-ha}

Duas máquinas virtuais são implementadas e prontas para a configuração do HA ou do Virtual Router Redundancy Protocol (VRRP).

### Rede
{: #fortinetvm_considerations-specs-network}

O acesso ao console do FortiGate® é fornecido por meio de uma rede de gerenciamento privado.

### Licença e taxas
{: #fortinetvm_considerations-specs-license}

As taxas de licença para cada máquina virtual são aplicadas a cada ciclo de faturamento, dependendo do tamanho de implementação selecionado e do modelo de licença de assinatura mensal.

Não é possível mudar o nível de licenciamento após a instalação do serviço. Para mudar o nível de licenciamento, deve-se remover o serviço existente e reinstalá-lo usando uma opção de licenciamento diferente.
{:important}

## Considerações ao instalar o FortiGate Virtual Appliance no IBM Cloud
{: #fortinetvm_considerations-install}

Revise as considerações a seguir antes de instalar o serviço FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}:
* As máquinas virtuais (MVs) do FortiGate são implementadas somente no cluster padrão.
* 100% de CPU e RAM para as duas MVs do FortiGate também são reservadas porque essas MVs estão no plano de dados das
comunicações de rede e é crítico que os recursos ainda estejam disponíveis para elas.

  Para calcular a reserva de CPU e de RAM para uma única MV do FortiGate, use a seguinte fórmula:
   * `Reserva de CPU = velocidade da CPU do servidor ESXi * número de vCPUs`
   * `Reserva de RAM = tamanho de RAM`
* Ao implementar um par de HA do FortiGate Virtual Appliances em sua instância, as regras de firewall e SNAT são definidas no Management NSX Edge Services Gateway (ESG) juntamente com rotas estáticas no FortiGate Virtual Appliances para permitir comunicações HTTPS de saída de sua instância para a rede pública para ativação da licença e para aquisição do conteúdo e das políticas de segurança mais recentes.
* Não é possível mudar o nível de licença após a instalação do serviço. Para mudar o nível de licença, deve-se remover o serviço existente e, em seguida, reinstalá-lo selecionando uma opção de licença diferente.
* Deve-se atender aos seguintes requisitos para evitar falhar com o FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}:
   * Pelo menos dois servidores ESXi ativos estão disponíveis para as duas MVs do FortiGate a serem implementadas com a regra de antiafinidade de manter as MVs em servidores separados.
   * Os dois servidores ESXi ativos têm recursos suficientes disponíveis para que uma MV do FortiGate possa ser hospedada em cada servidor ESXi com 100% de reserva de CPU e de RAM.
   * O VMware vSphere HA tem recursos suficientes para hospedar duas MVs do FortiGate com 100% de CPU e de RAM.

  Devido a esses requisitos, deve-se planejar o espaço necessário para o FortiGate Virtual Appliance on
{{site.data.keyword.cloud_notm}} cuidadosamente. Se necessário, antes de pedir o FortiGate Virtual Appliance on
{{site.data.keyword.cloud_notm}}, inclua de 1 a 2 servidores ESXi na sua instância, reduza a reserva de CPU de HA do vSphere para failover ou ambos.

## Exemplo de pedido do FortiGate Virtual Appliance on IBM Cloud
{: #fortinetvm_considerations-example}

Você pede uma instância **Pequena** do VMware vCenter Server com 2 servidores ESXi com a seguinte configuração: 16 núcleos em 2,10 GHz cada um com 128 GB de RAM. Para o FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}, você seleciona **Grande** (8 vCPUs / 12 GB de RAM) para o tamanho de implementação e qualquer modelo de licença de assinatura.

Nesse caso, uma única MV do FortiGate requer, em cada servidor:
* 2,1 GHz * 8 vCPU = 16,8 GHz de CPU e
* 12 GB de RAM

No total, são 33,6 GHz de CPU e 24 GB de RAM para duas MVs do FortiGate.

Cada servidor ESXi tem uma capacidade de 16 núcleos * 2,1 GHz = 33,6 GHz, então, nós atenderemos aos dois primeiros requisitos se ambos os servidores estiverem ativos e houver pelo menos 16,8 GHz de CPU e 12 GB de RAM disponível em cada servidor.

Por padrão, no entanto, o vSphere HA reserva 50% de CPU e de RAM para failover em instâncias do vCenter Server que foram inicialmente implementadas com 2 servidores ESXi; portanto, só temos:

`50% de 2 * 16 núcleos * 2,1 GHz = 33,6 GHz disponível`

Como existem outras cargas de trabalho nos servidores ESXi, por exemplo, o VMware vCenter Server, o VMware NSX Controller ou o VMware NSX Edge, usando esses recursos, o terceiro requisito não é atendido. Isso porque precisamos de 33.6 GHz de CPU e 24 GB de RAM
para as duas MVs FortiGate.

Nesse caso, a instalação do FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} pode falhar, a menos que pelo
menos um servidor ESXi seja incluído no ambiente e as reservas de failover de HA do vShpere sejam corretamente atualizadas para
assegurar que haja recursos suficientes para as duas MVs do FortiGate.

Se recursos adicionais forem necessários para executar o serviço FortiGate Virtual Appliance on
{{site.data.keyword.cloud_notm}}, será possível incluir mais servidores ESXi antes de instalar o serviço.

## Considerações ao remover o FortiGate Virtual Appliance no IBM Cloud
{: #fortinetvm_considerations-remove}

Antes de remover o serviço FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}, assegure-se de que a configuração do FortiGate Virtual Appliances existente seja removida corretamente. Especificamente, o tráfego de rede deve ser roteado ao redor do FortiGate Virtual Appliances em vez de através do FortiGate Virtual Appliances. Caso contrário, o tráfego de dados existente em seu ambiente pode ser afetado.

## Links relacionados
{: #fortinetvm_considerations-related}

* [Solicitando FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_ordering)
* [Gerenciando o FortiGate Virtual Appliance no {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingfortinetvm)
* [Entrando em contato com o Suporte IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [Perguntas mais frequentes](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [Website do Fortinet](https://www.fortinet.com/){:new_window}
* [Biblioteca de documentos do Fortinet](https://docs.fortinet.com/product/fortigate/6.2){:new_window}

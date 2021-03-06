---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-04"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Excluindo instâncias do NetApp ONTAP Select
{: #np_deletinginstance}

Se você excluir uma instância do NetApp ONTAP Select, os componentes a seguir serão liberados sequencialmente:
1. As MVs (máquinas virtuais) implementadas em cluster do NetApp ONTAP Select e a MV de implementação do NetApp ONTAP Select
2. Taxa de suporte e serviços
3. Licenças do produto VMware
4. Servidores ESXi
5. Subnets
6. VLANs

Devido a dependências de recursos, os componentes em sua instância não são liberados imediatamente quando você exclui a instância. Por exemplo, as sub-redes e VLANs não podem ser excluídas até que os servidores ESXi sejam totalmente recuperados pela infraestrutura do {{site.data.keyword.cloud}}, o que acontece no final do ciclo de faturamento do {{site.data.keyword.cloud_notm}}. No final do ciclo de faturamento, que é geralmente de 30 dias, as sub-redes e VLANs são recuperadas e a exclusão da instância está concluída.

Você é faturado até o final do ciclo de faturamento da instância excluída.
{:note}

## Procedimento para excluir instâncias da página Recursos
{: #np_deletinginstance-procedure1}

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Recursos** na área de janela de navegação esquerda.
2. Na tabela **Instâncias do NetApp ONTAP Select**, localize a instância a ser excluída.
3. Na coluna **Ações**, clique no ícone Excluir.
   O status da instância é mudado para **Excluindo**. Quando a instância for excluída com êxito e seu status for mudado para **Excluído**, clique no ícone de exclusão na coluna **Ações**
   novamente.
4. Se desejar remover o registro da instância do console do {{site.data.keyword.vmwaresolutions_short}}, conclua as etapas a seguir:
   1. Na coluna **Ações**, clique no ícone Excluir novamente.
   2. Na janela **Excluir instância**, clique em **OK**.

## Procedimento para excluir instâncias da página Detalhes da instância
{: #np_deletinginstance-procedure2}

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Recursos** na área de janela de navegação esquerda.
2. Na tabela **Instâncias do NetApp ONTAP Select**, clique na instância a ser excluída.
3. Clique no ícone do menu overflow próximo ao **console do NetApp** e clique em **Excluir instância**.
   O status da instância é mudado para **Excluindo**. Quando a instância for excluída com êxito, seus componentes serão liberados e seu status mudará para **Excluído**.
4. Se desejar remover o registro da instância do console do {{site.data.keyword.vmwaresolutions_short}}, conclua as etapas a seguir:
   1. Clique no ícone do menu overflow próximo ao **Console do vCenter** novamente e clique em **Excluir instância**.
   2. Na janela **Excluir instância**, clique em **OK**.

## Links relacionados
{: #np_deletinginstance-related}

* [Pedindo instâncias do NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)
* [Visualizando instâncias do NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_viewinginstances)
* [Entrando em contato com o Suporte IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)

---

copyright:

  years:  2016

lastupdated: "2016-11-04"

subcollection: vmware-solutions


---

# Notas del release para V1.1
{: #relnotes_v11}

Este release incluye nuevas características, mejoras en la usabilidad y correcciones de errores. Para ver una lista de los problemas solucionados en distintos releases, problemas conocidos del producto y sugerencias para utilizar {{site.data.keyword.vmwaresolutions_full}}, consulte [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Requisito de expansión de VLAN
{: #relnotes_v11-vlan-spanning}

Si utiliza una cuenta de SoftLayer® clásica (no VRF), la expansión de VLAN debe estar habilitada. Si la expansión de VLAN no está habilitada para cuentas clásicas, es posible que los diversos componentes del entorno de virtualización de VMware no se puedan comunicar entre sí. Para habilitar la expansión de VLAN en su cuenta de SoftLayer, consulte [Habilitación o inhabilitación de la expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning){:new_window}.

## Valores de correo electrónico y notificaciones
{: #relnotes_v11-email}

Puede configurar notificaciones por correo electrónico en la página **Configuración**. De forma predeterminada, el valor está habilitado, lo que significa que recibe una notificación por correo electrónico para cualquier instancia que se haya solicitado recientemente, cuando se suministra la instancia y está lista para ser utilizada. También puede inhabilitar las notificaciones por correo electrónico en la página **Configuración**. Para obtener más información, consulte [Cuentas de usuario y valores](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).

## Información de estado detallada
{: #relnotes_v11-status-info}

Ahora dispone de información de estado detallada para instancias de Cloud Foundation. Al pulsar un nombre de instancia, la información de estado que se muestra proporciona más detalles sobre el progreso de despliegue. Si se produce un error, se muestran mensajes para ayudarle con el problema.

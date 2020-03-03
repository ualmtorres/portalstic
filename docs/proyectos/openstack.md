# OpenStack STIC

![](http://www.iihtcampus.com/wp-content/uploads/2018/07/Openstack.png)

## Enlaces

* [Repositorio]( https://gitlabdoc.ual.es/mtorres/openstack-ha-ansible.git)
* [Issues](http://gitlab.ual.es/mtorres/openstack-ha-ansible/issues)
* [Chat](https://chat.stic.ual.es/openstack/channels/openstack)
* [Agenda](http://gitlab.ual.es/mtorres/openstack-ha-ansible/-/boards)
* [Sprints - No disponible](https://gitlab.com/gitlab-org/gitter/webapp/-/milestones?sort=due_date_desc&state=closed)
* [Drive - No disponible](https://drive.google.com/open?id=1wuxdWzKuAc61UvocLMgfRCGt03r9aXT8)
* [Web](http://openstack.stic.ual.es/horizon)


## Descripción

OpenStack STIC es un cloud privado OpenStack montado en alta disponibilidad que ofrece infraestructura como servicio (IaaS). Entre los servicios ofrecidos destacan:

* Máquinas virtuales.
* Almacenamiento de bloques y almacenamiento compartido de archivos (NFS). 
* Redes como servicio pudiendo usar balanceadores como servicio (LBaaS).

## Dirigido a

Personal del STIC.

## Background

El enfoque tradicional de uso de servidores dedicados no hace una gestión eficiente de los recursos. En ocasiones es hardware dedicado usado con un único propósito y que puede tener grandes periodos de uso reducido. Esto supone un desaprovechamiento de recursos. 

Disponer de una plataforma IaaS permite usar recursos dimensionados de acuerdo con las cargas de trabajo que tienen que soportar. Dichos recursos pueden ser ampliados o reducidos posteriormente de acuerdo en función de las cargas de trabajo que tengan que soportar en cada momento.

Por otro lado, los sistemas actuales de virtualización existentes en el STIC basados en VMware son bajo demanda. Esto impide que los miembros del STIC puedan crear de forma rápida y autónoma los recursos que necesiten. Esto permite escenarios habituales como el de la creación de infraestructura transitoria para pruebas. En este sentido, el enfoque de peticiones bajo demanda no es el más adecuado y flexible.

## Propuesta

OpenStack STIC tiene instalados los siguientes componentes o servicios de OpenStack:

- Keystone: Autenticación
- Glance: Imágenes y snapshots
- Placement: Gestión y planificación de recursos
- Nova: Cómputo (máquinas virtuales)
- Neutron: Networking
- LBaaS: Balanceadores como servicio
- Cinder: Almacenamiento de bloques
- Manila: Almacenamiento compartido (NFS)
- Horizon: Web UI


OpenStack STIC se ejecuta sobre el hardware siguiente:

| Función                     | Tipo     | Modelo                   | Cantidad | Procesador           | Núcleos  | RAM (GB) | HD (TB) |
|------------------------------|----------|--------------------------|----------|----------------------|-----------|----------|---------|
| Proxy                        | Servidor | Lenovo ThinkSystem SR530 | 1        | 1 x Xeon Silver 4208 | 8         | 32       |         |
| Control                      | Servidor | Lenovo ThinkSystem SR530 | 3        | 2 x Xeon Silver 4208 | 16        | 64       |         |
| Red                          | Servidor | Lenovo ThinkSystem SR530 | 2        | 1 x Xeon Silver 4214 | 8         | 64       |         |
| Cómputo                     | Servidor | Lenovo ThinkSystem SR550 | 12       | 2 x Xeon Silver 4214 | 24        | 128      | 4.3     |
| Cómputo                     | Servidor | Lenovo ThinkSystem SR550 | 12       | 2 x Xeon Silver 4214 | 24        | 256      | 4.3     |
| Almacenamiento de bloques    | NAS      | Synology SA3400          | 1        | 1 x Xeon D-1541      | 8         | 16       | 10.4    |
| Almacenamiento compartido    | Servidor | Lenovo ThinkSystem SR550 | 1        | 2 x Xeon Silver 4210 | 20        | 64       | 6.6     |

## Permisos y seguridad

### Usuarios

* Restringido a miembros del STIC.

### Redes

- Se han definido dos subredes en la red 192.168.128.0/21:
    - Desde 192.168.128.0 hasta 192.168.129.255 para servidores OpenStack y servidores virtuales en producción.
    - Desde 192.168.130.1 hasta 192.168.135.255 para uso discrecional.

## Interacciones

* **LDAP**: Autenticación de usuarios.
* **Sistema de backups**: Copia de seguridad de la base de datos de OpenStack, archivos de configuración de los servidores OpenStack y de volúmenes importantes almacenados en el NAS.

## Documentación

* [Guía básica](https://ualmtorres.github.io/OpenStackDI/)
* [Scripts de postinstalación de instancias](https://github.com/ualmtorres/openstack-instaladores)
* [Administración de OpenStack](http://ualmtorres.github.io/howtos/AdministracionOpenStack/)
* [Eliminación de proyectos](https://ualmtorres.github.io/OpenStackTecnicosDI/docs/eliminarProyectos.html)
* [Creación de una imagen OpenStack para desarrollo con XUbuntu](http://ualmtorres.github.io/howtos/XUbuntu/)
* [Creación de una imagen Windows 7 para OpenStack](http://ualmtorres.github.io/howtos/Windows7OpenStack/)
* [Instalación de OpenStack](http://ualmtorres.github.io/howtos/InstalacionOpenStack/)
* [Personalización de Horizon](https://github.com/ualmtorres/ost)


## Tricks

### Modificaciones para LBaaS

El componente LBaaS está sin mantenimiento para las versiones actuales de OpenStack, Ubuntu y Python por lo que hay que hacer un cambio manual. De no hacerlo, OpenStack informa de un error de falta de correspondencia en el número de argumentos.

### Personalización de Horizon

Se ha adaptado el aspecto de la interfaz de Horizon con un color de fondo, cenefa, logo de inicio y logo de la cenefa. Se ha creado un [repositorio](https://github.com/ualmtorres/ost) disponible con los archivos a incluir y las instrucciones para realizar la personalización.



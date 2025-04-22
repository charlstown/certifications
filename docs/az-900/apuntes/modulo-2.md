# M2 - Servicios principales

## 1. Componentes Arquitectónicos principales Azure

### Arquitectura global Azure

La arquitectura global de Azure se organiza en una jerarquía para ofrecer alta disponibilidad, escalabilidad y tolerancia a fallos:

- **Geografías:** agrupaciones de regiones que cumplen requisitos legales y de residencia de datos.
- **Regiones:** áreas físicas (como "Europa Occidental") que contienen varios centros de datos.

![](../assets/arquitecturas-azure.png)

### Zonas y conjuntos de disponibilidad

Son ubicaciones físicas independientes dentro de una región, cada una con uno o más CPDs (Centros de Procesamiento de Datos).

- Cada región suele tener al menos **3 zonas de disponibilidad separadas físicamente** (mínimo 500 km entre regiones).

### Conjuntos de disponibilidad

Permiten mantener las aplicaciones disponibles durante ventanas de mantenimiento o ante errores de hardware.

- **Dominios de actualización** (**_Update Domains, UD_**), de modo que las operaciones de mantenimiento programado, actualizaciones por cuestiones de rendimiento o seguridad se secuencian a través de os dominios de actualización.
- **Dominios de error** (**_Fault Domains, FD_**), que proporcionan separación física de cargas de trabajo distribuidas a través del hardware del centro de datos.

### Componentes Azure

| Componente                    | Descripción                                                               | Consideraciones                                                                   |
| ----------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| **Recurso**                   | Elemento individual de Azure como una VM, base de datos, red, etc.        | Es la unidad más básica. Se despliega en una ubicación concreta.                  |
| **Grupo de recursos**         | Contenedor lógico que agrupa varios recursos relacionados                 | Pueden estar en diferentes regiones aunque estén en el mismo grupo.               |
| **Subscripción**              | Unidad organizativa que agrupa grupos de recursos y define límites de uso | Puede tener asociadas otras subscripciones para separar entornos y una principal. |
| **Administrador de recursos** | Servicio que permite crear, actualizar y eliminar recursos de Azure       | Es la interfaz que interpreta las plantillas ARM y gestiona el ciclo de vida.     |
| **Grupos de administración**  | Contenedores que agrupan suscripciones para aplicar políticas comunes     | Facilitan la gobernanza y el control a gran escala en múltiples suscripciones.    |
| **Azure Portal**              | Interfaz web gráfica para interactuar con los servicios de Azure          | Permite gestionar recursos, ver métricas, configurar alertas, etc.                |

## 2. Productos principales de carga de trabajo Azure 14

### Servicios de cómputo

Servicios para cargas de servicios genéricas desde contenedores y máquinas virtuales

| Servicio                  | Tipo       | Descripción                                                                                                        |
| ------------------------- | ---------- | ------------------------------------------------------------------------------------------------------------------ |
| **Az Virtual Machines**   | **_IaaS_** | Máquinas virtuales completas en la nube, con control total sobre el sistema operativo y software.                  |
| **Az App Service**        | **_PaaS_** | Servicio gestionado para desplegar aplicaciones web y APIs sin preocuparse por la infraestructura.                 |
| **Az Container Service**  | **_PaaS_** | Plataforma para ejecutar y gestionar contenedores (Azure Container Instances o Azure Kubernetes Service).          |
| **Azure Virtual Desktop** | **_PaaS_** | Infraestructura de escritorio virtual que permite acceder de forma remota a escritorios y apps Windows en la nube. |

#### Comparativa

| Servicio                            | Nivel de control | Ideal para                              |
| ----------------------------------- | ---------------- | --------------------------------------- |
| **App Service**                     | Bajo             | Webs y APIs gestionadas                 |
| **Azure Container Instances (ACI)** | Medio-Bajo       | Contenedores rápidos y sueltos          |
| **Azure Kubernetes Service (AKS)**  | Alto             | Arquitecturas de microservicios         |
| **Azure Functions**                 | Muy bajo         | Scripts/eventos sin preocuparte de nada |

### Servicios de Red

Son recursos para crear redes virtuales e interconectar sistemas.

| Servicio                                  | Tipo       | Descripción                                                                  |
| ----------------------------------------- | ---------- | ---------------------------------------------------------------------------- |
| **Azure Virtual Network**                 | **_IaaS_** | Red privada en la nube que permite conectar y aislar recursos de Azure.      |
| **Virtual Private Network gateway (VPN)** | **_IaaS_** | Dispositivo virtual que permite conexiones seguras entre redes mediante VPN. |
| **Azure ExpressRoute**                    | **_IaaS_** | Conexión privada y dedicada entre tu red local y Azure, fuera de Internet.   |

### Servicios de almacenamiento

Ofrecen recursos para almacenar información.

| Servicio         | Tipo       | Descripción                                                                 |
|------------------|------------|-----------------------------------------------------------------------------|
| **Blob storage** | **_IaaS_** | Almacenamiento de objetos no estructurados como imágenes, vídeos o backups. |
| **Disk storage** | **_IaaS_** | Discos virtuales que se usan con máquinas virtuales, similar a un disco duro.|
| **Azure files**  | **_IaaS_** | Almacenamiento compartido accesible mediante el protocolo SMB, como un NAS. |

#### Niveles de almacenamiento

Niveles de acceso al dato.

| Frecuente                         | Poco frecuente                        | Archivo                                   |
| --------------------------------- | ------------------------------------- | ----------------------------------------- |
| Datos con acceso regular y activo | Datos con acceso ocasional (≥30 días) | Datos fríos o archivados (≥180 días)      |
| Mayor coste de almacenamiento     | Coste intermedio                      | Muy bajo coste de almacenamiento          |
| Bajo coste de acceso              | Coste moderado de acceso              | Alto coste de acceso y recuperación lenta |

### Servicios de bases de datos

| Servicio                 | Tipo       | Descripción                                                                           |
| ------------------------ | ---------- | ------------------------------------------------------------------------------------- |
| **CosmosDB**             | **_PaaS_** | Base de datos NoSQL distribuida globalmente, con baja latencia y alta disponibilidad. |
| **Azure SQL Db**         | **_PaaS_** | Base de datos relacional gestionada basada en SQL Server.                             |
| **ADB for MySQL**        | **_PaaS_** | Servicio de base de datos MySQL totalmente gestionado en la nube.                     |
| **ADB for PostgreSQL**   | **_PaaS_** | Servicio de base de datos PostgreSQL totalmente gestionado.                           |
| **SQL Managed Instance** | **_PaaS_** | Instancia de SQL Server con alta compatibilidad, ideal para migraciones.              |

### Azure Marketplace

Azure Marketplace es una plataforma en la que puedes **descubrir, probar y adquirir** soluciones de terceros que se integran con los servicios de Azure.

- **Máquinas virtuales preconfiguradas** (con software ya instalado)
- **Aplicaciones empresariales** (CRM, ERP, seguridad, backup, etc.)
- **Sistemas operativos** (Linux, Windows Server, etc.)
- **Bases de datos** y middlewares
- **Contenedores**, plantillas ARM y servicios gestionados

Permite desplegar soluciones listas para usar con unos pocos clics, muchas de ellas con soporte oficial del proveedor.

### Políticas de redundancia de backup en Azure

Azure Backup permite elegir entre diferentes opciones de redundancia para almacenar los datos en los cofres de Recovery Services. Esta configuración afecta al nivel de durabilidad, coste y resiliencia frente a fallos.

| Opción    | Copias                              | Región secundaria | Lectura desde región secundaria | Coste       | Soportado por Azure Backup |
|-----------|-------------------------------------|-------------------|----------------------------------|-------------|-----------------------------|
| LRS       | 3 copias en un datacenter           | No                | No                               | Bajo        | Sí                          |
| ZRS       | 3 copias en zonas de una región     | No                | No                               | Medio       | Parcial (según servicio)    |
| GRS       | 3 copias + réplica geográfica       | Sí (asíncrona)    | No                               | Alto        | Sí                          |
| RA-GRS    | 3 copias + réplica geográfica       | Sí (asíncrona)    | Sí                               | Más alto    | No                          |
| GZRS      | Copias en zonas + réplica geográfica| Sí (asíncrona)    | No                               | Alto        | No                          |
| RA-GZRS   | Zonas + réplica geográfica          | Sí (asíncrona)    | Sí                               | Más alto    | No                          |

#### LRS - Locally Redundant Storage

Replica los datos tres veces dentro de una única región física (mismo datacenter).  
Es la opción más económica, pero no protege frente a desastres regionales.  
Adecuado cuando el coste es prioritario y la pérdida de datos regionales es aceptable.

#### ZRS - Zone-Redundant Storage

Replica sincrónicamente los datos entre tres zonas de disponibilidad dentro de una misma región.  
Ofrece alta disponibilidad frente a fallos zonales.  
No siempre está disponible en servicios de backup. Verificar soporte actualizado.

#### GRS - Geo-Redundant Storage

Replica los datos tres veces en la región primaria y los copia de forma asíncrona a una región secundaria geográfica.  
Aporta alta durabilidad incluso en escenarios de desastre regional.  
Es la opción recomendada por defecto en la mayoría de escenarios críticos de backup.

#### RA-GRS - Read-Access Geo-Redundant Storage

Igual que GRS, pero permite el acceso de solo lectura a los datos desde la región secundaria.  
Aporta disponibilidad de lectura adicional en caso de fallo en la región principal.  
Azure Backup no admite esta opción; solo están disponibles LRS y GRS.

#### GZRS - Geo-Zone-Redundant Storage

Combina replicación entre zonas dentro de la región primaria con replicación geográfica a una región secundaria.  
Diseñado para alta disponibilidad local más recuperación ante desastres regionales.  
No disponible actualmente en Azure Backup.

#### RA-GZRS - Read-Access Geo-Zone-Redundant Storage

Extiende GZRS permitiendo lectura desde la región secundaria.  
Ofrece máxima durabilidad y disponibilidad.  
No soportado por Azure Backup.

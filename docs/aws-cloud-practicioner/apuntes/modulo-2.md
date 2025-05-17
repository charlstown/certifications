# M2 - Servicios cómputo y almacenamiento


## 1. Servicio de redes y entrega de contenido

### Amazon Virtual Private Cloud (Amazon VPC)

**Amazon VPC** es un servicio fundamental de AWS que permite **aislar de forma lógica una sección de la nube de AWS** para desplegar recursos de forma segura y controlada.

![[aws-vpc.png]]

#### Características principales de Amazon VPC

|Característica|Descripción|
|---|---|
|**Aislamiento lógico**|Crea redes privadas dentro de AWS, independientes de otras VPC.|
|**Control de direcciones IP**|Define rangos de direcciones IP para las instancias y recursos.|
|**Subredes**|Crea subredes **públicas** (con acceso a Internet) o **privadas**.|
|**Tablas de enrutamiento**|Gestionan las rutas del tráfico de red entre subredes y a Internet.|
|**Puertas de enlace**|Controlan la salida/entrada de la red (Internet Gateway, NAT Gateway).|
|**ACLs de red**|Capas adicionales de control de acceso para gestionar el tráfico entre subredes.|

#### Direcciones IP en Amazon VPC

|Tipo de IP|Descripción|
|---|---|
|**Privada**|Asignada automáticamente en la VPC.|
|**Pública**|Opcional al crear la instancia, permite acceso desde Internet.|
|**Elástica (EIP)**|IP pública **estática** asociada a la cuenta. Puede implicar costes adicionales.|

#### Interfaz de red elástica (ENI)

- Es una **interfaz de red virtual** que puede:
    - Asociarse o desacoplarse de una instancia de EC2.
    - Mantener atributos como direcciones IP, MAC y reglas de seguridad al cambiar de instancia.

- Permite **redireccionar tráfico de red** rápidamente a otra instancia, facilitando tareas de alta disponibilidad y recuperación.

#### Tablas de enrutamiento

Es simplemente una **lista de reglas (rutas)** que indican **a dónde debe enviarse el tráfico de red según su destino**.

| Concepto                  | Descripción                                                                    |
| ------------------------- | ------------------------------------------------------------------------------ |
| **Tabla de enrutamiento** | Define las rutas del tráfico de red de las subredes.                           |
| **Destino**               | Dirección de red hacia donde se dirige el tráfico.                             |
| **Objetivo**              | Indica cómo se envía el tráfico (por ejemplo, Internet Gateway o NAT Gateway). |

- Cada subred debe estar asociada a una tabla de enrutamiento.
- Varias subredes pueden compartir la misma tabla.

!!! Info "¿Qué tipo de IP se utiliza para asegurar una dirección pública fija?"

    → Las **Elastic IP (EIP)**.

!!! Info "¿Qué recurso permite separar el tráfico de Internet en subredes públicas y privadas?"

    → La **Internet Gateway** para subredes públicas y **NAT Gateway** para permitir tráfico saliente desde subredes privadas.

!!! Info "¿Qué permite hacer una Interfaz de Red Elástica (ENI)?"

    → Mover la configuración de red y redirigir el tráfico a otra instancia de forma rápida.

### Redes y seguridad en Amazon VPC

Una vez creada la VPC, se dispone de diferentes herramientas y componentes para controlar y gestionar el tráfico dentro de la red.

#### Componentes de red

|Componente|Descripción|
|---|---|
|**Internet Gateway**|Permite la comunicación entre instancias de la VPC e Internet. Se requiere para hacer pública una subred.|
|**NAT Gateway**|Permite a instancias en subredes privadas acceder a Internet sin ser accesibles desde fuera.|
|**Peering de VPC**|Establece interconexión entre dos VPCs para compartir recursos.|
|**Elastic IP (EIP)**|IP pública y estática asignable a recursos de la VPC.|

#### Herramientas y servicios de gestión de VPC

| Servicio                           | Función principal                                                  |
| ---------------------------------- | ------------------------------------------------------------------ |
| **AWS Site-to-Site VPN**           | Conexión segura entre la VPC y una red remota.                     |
| **AWS Direct Connect**             | Conexión dedicada de baja latencia entre la red on-premises y AWS. |
| **VPC Endpoint (AWS PrivateLink)** | Conexión privada a servicios de AWS sin pasar por Internet.        |
| **AWS Transit Gateway**            | Centraliza la conectividad de múltiples VPCs y redes locales.      |
| **Amazon Route 53**                | Servicio DNS escalable y altamente disponible.                     |
| **Amazon CloudFront**              | Red de distribución de contenido (CDN) global.                     |

#### Seguridad en la VPC: Security Groups vs. ACL de Red

| Característica       | Security Group (Nivel de instancia)        | ACL de Red (Nivel de subred)                              |
| -------------------- | ------------------------------------------ | --------------------------------------------------------- |
| Nivel de aplicación  | Instancia EC2                              | Subred                                                    |
| Tipo de reglas       | Solo **permitir**                          | **Permitir** y **denegar**                                |
| Estado               | Con estado (retorno de tráfico automático) | Sin estado (debe configurarse el tráfico de retorno)      |
| Evaluación de reglas | Evalúa todas las reglas antes de decidir   | Evalúa en orden, aplicando la primera regla que coincide. |
| Aplicación           | Manual a instancias                        | Automáticamente a toda la subred                          |

!!! Info "¿Qué recurso debes utilizar para permitir que una instancia de una subred privada acceda a Internet?"

    → **NAT Gateway**.

!!! Info "¿Qué diferencia clave existe entre un Security Group y una Access Control List (ACL) de Red?"

    → Los **Security Groups son con estado** (permiten automáticamente el tráfico de retorno) y las **ACL de red son sin estado**, por lo que deben configurarse reglas explícitas para cada dirección de tráfico.

## 2. Amazon Elastic Compute Cloud

| Servicio              | Tipo         | Caso de uso principal                        | Gestión Infraestructura | Escalabilidad         |
| --------------------- | ------------ | -------------------------------------------- | ----------------------- | --------------------- |
| [[#Amazon EC2]]       | IaaS         | Máquinas virtuales, control total            | Cliente                 | Manual / Auto Scaling |
| **Lambda**            | FaaS         | Funciones sin servidor, ejecución por evento | AWS (**Serverless**)    | Automática            |
| **Elastic Beanstalk** | PaaS         | Despliegue rápido de aplicaciones web        | AWS (simplificado)      | Automática            |
| **ECS (EC2)**         | CaaS         | Contenedores gestionados sobre EC2           | Cliente (EC2)           | Manual / Auto Scaling |
| **ECS (Fargate)**     | CaaS         | Contenedores sin gestionar servidores        | AWS (**Serverless**)    | Automática            |
| **EKS**               | CaaS         | Kubernetes gestionado                        | Compartida              | Automática            |
| **Batch**             | Batch        | Procesos batch de gran volumen               | AWS (**Serverless**)    | Automática            |
| **Lightsail**         | Simplificado | Aplicaciones simples y entornos de prueba    | AWS (muy simplificado)  | Manual                |

### Amazon EC2

**Amazon EC2** es un servicio de tipo **IaaS (Infrastructure as a Service)** que permite desplegar máquinas virtuales en la nube de AWS. Es ideal para ejecutar cualquier tipo de aplicación con escalabilidad, alta disponibilidad y pago por uso.

#### Pasos para levantar un EC2

| Paso                              | Descripción                                                                                                                                                                                                                                                                                        |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. AMI (Amazon Machine Image)** | Plantilla con el sistema operativo y configuraciones iniciales. Puede ser de AWS, propia, de Marketplace o de la comunidad.                                                                                                                                                                        |
| **2. Tipo de instancia**          | Selección de recursos de CPU, RAM, almacenamiento y red según la carga de trabajo. Ejemplo: t3.micro, m5.large.                                                                                                                                                                                    |
| **3. Configuración de red**       | Seleccionar **región**, **VPC**, **subred** y si se asigna una IP pública.                                                                                                                                                                                                                         |
| **4. Asociar rol IAM**            | Permite a la instancia acceder a otros servicios AWS (ej. S3) sin usar claves de acceso.                                                                                                                                                                                                           |
| **5. Datos de usuario**           | Scripts que se ejecutan automáticamente al arrancar la instancia. (User Data).                                                                                                                                                                                                                     |
| **6. Opciones de almacenamiento** | - **EBS**: Almacenamiento persistente a nivel de bloque.<br>- **Instancia Store**: Almacenamiento efímero, se pierde al parar la instancia.<br>- **EFS**: Almacenamiento de archivos compartido. No se usa para volumen raíz.<br>- **S3**: Almacenamiento de objetos, no se usa como volumen raíz. |
| **7. Agregar etiquetas**          | Claves/valores para organizar y gestionar recursos (ej. `Environment: Production`).                                                                                                                                                                                                                |
| **8. Grupos de seguridad**        | Reglas de firewall que controlan el tráfico de entrada y salida.                                                                                                                                                                                                                                   |
| **9. Par de claves**              | Se usa para autenticarse en la instancia (SSH o RDP). Guarda la clave privada con seguridad. |

!!! Info "¿Qué servicio de almacenamiento persistente a nivel de bloque es adecuado para el volumen raíz?"

    → **Amazon EBS**.

!!! Info "¿Qué ocurre si eliminas una instancia con almacenamiento tipo Instance Store?"

    → Se **pierden los datos**; es un almacenamiento efímero.

!!! Info "¿Cómo se permite que una instancia EC2 acceda a S3 sin usar claves de acceso?"

    → Asociando un **rol de IAM** a la instancia.

#### Modelos de precios de Amazon EC2

AWS ofrece diferentes modelos de precios para adaptarse a las necesidades de coste, flexibilidad y compromiso de los clientes.

|Modelo|Descripción|Casos de uso recomendados|
|---|---|---|
|**Instancias bajo demanda**|Máxima flexibilidad, sin compromisos. Facturación por segundo. Ideal para cargas variables o impredecibles.|Aplicaciones de prueba, cargas con picos irregulares.|
|**Hosts dedicados**|Servidores físicos dedicados. Permiten aprovechar **licencias propias** (BYOL - Bring Your Own License).|Cumplimiento normativo, uso de licencias específicas.|
|**Instancias dedicadas**|Instancias en hardware físico aislado, exclusivo para un solo cliente.|Requisitos de aislamiento físico, normativas de seguridad estrictas.|
|**Instancias reservadas**|Compromiso de 1 o 3 años a cambio de descuentos de hasta un **75%**. Opción de **reservas programadas** para horarios fijos.|Cargas de trabajo estables y predecibles, entornos de producción.|
|**Instancias de spot**|Aprovechan capacidad no utilizada de EC2 con descuentos de hasta un **90%**. Precios variables según oferta y demanda.|Procesos batch, big data, machine learning, cargas tolerantes a interrupciones.|

!!! Info "¿Qué modelos permiten facturación por segundo?"

    → **Instancias bajo demanda, reservadas y spot** (solo en Amazon Linux y Ubuntu).

!!! Info "¿Cuál es el modelo de menor coste pero con riesgo de interrupción?"

    → **Instancias de spot**.

!!! Info "¿Qué modelo conviene para entornos de producción con uso estable?"

    → **Instancias reservadas** (1 o 3 años).

#### Optimización de costes en instancias EC2

Para reducir costes de forma eficiente es necesario revisar los siguientes factores:

|Factor|Descripción|
|---|---|
|**Adaptación del tamaño**|Seleccionar tipos de instancias adecuados. Utilizar **Amazon CloudWatch** para analizar métricas de rendimiento y evitar el sobredimensionamiento.|
|**Aumento de elasticidad**|Detener instancias cuando no se usan y habilitar **Auto Scaling** para ajustar recursos según la demanda.|
|**Modelo de precios óptimo**|Evaluar patrones de uso y combinar opciones de precios: **On-Demand, Reserved, Spot** o considerar soluciones **serverless** como **AWS Lambda**.|
|**Optimización de almacenamiento**|Ajustar el tamaño de volúmenes **EBS**, eliminar recursos no utilizados y revisar la configuración de almacenamiento para minimizar costes.|

!!! Info "¿Qué servicio permite identificar si una instancia está sobredimensionada?"

    → **Amazon CloudWatch**.

### Amazon CloudWatch

Servicio de **monitorización y observabilidad** de AWS para recopilar, visualizar y analizar métricas, logs y eventos en tiempo real.

|Componente|Función principal|
|---|---|
|**Métricas**|Recopila métricas de recursos AWS y personalizadas.|
|**Alarmas**|Configura alertas y automatiza respuestas.|
|**Logs**|Centraliza y analiza logs de aplicaciones.|
|**Dashboards**|Paneles visuales personalizados.|
|**Eventos**|Automatiza respuestas a eventos (EventBridge).|

!!! Info "¿Qué servicio permite crear alarmas automáticas basadas en métricas?"

    → **Amazon CloudWatch**.


### Elastic Container service (ECS)

* Servicio de administración de contenedores totalmente gestionado y escalable.
* Compatible con **Docker**.
* Permite desplegar miles de contenedores en minutos.
* Integrado con **Elastic Load Balancing**, **Security Groups**, **IAM Roles** y **volúmenes de almacenamiento**.

| Modo de ejecución | Descripción                                                                                           |
| ----------------- | ----------------------------------------------------------------------------------------------------- |
| **EC2**           | Los contenedores se ejecutan en instancias EC2 dentro de un clúster. Tú gestionas las instancias.     |
| **Fargate**       | **Serverless**: AWS gestiona la infraestructura. No necesitas aprovisionar ni administrar servidores. |

!!! Info "¿Qué opción de ECS elimina la necesidad de gestionar instancias EC2?"

    → **AWS Fargate**.

### Amazon Elastic Kubernetes Service (EKS)

* Servicio **gestionado de Kubernetes**.
* Permite ejecutar clústeres de Kubernetes sin preocuparse de la infraestructura del plano de control.
* Compatible con contenedores **Linux** y **Windows**.
* Funciona con las herramientas estándar de la comunidad de Kubernetes.

!!! Info "¿Qué servicio usarías si tu empresa ya trabaja con Kubernetes?"

    → **Amazon EKS**.

### Amazon Elastic Container Registry (ECR)

* Registro privado de contenedores completamente gestionado.
* Permite almacenar, administrar y desplegar **imágenes Docker** de forma segura y eficiente.
* Integración directa con **ECS**, **EKS** y **Fargate**.

!!! Info "¿Qué servicio facilita la gestión y despliegue de imágenes Docker en AWS?"

    → **Amazon ECR**.

### AWS Lambda

**AWS Lambda** es un servicio de **informática sin servidores (serverless)** que permite ejecutar código sin necesidad de gestionar servidores físicos o virtuales. La ejecución se activa en respuesta a **eventos** y AWS administra automáticamente los recursos necesarios.

#### Características principales

|Aspecto|Detalles|
|---|---|
|**Modelo de ejecución**|Basado en eventos (Event-driven).|
|**Modelo de pago**|Pago por uso, en incrementos de **100 ms**. Sin coste cuando no se ejecuta código.|
|**Lenguajes compatibles**|Java, Go, C#, Python, Node.js, entre otros.|
|**Alta disponibilidad**|Tolerante a fallos y escalabilidad automática.|
|**Integraciones nativas**|Con servicios como **S3, DynamoDB, SQS, API Gateway, CloudWatch**, entre otros.|
|**Orquestación de flujos**|Mediante **AWS Step Functions** para coordinar funciones Lambda.|

#### Ejemplos de activadores de Lambda

- Sube de archivos a **Amazon S3**.
- Nuevos registros en **DynamoDB Streams**.
- Mensajes en colas de **Amazon SQS**.
- Peticiones HTTP a través de **API Gateway**.

!!! Info "¿Cuándo se paga por AWS Lambda?"

    → Solo cuando se ejecuta el código, en bloques de **100 milisegundos**.

!!! Info "¿Qué servicio permite coordinar flujos de trabajo de múltiples funciones Lambda?"

    → **AWS Step Functions**.


### AWS Elastic Beanstalk

**AWS Elastic Beanstalk** es un servicio de tipo **PaaS (Platform as a Service)** que permite implementar, gestionar y escalar aplicaciones web de forma sencilla, sin preocuparse por la infraestructura subyacente.
#### Características principales

|Aspecto|Detalles|
|---|---|
|**Modelo de servicio**|PaaS (Plataforma como servicio).|
|**Gestión**|AWS se encarga de la infraestructura, balanceo de carga, escalado automático, monitoreo y logs.|
|**Modelo de pago**|Solo se paga por los recursos subyacentes (EC2, RDS, etc.), no por usar Beanstalk.|
|**Lenguajes soportados**|Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker.|
|**Entornos de ejecución**|Apache Tomcat, Apache HTTP Server, Nginx, Passenger, Puma, IIS, según el lenguaje.|
|**Escalabilidad**|Automática, según la demanda. Se puede seleccionar el tipo de instancia EC2.|

!!! Info "¿Qué responsabilidad mantiene el usuario al usar Elastic Beanstalk?"

    → Solo debe **desarrollar y subir el código**, AWS gestiona el resto.

!!! Info "¿Se paga por el uso de Elastic Beanstalk como servicio?"

    → **No**, solo por los recursos que consume (instancias EC2, almacenamiento, etc.).

## 3. Servicios de almacenamiento

### Amazon EBS (Elastic Block Store)

**Amazon EBS** es un servicio de **almacenamiento en bloques** diseñado para ser utilizado con instancias de **Amazon EC2**. Proporciona almacenamiento persistente, lo que significa que los datos se conservan incluso después de detener o finalizar una instancia.

#### Características principales

|Característica|Detalles|
|---|---|
|**Tipo de almacenamiento**|En bloques (Block Storage), similar a un disco duro tradicional.|
|**Persistencia**|Los datos se mantienen incluso si la instancia EC2 se apaga o termina.|
|**Replicación**|Automática dentro de la misma zona de disponibilidad para alta disponibilidad.|
|**Escalabilidad**|Se puede ampliar o reducir la capacidad en minutos.|
|**Modelo de pago**|Pago por el almacenamiento aprovisionado.|
|**Cifrado**|Disponible de forma nativa para todos los volúmenes.|

#### Tipos de volúmenes

|Tipo de volumen|Descripción|Casos de uso|
|---|---|---|
|**SSD (gp3, io1, io2)**|Alta IOPS y baja latencia.|Bases de datos, aplicaciones críticas, sistemas transaccionales.|
|**HDD (st1, sc1)**|Mayor capacidad a menor coste, rendimiento secuencial.|Big data, cargas de trabajo de acceso poco frecuente.|

#### Copias de seguridad

- Las copias de seguridad de EBS se llaman **instantáneas (Snapshots)**.
- Se almacenan en **Amazon S3** y permiten restaurar volúmenes o crear nuevas instancias EC2 a partir de ellas.
- Las **Amazon Machine Images (AMIs)** también incluyen los volúmenes EBS para facilitar la creación de nuevas instancias preconfiguradas.

!!! Info "¿Qué mecanismo se usa para realizar copias de seguridad de EBS?"

    → **Snapshots (instantáneas)**.

!!! Info "¿Qué tipo de almacenamiento usarías para bases de datos en EC2?"

    → **EBS con volúmenes SSD (gp3, io1, io2)**.


### Amazon S3 (Simple Storage Service)

**Amazon S3** es un servicio de **almacenamiento de objetos** completamente gestionado y altamente escalable. Permite almacenar y recuperar cualquier cantidad de datos desde cualquier lugar, sin necesidad de gestionar servidores.

#### Características principales

|Característica|Detalles|
|---|---|
|**Modelo de almacenamiento**|Basado en objetos (hasta **5 TB** por objeto).|
|**Durabilidad**|**99.999999999% (11 nueves)**.|
|**Seguridad**|Cifrado en reposo y en tránsito, acceso privado por defecto.|
|**Acceso**|Consola AWS, API, SDKs, CLI y herramientas de terceros.|
|**Escalabilidad**|Automática y sin límite práctico de almacenamiento.|
|**Notificaciones**|Puede generar eventos para notificar o activar procesos (ej. AWS Lambda).|

#### Clases de almacenamiento de S3

| Clase                        | Uso recomendado                           | Latencia        | Coste                        |
| ---------------------------- | ----------------------------------------- | --------------- | ---------------------------- |
| S3 Standard                  | Acceso frecuente a datos activos.         | Milisegundos    | Alto                         |
| S3 Intelligent-Tiering (INT) | Datos con patrones de acceso variables.   | Milisegundos    | Variable                     |
| S3 Standard-IA (S-IA)        | Datos poco accedidos, acceso rápido.      | Milisegundos    | Bajo (+ fee de recuperación) |
| S3 One Zone-IA (Z-IA)        | Datos infrecuentes, menor disponibilidad. | Milisegundos    | Más bajo                     |
| S3 Glacier                   | Archivado a largo plazo.                  | Minutos / Horas | Muy bajo                     |
| S3 Glacier Deep Archive      | Archivado muy a largo plazo.              | Horas           | Más económico                |

!!! Info "¿Qué clase de almacenamiento es ideal para copias de seguridad antiguas que rara vez se consultan?"

    → **S3 Glacier Deep Archive**.

!!! Info "¿Los buckets de S3 son públicos por defecto?"

    → **No**, por defecto son privados y requieren configuraciones explícitas para acceso público.


### Amazon EFS (Elastic File System)

Amazon EFS es un servicio de almacenamiento en la nube de tipo sistema de archivos que proporciona un almacenamiento compartido, escalable y totalmente gestionado. Permite a múltiples instancias EC2 y otros servicios de AWS acceder de forma simultánea a los mismos archivos.

#### Características principales

|Característica|Detalles|
|---|---|
|Modelo de almacenamiento|Sistema de archivos (NFS).|
|Escalabilidad|Automática, desde gigabytes hasta petabytes.|
|Acceso simultáneo|Cientos de instancias EC2 pueden acceder al mismo sistema de archivos.|
|Casos de uso|Big data, análisis, procesamiento multimedia, servidores web, almacenamiento de directorios.|
|Alta disponibilidad|Sí, datos replicados entre zonas de disponibilidad.|
|Modelo de pago|Pago solo por el almacenamiento utilizado, sin tarifas mínimas.|

!!! Info "¿Qué servicio de almacenamiento permite acceso compartido a través de NFS?"

    → Amazon EFS.

!!! Info "¿Cómo se factura EFS?"

    → Solo por el almacenamiento utilizado, sin costes de aprovisionamiento.

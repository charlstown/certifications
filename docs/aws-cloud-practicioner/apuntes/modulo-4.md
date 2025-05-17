# M4 - Facturación, precios y soporte


### Servicios de Cómputo en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**Amazon EC2**|Proporciona **capacidad de cómputo escalable** en forma de máquinas virtuales.|Despliegue de aplicaciones, servidores web, bases de datos.|
|**Amazon EC2 Auto Scaling**|Permite **ajustar automáticamente** la cantidad de instancias EC2 en función de la demanda.|Mantener alta disponibilidad, escalabilidad automática.|
|**Amazon ECS**|Servicio de **gestión de contenedores** compatible con Docker, altamente escalable.|Orquestación de contenedores, microservicios.|
|**Amazon ECR**|**Registro gestionado de imágenes Docker**, facilita almacenar, administrar e implementar contenedores.|Almacenamiento y despliegue de imágenes de contenedores.|
|**AWS Elastic Beanstalk**|Servicio PaaS para **implementar y escalar aplicaciones web** rápidamente sin gestionar la infraestructura.|Aplicaciones web en servidores como Apache o IIS.|
|**AWS Lambda**|Servicio **serverless** para ejecutar código en respuesta a eventos, sin necesidad de gestionar servidores.|Automatización, APIs, procesamiento de eventos.|
|**Amazon EKS**|Servicio de **gestión de clústeres Kubernetes** totalmente administrado.|Orquestación de contenedores con Kubernetes.|
|**AWS Fargate**|Motor informático **serverless para contenedores**. Permite ejecutar contenedores sin gestionar servidores o clústeres.|Ejecución de microservicios en contenedores sin preocuparse por la infraestructura.|
|**AWS Serverless Application Repository**|Permite **descubrir, implementar y publicar aplicaciones serverless**.|Reutilización de aplicaciones sin servidor, aceleración del desarrollo.|

!!! Info "¿Qué servicio de AWS permite ejecutar contenedores sin necesidad de gestionar servidores o clústeres?"

    → **AWS Fargate**.

### Servicios de Almacenamiento y Bases de Datos en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**Amazon EBS**|Almacenamiento **persistente en bloques** para instancias EC2.|Volúmenes de discos para EC2, almacenamiento de bases de datos.|
|**Amazon S3**|Almacenamiento **de objetos** altamente escalable y accesible mediante URL.|Almacenamiento de archivos, backups, hosting de contenido estático.|
|**Clases de Amazon S3**|- **S3 Estándar**: Acceso frecuente. - **S3 Intelligent-Tiering**: Acceso con patrones variables. - **S3 Estándar - IA**: Acceso poco frecuente. - **S3 One Zone - IA**: Acceso poco frecuente en una sola AZ. - **S3 Glacier**: Archivado a largo plazo. - **S3 Glacier Deep Archive**: Archivado de muy largo plazo.|Gestión de datos por frecuencia de acceso, optimización de costes.|
|**Amazon EFS**|Sistema de archivos **compartido** y elástico, accesible desde múltiples instancias EC2 mediante NFS.|Almacenamiento compartido entre aplicaciones, directorios de usuarios.|
|**Amazon RDS**|Servicio gestionado de **bases de datos relacionales**.|Aplicaciones que requieren bases de datos SQL (MySQL, PostgreSQL, Oracle, SQL Server, Aurora).|
|**Amazon DynamoDB**|Base de datos **NoSQL rápida y totalmente gestionada**, con baja latencia en milisegundos.|Aplicaciones de alta demanda, juegos, IoT, almacenamiento de sesiones.|

!!! Info "¿Qué servicio de AWS permite almacenar archivos en forma de objetos y acceder a ellos mediante URL?"

    → **Amazon S3**.

### Servicios de Control y Gobernanza en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**AWS Cost Explorer**|Permite **visualizar y gestionar los costes y uso de AWS** a través de informes interactivos.|Análisis de costes, identificación de tendencias de gasto.|
|**AWS Budgets**|Servicio para **gestionar presupuestos** y generar alertas mediante **Amazon SNS** al superar ciertos umbrales de gasto.|Control de presupuestos, alertas proactivas de costes.|
|**AWS Cost & Usage Report**|Proporciona **informes detallados de uso y costes** a nivel de cuenta u organización, con desglose por hora, día o mes.|Auditorías de costes, análisis de facturación detallada.|
|**Amazon CloudWatch**|Servicio de **monitoreo de recursos y aplicaciones**. Permite crear alarmas, visualizar métricas y responder a eventos en tiempo real.|Supervisión de rendimiento, automatización basada en métricas.|
|**AWS CloudTrail**|Realiza un **seguimiento de la actividad de los usuarios y del uso de la API** de AWS.|Auditorías de seguridad, análisis de eventos y actividades sospechosas.|
|**AWS Config**|Permite realizar un **seguimiento de los recursos de AWS y sus cambios de configuración**.|Auditorías de cumplimiento, inventario de recursos.|
|**AWS Auto Scaling**|Ajusta de forma automática la capacidad de los recursos para **mantener un rendimiento estable** al menor coste.|Optimización de recursos, escalabilidad de aplicaciones.|
|**Amazon EC2 Auto Scaling**|Ajusta automáticamente la cantidad de **instancias EC2** en función de la demanda para garantizar la disponibilidad.|Alta disponibilidad y optimización de costes en EC2.|
|**Elastic Load Balancing**|Distribuye automáticamente el **tráfico de red y de aplicaciones entre múltiples destinos**.|Balanceo de carga, alta disponibilidad de aplicaciones web.|

!!! Info "¿Qué servicio de AWS permite realizar un seguimiento de la actividad de los usuarios y llamadas a la API?"

    → **AWS CloudTrail**.


### Servicios de Seguridad y Gestión en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**Amazon GuardDuty**|Servicio de **detección de amenazas** que analiza registros de AWS para identificar actividades maliciosas.|Detección proactiva de amenazas, análisis de logs de seguridad.|
|**Amazon Inspector**|**Evalúa la seguridad de las instancias EC2** y aplicaciones, buscando vulnerabilidades.|Análisis de vulnerabilidades, comprobación de configuraciones de seguridad.|
|**Amazon Macie**|Utiliza **machine learning para proteger datos confidenciales** almacenados en S3.|Identificación de datos personales o sensibles, protección de información.|
|**AWS Artifact**|Proporciona acceso a **informes de conformidad y seguridad** de AWS.|Auditorías de seguridad, gestión de cumplimiento normativo.|
|**AWS Certificate Manager**|Servicio para **gestionar certificados SSL/TLS**, facilitando la creación, renovación y despliegue.|Cifrado de comunicaciones, gestión de certificados digitales.|
|**AWS Secrets Manager**|Servicio para **gestionar credenciales y secretos** de forma segura.|Almacenamiento seguro de contraseñas, tokens de API, claves de bases de datos.|
|**AWS Shield**|Protección automática contra **ataques DDoS**. Incluye una versión básica gratuita y otra avanzada.|Protección contra denegación de servicio, mitigación de ataques en aplicaciones web.|
|**Amazon Cognito**|Gestión de **identidades y acceso de usuarios** en aplicaciones web y móviles.|Autenticación de usuarios, control de acceso con SSO y federación de identidades.|
|**AWS Amplify**|Conjunto de herramientas para **desarrollo de aplicaciones frontend** web y móviles con marcos como React, Angular y Vue.|Desarrollo de aplicaciones modernas con autenticación, APIs y almacenamiento.|

!!! Info "¿Qué servicio de AWS permite gestionar y almacenar de forma segura contraseñas y claves de acceso?"

    → **AWS Secrets Manager**.

### Servicios de Analytics en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**Amazon Athena**|Permite **consultar directamente datos en S3** usando **SQL estándar** sin necesidad de cargar los datos en una base de datos.|Análisis ad-hoc sobre grandes volúmenes de datos en S3, consultas rápidas sin ETL.|
|**Amazon EMR**|Plataforma de **Big Data totalmente gestionada** que permite procesar grandes volúmenes de datos utilizando frameworks como **Apache Spark, Hive, Hadoop, Presto**.|Procesamiento de grandes datasets, machine learning, análisis de logs.|
|**Amazon Kinesis**|Servicio completamente gestionado para **procesamiento y análisis de datos en tiempo real**. Permite capturar, procesar y analizar flujos de datos a escala.|Análisis de clics en tiempo real, detección de fraudes, monitoreo en vivo.|
|**Amazon QuickSight**|Herramienta de **Business Intelligence sin servidor** que permite crear paneles y reportes interactivos de forma rápida.|Visualización de datos, creación de dashboards empresariales, análisis interactivos.|
|**AWS Glue**|Servicio de **integración de datos y ETL gestionado**, que permite preparar, transformar y mover datos de forma sencilla. Basado en código (Spark y Python).|Integraciones ETL, catálogos de datos, transformación y limpieza de datos antes del análisis.|

!!! Info "¿Qué servicio de AWS permite realizar consultas directas sobre datos en S3 usando SQL sin necesidad de mover los datos?"

    → **Amazon Athena**.


### Integración de Aplicaciones en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**AWS Step Functions**|Permite **orquestar flujos de trabajo** de forma visual, facilitando la secuenciación de tareas, especialmente con **AWS Lambda** y otros servicios.|Automatización de procesos, flujos de datos entre servicios, microservicios coordinados.|
|**Amazon MQ**|Servicio de **mensajería gestionado** compatible con **Apache ActiveMQ y RabbitMQ**. Facilita la migración de aplicaciones que usan protocolos de mensajería estándar.|Integración de sistemas legacy, migración de entornos on-premises, mensajería empresarial.|
|**Amazon SQS**|Servicio de **colas de mensajes completamente gestionado** para desacoplar componentes de aplicaciones y escalar de forma independiente.|Procesamiento asíncrono, desacoplamiento de microservicios, colas de trabajo.|
|**Amazon SNS**|Servicio de **notificaciones push y mensajería**. Permite enviar mensajes a **móviles, correo electrónico, SMS, HTTP/S** y activar otros servicios como Lambda.|Envío de alertas, notificaciones de eventos, difusión de mensajes a múltiples suscriptores.|

!!! Info "¿Qué servicio de AWS permite coordinar la ejecución de varios servicios a través de flujos de trabajo visuales?"

→ **AWS Step Functions**.



### Herramientas de Desarrollo y DevOps en AWS

|Servicio|Descripción|Casos de uso principales|
|---|---|---|
|**AWS CodeCommit**|Servicio para **alojar repositorios privados basados en Git** de forma segura y escalable.|Control de versiones, colaboración en equipos de desarrollo, almacenamiento de código fuente.|
|**AWS CodeBuild**|Servicio de **integración continua** que compila código fuente, ejecuta pruebas y genera paquetes listos para despliegue.|Automatización de compilaciones, pruebas unitarias, generación de artefactos de despliegue.|
|**AWS CodeDeploy**|Servicio que **automatiza las implementaciones de software** en EC2, Fargate y entornos on-premises.|Despliegue continuo, actualizaciones sin tiempo de inactividad, automatización de releases.|
|**AWS Cloud9**|**IDE en la nube** que permite escribir, ejecutar y depurar código desde cualquier navegador.|Desarrollo remoto, colaboración en tiempo real, entornos de desarrollo preconfigurados.|

!!! Info "¿Qué servicio de AWS permite automatizar las implementaciones de software en entornos de nube e instalaciones locales?"

    → **AWS CodeDeploy**.


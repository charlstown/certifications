# M3 - Servicios principales

## 1. Servicios de bases de datos

### Amazon RDS (Relational Database Service)

Amazon RDS es un servicio **gestionado de bases de datos relacionales** que simplifica la configuración, operación y escalado de bases de datos en la nube. Permite a los desarrolladores centrarse en las aplicaciones, mientras AWS se encarga de las tareas administrativas.

#### Características principales

| Característica       | Descripción                                                                                   |
| -------------------- | --------------------------------------------------------------------------------------------- |
| Modelo de servicio   | Base de datos como servicio (DBaaS).                                                          |
| Tareas automatizadas | Instalación, parches, backups, replicación y alta disponibilidad.                             |
| Escalabilidad        | Vertical (más CPU/RAM) y horizontal (réplicas de lectura).                                    |
| Seguridad            | Cifrado en reposo y en tránsito, integración con IAM.                                         |
| Facturación          | Por hora de uso, tipo de instancia, almacenamiento y operaciones de I/O.                      |
| Modos de compra      | Instancias bajo demanda o reservadas (1 o 3 años).                                            |
| Motores              | - MySQL<br>- PostgreSQL<br>- MariaDB<br>- Oracle<br>- Microsoft SQL Server<br>- Amazon Aurora |

#### ¿Cuándo usar Amazon RDS?

- Aplicaciones que requieren transacciones o consultas complejas.
- Necesidad de alta durabilidad y disponibilidad.
- Tasa de consultas o escrituras **media a alta** (hasta 30,000 IOPS).

#### ¿Cuándo no usar Amazon RDS?

- Aplicaciones con tasas de lectura o escritura **muy altas** (ej. 150,000 escrituras por segundo).
- Necesidad de fragmentación compleja o personalización avanzada del motor de base de datos.
- Casos donde una base de datos **NoSQL** es más adecuada (consultas simples tipo GET/PUT).

!!! Info "¿Qué servicio de AWS permite crear réplicas de lectura en otra región?"

    → **Amazon RDS** (para MySQL, MariaDB, PostgreSQL y Aurora).

!!! Info "¿Cómo se factura Amazon RDS?"

    → Por horas de uso, características de la instancia (motor, tamaño, memoria) y operaciones de e

### Amazon DynamoDB

Amazon DynamoDB es un servicio de **base de datos NoSQL totalmente gestionado**, diseñado para aplicaciones que requieren **baja latencia y alta escalabilidad**, con tiempos de respuesta en milisegundos incluso a gran escala.

#### Características principales

|Característica|Descripción|
|---|---|
|Modelo de datos|NoSQL (almacenamiento de documentos clave-valor y tablas).|
|Escalabilidad|Automática y sin límite práctico de tamaño de tablas o elementos.|
|Latencia|Baja, uniforme en milisegundos de un solo dígito.|
|Rendimiento|Ajustable de forma automática o mediante aprovisionamiento manual.|
|Seguridad|Cifrado en reposo, en tránsito e integración con IAM.|
|Facturación|Basada en capacidad de lectura/escritura (On-Demand o Provisioned) y almacenamiento utilizado.|

#### Componentes de DynamoDB

|Componente|Descripción|
|---|---|
|Tabla|Almacena los datos.|
|Elemento|Registro individual dentro de la tabla.|
|Atributo|Campo de datos dentro de un elemento (similar a una columna).|

#### Tipos de claves principales

| Tipo de clave de partición | Descripción                                                                      |
| -------------------------- | -------------------------------------------------------------------------------- |
| Clave única                | Clave simple, define la partición de datos.                                      |
| Clave compuesta            | Clave de partición + clave de ordenamiento (permite ordenar y consultar rangos). |

!!! Info "¿Qué modelo de base de datos permite escalabilidad automática sin límite de tamaño?"

    → **Amazon DynamoDB**.

!!! Info "¿Qué tipo de clave principal permite ordenar los resultados de una consulta en DynamoDB?"

    → **Clave compuesta** (clave de partición + clave de ordenamiento).

### Amazon Redshift

Amazon Redshift es un servicio de **almacenamiento de datos (Data Warehouse) totalmente gestionado** que permite realizar análisis complejos de grandes volúmenes de datos de forma rápida y rentable, utilizando **SQL estándar** y herramientas de Business Intelligence (BI) existentes.

#### Características principales

|Característica|Descripción|
|---|---|
|Tipo de servicio|Almacenamiento de datos (Data Warehouse).|
|Consultas|Analíticas complejas sobre **petabytes** de datos.|
|Rendimiento|Alta velocidad gracias a almacenamiento en columnas y ejecución en paralelo (MPP - Massive Parallel Processing).|
|Redshift Spectrum|Permite consultar directamente datos en **Amazon S3** sin cargarlos en Redshift.|
|Seguridad|Cifrado de datos en reposo y en tránsito, integración con IAM y VPC.|
|Facturación|Pago por uso, según el almacenamiento y la capacidad de cómputo utilizada.|

!!! Info "¿Qué característica de Redshift permite consultar datos directamente en S3?"

    → **Amazon Redshift Spectrum**.

!!! Info "¿Qué modelo de ejecución permite a Redshift procesar consultas de forma rápida en grandes volúmenes de datos?"

    → **Procesamiento masivo en paralelo (MPP)**.


### Amazon Aurora

Amazon Aurora es un **servicio de base de datos relacional completamente gestionado**, diseñado para ofrecer un alto rendimiento y disponibilidad. Es compatible con **MySQL y PostgreSQL**, y combina la facilidad de un servicio gestionado con la eficiencia de una base de datos empresarial optimizada para la nube.

#### Características principales

|Característica|Descripción|
|---|---|
|Compatibilidad|Compatible con **MySQL** y **PostgreSQL**.|
|Alta disponibilidad|Almacena múltiples copias de los datos en varias zonas de disponibilidad.|
|Réplicas de lectura|Soporta hasta **15 réplicas de lectura** para mejorar la escalabilidad y disponibilidad.|
|Seguridad|Cifrado en tránsito y en reposo, backups continuos en Amazon S3.|
|Recuperación rápida|Detección automática de fallos y recuperación instantánea.|
|Integración|Compatible con **AWS DMS** y **AWS Schema Conversion Tool** para migraciones y conversiones de bases de datos.|
|Facturación|Pago por uso, solo por los recursos y características consumidas.|

!!! Info "¿Qué ventaja ofrece Amazon Aurora frente a otras bases de datos en términos de recuperación?"

    → Recuperación de errores **instantánea** si la base de datos principal falla.

!!! Info "¿Cuántas réplicas de lectura permite Aurora?"

    → Hasta **15 réplicas de lectura**.

### Amazon ElastiCache

Amazon ElastiCache es un servicio completamente gestionado que permite **implementar almacenes de datos en memoria** para mejorar el rendimiento de las aplicaciones al reducir la latencia en el acceso a los datos.

#### Características principales

| Característica     | Descripción                                                                            |
| ------------------ | -------------------------------------------------------------------------------------- |
| Modelo de servicio | Almacén de datos en memoria, completamente gestionado.                                 |
| Motores soportados | **Redis** y **Memcached**.                                                             |
| Latencia           | Acceso a datos en **milisegundos o microsegundos**.                                    |
| Escalabilidad      | Automática, ajusta la capacidad según la demanda.                                      |
| Casos de uso       | Caché de consultas, gestión de sesiones, contadores en tiempo real, colas de mensajes. |
| Integración        | Fácil integración con **EC2**, **RDS**, **DynamoDB** y **Lambda**.                     |
| Modelo de pago     | Pago por uso de los nodos de caché.                                                    |

#### ¿Cuándo usar ElastiCache?

- Para acelerar consultas de bases de datos con **datos que no cambian frecuentemente**.
- Al gestionar **sesiones de usuario** en aplicaciones web.
- En casos de uso de **ranking, contadores en tiempo real, colas de mensajes** o **sistemas de recomendación**.

!!! Info "¿Qué motor de ElastiCache elegirías para soportar persistencia de datos en memoria?"

    → **Redis**.

!!! Info "¿Qué motor elegirías si solo necesitas una caché simple sin replicación?"

    → **Memcached**.

## 2. Arquitectura en la nube de AWS

### El Marco de Buena Arquitectura de AWS

El Marco de Buena Arquitectura de AWS es una guía oficial diseñada para ayudar a las organizaciones a crear aplicaciones y cargas de trabajo en la nube con la **máxima seguridad, alto rendimiento, resiliencia y eficiencia de costes**.

Se basa en cinco pilares fundamentales, cada uno con principios de diseño y prácticas recomendadas.

#### Pilares del Marco de Buena Arquitectura

1. **Excelencia Operativa**: Optimizar la gestión y automatización de las operaciones para ofrecer valor de negocio de forma continua.
2. **Seguridad**: Proteger los datos y sistemas mediante controles de acceso, cifrado y monitoreo constante.
3. **Fiabilidad**: Garantizar la recuperación ante fallos y mantener la continuidad del servicio mediante arquitecturas resilientes.
4. **Eficiencia del Rendimiento**: Utilizar los recursos de forma eficiente, adaptando la capacidad a la demanda para maximizar el rendimiento.
5. **Optimización de Costes**: Controlar y reducir costes utilizando modelos de consumo y eliminando recursos innecesarios.

!!! Info "Una empresa busca reducir los costes operativos eliminando la gestión manual de bases de datos, adoptando servicios gestionados, y trasladando sus cargas de trabajo a modelos de pago por uso. ¿Qué pilar está aplicando principalmente?"

    → **Optimización de Costes**.

!!! Info "Durante una auditoría, se identifica que los desarrolladores tienen acceso directo a bases de datos productivas. La empresa implementa un sistema de roles estrictos y habilita registros de auditoría. ¿Qué pilar está reforzando?"

    → **Seguridad**.

### Fiabilidad y Disponibilidad en AWS

Dentro del Marco de Buena Arquitectura de AWS, se recomienda **planificar los errores** y diseñar sistemas que se mantengan operativos incluso ante fallos. Esto se aborda a través de los conceptos de **fiabilidad** y **alta disponibilidad**.

#### Fiabilidad

|Concepto|Descripción|
|---|---|
|¿Qué mide?|Capacidad de un sistema para funcionar correctamente cuando se necesita.|
|Métrica clave|**MTBF (Mean Time Between Failures)**: tiempo promedio entre fallos.|
|Objetivo|Reducir la frecuencia de errores, aunque no implica necesariamente alta disponibilidad.|

#### Disponibilidad

|Concepto|Descripción|
|---|---|
|¿Qué mide?|Porcentaje de tiempo que un sistema está operativo y funcionando según lo esperado.|
|Incluye|Tanto interrupciones no planificadas como las programadas.|
|Forma de expresión|Porcentaje de “nueves”: 99.9%, 99.99%, 99.999%, etc.|

|Disponibilidad|Tiempo de inactividad anual aproximado|
|---|---|
|99.9% (Tres nueves)|8 horas 45 minutos|
|99.99% (Cuatro nueves)|52 minutos|
|99.999% (Cinco nueves)|5 minutos (**Alta disponibilidad**)|

#### Factores que afectan a la disponibilidad

|Factor|Descripción|
|---|---|
|Tolerancia a errores|Redundancia integrada para seguir operando aunque fallen componentes.|
|Escalabilidad|Capacidad de adaptarse a cambios en la demanda de recursos.|
|Capacidad de recuperación|Rapidez con la que el sistema se recupera tras un fallo, sin pérdida de datos.|

!!! Info "¿Qué factor permite que un sistema continúe operando correctamente incluso si falla uno de sus componentes?"

    → **Tolerancia a errores**.


### AWS Trusted Advisor

AWS Trusted Advisor es una herramienta que proporciona **recomendaciones automáticas** para ayudarte a optimizar los recursos de AWS en cinco áreas clave:

|Área|Descripción|
|---|---|
|Coste|Sugerencias para reducir gastos.|
|Seguridad|Recomendaciones para mejorar la seguridad de tus recursos.|
|Tolerancia a fallos|Identifica configuraciones para mejorar la disponibilidad.|
|Rendimiento|Ayuda a mejorar la eficiencia de los recursos.|
|Límites de servicio|Informa sobre los límites alcanzados en los servicios de AWS.|

Trusted Advisor revisa la configuración de tu cuenta y destaca oportunidades de mejora para hacer tus entornos **más seguros, eficientes y económicos**.

!!! Info "Pregunta de examen: ¿Qué herramienta de AWS te ayuda a identificar oportunidades de ahorro de costes y mejora de seguridad?"

    → **AWS Trusted Advisor**.

## 3. Monitoreo y escalado automático

### Elastic Load Balancing (ELB)

AWS Elastic Load Balancing es un servicio que distribuye automáticamente el tráfico de red y de aplicaciones entre múltiples destinos, como **instancias EC2**, **contenedores**, **funciones Lambda** o direcciones IP. Permite manejar cargas de trabajo de forma eficiente, asegurando alta disponibilidad y escalabilidad.

|Característica|Descripción|
|---|---|
|Distribución de tráfico|Equilibra el tráfico entrante entre varios destinos.|
|Alta disponibilidad|Funciona en una o varias zonas de disponibilidad.|
|Escalabilidad|Ajusta la capacidad automáticamente según la carga de tráfico.|
|Destinos soportados|EC2, contenedores, IPs, funciones Lambda.|

#### Monitoreo y análisis de ELB

|Herramienta|Descripción|
|---|---|
|Amazon CloudWatch|Proporciona métricas para supervisar el rendimiento y comportamiento del balanceador.|
|Registros de acceso|Almacenan información detallada de las solicitudes en Amazon S3.|
|AWS CloudTrail|Registra las llamadas a la API de ELB, incluyendo quién realizó la acción y desde qué IP.|

!!! Info "¿Qué servicio de AWS permite distribuir automáticamente el tráfico de aplicaciones entre varias instancias y servicios?"

    → **Elastic Load Balancing (ELB)**.

### Amazon CloudWatch

Amazon CloudWatch es un servicio de **monitoreo en tiempo real** que permite supervisar recursos de AWS y aplicaciones personalizadas. Proporciona visibilidad sobre la utilización de recursos, rendimiento de las aplicaciones y estado operativo del sistema.

|Característica|Descripción|
|---|---|
|Monitoreo de recursos|Supervisa servicios como EC2, ELB, DynamoDB, SQS, y métricas personalizadas.|
|Alarmas|Permite crear alarmas para automatizar acciones (escalado, reinicio de instancias) o enviar notificaciones con **Amazon SNS**.|
|Integración|Compatible con **Auto Scaling**, **SNS**, **EC2** y otros servicios.|
|Pago por uso|Sin compromisos iniciales ni tarifas mínimas; solo se paga por lo que se consume.|

#### Ejemplos de uso de alarmas

|Caso de uso|Ejemplo de alarma configurada|
|---|---|
|Uso de CPU en EC2|Enviar alerta si supera el 80%.|
|Latencia en ELB|Crear alarma si la latencia es alta.|
|Carga en DynamoDB|Detectar bajo rendimiento.|
|Longitud de colas en SQS|Activar notificación si hay demasiados mensajes pendientes.|
|Control de gastos|Crear alarma sobre los cargos en la factura de AWS.|

!!! Info "¿Qué servicio permite crear alarmas para supervisar el uso de recursos y automatizar acciones como escalado o envío de notificaciones?"

    → **Amazon CloudWatch**.

### Amazon EC2 Auto Scaling

Amazon EC2 Auto Scaling permite **ajustar automáticamente la capacidad de cómputo** de una aplicación para mantener su disponibilidad y eficiencia de costes. Puede aumentar o reducir el número de instancias EC2 en función de la demanda, sin necesidad de intervención manual.

|Característica|Descripción|
|---|---|
|Escalado automático|Agrega o elimina instancias EC2 según las condiciones definidas (como uso de CPU o tráfico).|
|Alta disponibilidad|Mantiene la cantidad mínima de instancias activas para asegurar la operación del servicio.|
|Modos de escalado|Manual, programado o basado en demanda.|
|Escalado predictivo|Ajusta la capacidad anticipándose a los cambios de carga, utilizando inteligencia predictiva.|

#### Conceptos clave en Auto Scaling

|Concepto|Descripción|
|---|---|
|Minimum Size|Número mínimo de instancias en ejecución.|
|Desired Capacity|Cantidad de instancias que se intenta mantener normalmente.|
|Maximum Size|Número máximo de instancias que pueden ejecutarse.|
|Scale Out|Agregar instancias cuando la carga aumenta.|
|Scale In|Eliminar instancias cuando la carga disminuye.|

!!! Info "¿Qué valor define la cantidad máxima de instancias que puede ejecutar un grupo de Auto Scaling?"

    → **Maximum Size**.

## 4. Planes de soporte y herramientas de gestión

### AWS Support

AWS ofrece diferentes planes de soporte adaptados a las necesidades de los clientes, desde entornos de prueba hasta cargas de trabajo críticas en producción. Además, proporciona herramientas como **AWS Trusted Advisor** para optimizar costes, seguridad y rendimiento.

|Plan de soporte|Descripción|
|---|---|
|**Basic**|Acceso al centro de recursos 24/7, panel de estado de servicio, 6 comprobaciones de Trusted Advisor, foros de debate y acceso a **AWS Personal Health Dashboard**.|
|**Developer**|Soporte para entornos de desarrollo y cargas de trabajo no productivas. Incluye orientación y buenas prácticas.|
|**Business**|Soporte para cargas de trabajo en producción. Permite acceso a expertos y tiempos de respuesta reducidos.|
|**Enterprise**|Soporte para cargas de trabajo críticas, con acceso a **Technical Account Manager (TAM)** y soporte proactivo.|

#### Recursos adicionales de soporte

|Recurso|Descripción|
|---|---|
|**Trusted Advisor**|Ofrece recomendaciones sobre seguridad, optimización de costes y rendimiento.|
|**TAM (Technical Account Manager)**|Contacto principal en planes avanzados (Business y Enterprise) para revisión de arquitecturas y optimización de soluciones.|
|**Concierge Support Team**|Expertos en gestión de cuentas y facturación, ayudan con análisis rápidos y eficaces.|

!!! Info "¿Qué plan de soporte de AWS proporciona acceso a un Technical Account Manager (TAM)?"

    → **Enterprise**.

### Herramientas de Gestión de AWS

AWS proporciona un conjunto de herramientas que permiten **provisionar, monitorizar y automatizar la gestión de entornos en la nube**, facilitando la adopción de prácticas de **Infrastructure as Code (IaC)** y automatización operativa.

|Herramienta|Descripción|
|---|---|
|**AWS CloudFormation**|Permite modelar y aprovisionar recursos de AWS y de terceros utilizando plantillas declarativas. Facilita la gestión de infraestructuras como código y el despliegue consistente de entornos.|
|**AWS Systems Manager**|Ofrece una consola centralizada para visualizar datos operativos y automatizar tareas en recursos como EC2, EKS, S3 y RDS. Permite gestionar inventarios, aplicar parches y ejecutar comandos remotos.|
|**AWS OpsWorks**|Servicio de gestión de configuración basado en **Chef** y **Puppet**. Permite automatizar la configuración, implementación y administración de servidores tanto en AWS como en entornos on-premises.|

!!! Info "¿Qué herramienta de AWS permite gestionar la infraestructura como código mediante plantillas?"

    → **AWS CloudFormation**.

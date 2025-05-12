# M1 - Conceptos de la nube

## 1. Descripción de la Nube AWS
### Introducción

#### Modelos de servicio en la nube

| Modelo | ¿Qué ofrece?           | Ejemplos en AWS                                       | Responsabilidad del cliente            |
| ------ | ---------------------- | ----------------------------------------------------- | -------------------------------------- |
| IaaS   | Infraestructura básica | EC2, EBS, S3 (cuando se usa como almacenamiento puro) | Sistema operativo, aplicaciones, datos |
| PaaS   | Plataforma gestionada  | Lambda, Elastic Beanstalk, RDS, Fargate               | Código y datos de la aplicación        |
| SaaS   | Aplicación completa    | WorkMail, Chime, AWS Managed Microsoft AD             | Solo configuración y uso               |

!!! info "¿A qué modelo pertenece Amazon RDS?"

    → RDS es **PaaS**, ya que AWS gestiona la base de datos subyacente.  
    → No es IaaS porque no gestionas el sistema operativo ni la base de datos directamente.

#### Implementaciones en la nube

|Tipo de implementación|Descripción|Ejemplos en AWS|
|---|---|---|
|Nube pública|Toda la infraestructura es de AWS|EC2, Lambda, S3|
|Nube privada|Infraestructura dedicada, gestionada localmente o por AWS|AWS Outposts, VMware Cloud on AWS|
|Nube híbrida|Combina infraestructura on-premises y en la nube|AWS Direct Connect, Storage Gateway|

!!! info "¿Qué servicio permite una conexión privada y de baja latencia entre on-premises y AWS?"

    → **AWS Direct Connect** (no confundir con VPN, que es más barata pero no garantiza baja latencia).


### Ventajas de migrar a la nube

| Ventaja                              | Descripción                                                                                           |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Cambio de **CAPEX** a **OPEX**       | Se sustituyen grandes inversiones en infraestructura (CAPEX) por gastos variables controlados (OPEX). |
| Economías de escala                  | Al haber más clientes, los proveedores pueden ofrecer precios más bajos.                              |
| Sin necesidad de estimar capacidad   | Se pueden ajustar los recursos de forma dinámica según la demanda.                                    |
| Aumento de velocidad y agilidad      | Los recursos se despliegan en minutos en lugar de semanas.                                            |
| Reducción de costes de mantenimiento | No es necesario gestionar centros de datos; se puede enfocar en el negocio.                           |
| Expansión global en minutos          | Con AWS, es posible desplegar servicios en múltiples regiones con baja latencia y menor coste.        |

!!! info "¿Qué ventaja económica clave impulsa la migración a la nube?"

    → El cambio de **CAPEX a OPEX** permite a las empresas evitar grandes inversiones iniciales y pagar solo por lo que consumen.

### Introducción a Amazon Web Services

#### Interacción con los servicios

|Opción de interacción|Descripción|
|---|---|
|Consola de administración|Interfaz gráfica web. Intuitiva y fácil de usar, pensada para tareas puntuales o exploración.|
|CLI (Command Line Interface)|Herramienta de línea de comandos, útil para automatizar tareas y scripting.|
|SDKs|Conjuntos de librerías para lenguajes como Python (Boto3), Java, JavaScript, etc.|

!!! info "¿En qué se basan las tres opciones de interacción con AWS?"

    → Todas usan **la API REST de AWS** como base para ejecutar operaciones sobre los servicios.

!!! info "¿Qué herramienta es ideal para tareas automatizadas o integraciones en scripts?"

    → La **CLI de AWS** permite interactuar con servicios mediante scripts en bash, PowerShell, etc.

#### Adopción de la nube

AWS proporciona un marco llamado **AWS Cloud Adoption Framework (AWS CAF)**.

- Su objetivo es ayudar a las organizaciones a **planificar y estructurar la adopción de la nube**.
- Define **6 perspectivas**, que cubren diferentes áreas funcionales de una empresa.

|Perspectiva|Enfoque principal|
|---|---|
|Business|Alineación con objetivos de negocio|
|People|Preparación del personal y habilidades|
|Governance|Gestión de riesgos, cumplimiento, políticas|
|Platform|Infraestructura, herramientas y servicios|
|Security|Protección de datos, identidad y acceso|
|Operations|Gestión de operaciones y monitoreo|

!!! info "¿Qué es AWS CAF y para qué sirve?"

    → Es un marco de trabajo que ayuda a las organizaciones a migrar a la nube alineando tecnología, personas y procesos.

!!! info "¿Cuántas perspectivas define AWS CAF?"

    → Seis: Business, People, Governance, Platform, Security y Operations.

## 2. Facturación y economía en la nube

### Aspectos generales

#### Modelo de precios de AWS

|Fuente de Costos|Unidad de Cálculo|Notas Clave|
|---|---|---|
|Computación|Por hora o por segundo|EC2, Lambda, RDS, etc.|
|Almacenamiento de datos|Por GB|S3, EBS, Glacier, EFS|
|Transferencia de datos|Por GB (salida)|Entrada gratuita en la mayoría de casos.|

##### Transferencia de datos

- Entrada: **Gratis** en la mayoría de los servicios.
- Salida: **Se cobra por GB**.
- Transferencia entre servicios en la misma región: **Generalmente gratuita** (hay excepciones).

#### Estrategias de ahorro

| Estrategia                       | Descripción                                                                    |
| -------------------------------- | ------------------------------------------------------------------------------ |
| Pago por uso                     | Sin compromisos, pagas lo que consumes.                                        |
| Reservas de capacidad (EC2, RDS) | Ahorro de hasta un **75%** respecto a demanda por 1 o 3 años.                  |
| Instancias Spot                  | Usa capacidad no utilizada de AWS a precios reducidos (hasta 90% más baratas). |
| Descuentos por volumen           | Cuanto más usas, menos pagas por GB.                                           |

##### Tipos de instancias reservadas (para ECS y RDS)

| Tipo                   | Descripción           |
| ---------------------- | --------------------- |
| AURI (All Upfront)     | Pago inicial completo |
| PURI (Partial Upfront) | Pago inicial parcial  |
| NURI (No Upfront)      | Sin pago inicial      |

#### Capa gratuita de AWS

- Disponible por **12 meses** para nuevos clientes.
- Incluye servicios como **EC2, S3, RDS (uso limitado), Lambda, DynamoDB**, etc.
- Algunos servicios como **VPC, IAM, Auto Scaling, CloudFormation, OpsWorks y Elastic Beanstalk** no tienen coste adicional, aunque el uso de recursos asociados puede generar cargos.

!!! info "¿Cuándo es gratuita la transferencia de datos en AWS?"

    → La **entrada de datos** es gratuita casi siempre. La **salida** se cobra por GB, pero la transferencia **dentro de la misma región** suele ser gratuita (hay excepciones).

!!! info "¿Qué porcentaje de ahorro máximo se puede obtener con instancias reservadas?"

    → Hasta **75%** de ahorro frente a instancias bajo demanda.

!!! info "¿Cuáles son los tipos de instancias reservadas en AWS?"

    → **AURI** (Pago inicial completo), **PURI** (Parcial), **NURI** (Sin pago inicial).

### Coste total de la propiedad (TCO- Total Cost of Ownership)

El **coste total de la propiedad (TCO, Total Cost of Ownership)** es la estimación financiera que ayuda a identificar todos los **costes directos e indirectos** de un sistema.

Se usa para comparar:

- Ejecutar una infraestructura en **instalaciones propias** (on-premises)
- Versus hacerlo en **la nube (AWS)**

Sirve también para **presupuestar una migración**.

|Categoría de coste|Elementos incluidos|
|---|---|
|**Server Costs**|Hardware (servidores, racks, switches), licencias de software y mantenimiento|
|**Storage Costs**|Discos, switches SAN/FC, costes de administración de almacenamiento|
|**Network Costs**|Hardware LAN, balanceadores, ancho de banda, costes de red|
|**IT Labor Costs**|Administración de servidores y virtualización|
|**Overhead Costs**|Espacio físico, energía eléctrica, refrigeración|

!!! info "¿Qué costes se suelen ignorar en los cálculos on-premises pero son importantes en TCO?"

    → Costes indirectos como **energía, espacio, refrigeración y mantenimiento del personal IT**.

### Costes en la nube vs. on-premises

|Aspecto|Nube (AWS)|Instalaciones propias (on-premises)|
|---|---|---|
|Tipo de gasto|Variables (OPEX)|Predicción fija (CAPEX + OPEX)|
|Escalabilidad|Elástica, bajo demanda|Limitada, requiere sobredimensionamiento|
|Previsibilidad de costes|Alta, gracias a precios por unidad de uso|Baja, incluye costes fijos aunque no se use|
|Herramientas de cálculo|**AWS Pricing Calculator**|Estimaciones manuales o herramientas de terceros|

!!! info "¿Qué ventaja clave ofrece AWS respecto a costes?"

    → **Transparencia y granularidad**, permite estimar costes según uso real: RAM, almacenamiento, red, etc.

!!! info "¿Qué herramienta permite calcular y optimizar el coste en AWS?"

    → [AWS Pricing Calculator](https://calculator.aws/#/)  
    Útil para planificar servicios, estimar facturas y detectar posibles **reducciones de coste**.

### Administración de costes y facturación en AWS

AWS proporciona herramientas centralizadas y visuales para facilitar el control, optimización y previsión de costes.

#### AWS Organizations

Servicio **gratuito** para gestionar múltiples cuentas desde una sola organización.

Permite:

- Crear **grupos de cuentas**.
- Aplicar **políticas de control de servicios (SCPs)**.
- Unificar la **facturación** (una sola factura para toda la organización).
- Administrar aplicaciones y permisos de forma centralizada mediante API.
- No sustituye a IAM, pero puede **permitir o denegar servicios a cuentas específicas**.

!!! info "¿Qué ventaja clave ofrece AWS Organizations en facturación?"

    → Permite una **factura única** para todas las cuentas de la organización, facilitando el seguimiento y consolidación de costes.

#### Herramientas de administración de costes

|Herramienta|Función principal|
|---|---|
|**Panel de facturación**|Consulta el gasto acumulado por servicio y visualiza tendencias.|
|**AWS Cost Explorer**|Gráficos, informes detallados, datos históricos de hasta **13 meses**.|
|**Presupuestos de AWS**|Estimaciones y alertas personalizadas vía **Amazon SNS**.|
|**Informes de uso y coste**|Datos diarios detallados exportables a **S3** para análisis avanzado.|

!!! info "¿Qué herramienta usar para recibir alertas cuando se supera un presupuesto?"

    → **Presupuestos de AWS**, configurando alertas con **Amazon SNS**.

!!! info "¿Qué herramienta permite ver el uso de AWS en gráficas históricas?"

    → **AWS Cost Explorer**, con vista de hasta **13 meses**.

#### AWS Support

AWS ofrece tanto **herramientas de soporte** como **planes de soporte personalizados** para adaptarse a distintos entornos, desde pruebas hasta cargas de trabajo críticas en producción.

##### Herramientas de soporte incluidas

|Herramienta|Funciones principales|
|---|---|
|**AWS Trusted Advisor**|- Optimizar costes - Mejorar la seguridad - Aumentar la fiabilidad y rendimiento - Detectar configuraciones ineficientes|
|**TAM (Technical Account Manager)**|- Punto de contacto principal (Business y Enterprise) - Revisión de arquitectura, planificación y optimización|
|**Concierge Support Team**|- Expertos en gestión de cuentas y facturación|

##### Planes de soporte de AWS

| Plan           | Descripción                                                               | Uso recomendado                   |
| -------------- | ------------------------------------------------------------------------- | --------------------------------- |
| **Basic**      | Gratuito. Acceso a recursos, foros y 6 comprobaciones de Trusted Advisor. | Experimentación inicial.          |
| **Developer**  | Soporte durante la fase de desarrollo.                                    | Cargas de trabajo no productivas. |
| **Business**   | Soporte para cargas en producción.                                        | Aplicaciones empresariales.       |
| **Enterprise** | Soporte para cargas críticas, incluye TAM.                                | Aplicaciones críticas de negocio. |

!!! info "¿Qué planes de soporte incluyen un TAM (Technical Account Manager)?"

    → Solo los planes **Business** y **Enterprise**.

!!! info "¿Qué plan debes contratar si tienes cargas de trabajo en producción?"

    → Mínimo el plan **Business**.

!!! info "¿Cuántas comprobaciones de Trusted Advisor están disponibles en el plan Basic?"

    → Solo **6 comprobaciones**.

## 3. Infraestructura y modelo de responsabilidad

### Infraestructura global de AWS

| Componente                               | Descripción                                                                                                                                                                                          |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Regiones**                             | Ubicaciones geográficas independientes. Aisladas entre sí para garantizar seguridad y gobernanza de datos.                                                                                           |
| **Zonas de Disponibilidad (AZ)**         | Cada región tiene varias AZs. Ofrecen alta disponibilidad, tolerancia a fallos y escalabilidad. Cada AZ puede incluir varios centros de datos separados físicamente **(hasta 100 km de distancia)**. |
| **Puntos de Presencia (Edge Locations)** | Mejoran la latencia y la entrega de contenido. Utilizados por servicios como **Amazon CloudFront (CDN)** y **Route 53 (DNS)**.                                                                       |

#### Características clave de la infraestructura de AWS

|Característica|Detalles|
|---|---|
|**Elástica y escalable**|Recursos que se ajustan dinámicamente a la demanda. Rápida adaptación a crecimientos o reducciones.|
|**Tolerante a errores**|Redundancia integrada en los componentes. Permite continuar operaciones incluso con fallos en algunos elementos.|
|**Alta disponibilidad**|Diseño para minimizar el tiempo de inactividad. Uso de múltiples AZs para continuidad de negocio.|

!!! info "¿Qué componente de AWS mejora la experiencia de usuario mediante baja latencia y optimización de contenido?"

    → Los **Puntos de Presencia (Edge Locations)**, utilizados en **Amazon CloudFront** y **Route 53**.

!!! info "¿Las regiones de AWS replican datos automáticamente entre sí?"

    → **No**, la replicación entre regiones debe ser gestionada por el cliente.

!!! info "¿Cuál es la separación máxima entre centros de datos de una misma zona de disponibilidad?"

    → Hasta **100 km**.

### Modelo de responsabilidad compartida

El **modelo de responsabilidad compartida** define qué aspectos de la seguridad y el cumplimiento son responsabilidad de **AWS** y cuáles del **cliente**.

#### Responsabilidades de AWS (seguridad _de_ la nube)

|Área|Descripción|
|---|---|
|Infraestructura física|Seguridad de centros de datos, edificios, energía, refrigeración.|
|Infraestructura de red y hardware|Seguridad de switches, servidores, almacenamiento y redes.|
|Software de base|Computación, almacenamiento, base de datos y red gestionados.|
|Regiones, zonas y edge locations|Protección y monitoreo continuo de la infraestructura global.|

#### Responsabilidades del cliente (seguridad _en_ la nube)

|Área|Descripción|
|---|---|
|Datos del cliente|Cifrado, clasificación y control de acceso a los datos.|
|Gestión de aplicaciones y accesos|Identidad, permisos, MFA, rotación de claves.|
|Sistema operativo y red|Parches de seguridad, configuración de firewall, apertura de puertos.|
|Cifrado del tráfico y almacenamiento|Cifrado en tránsito y en reposo (opcional según servicio y uso).|

!!! info "¿Quién es responsable de aplicar parches en una instancia EC2?"

    → El **cliente**, ya que EC2 es un servicio tipo **IaaS**.

!!! info "¿Y en un servicio como Lambda?"

    → AWS gestiona la infraestructura y el sistema operativo (modelo **PaaS**), el cliente solo sube su código.

## 4. AWS IAM. Seguridad

### AWS IAM (Identity and Access Management)

**AWS IAM** es un **servicio gratuito** que permite controlar de forma segura el acceso a recursos en AWS. Permite definir **quién** puede acceder, **a qué recursos**, **qué acciones** puede realizar y **cómo** puede acceder.

#### Componentes clave de IAM

|Componente|Descripción|
|---|---|
|**Usuario IAM**|Identidad que representa a una persona o aplicación.|
|**Grupo IAM**|Conjunto de usuarios IAM que comparten políticas comunes.|
|**Política IAM**|Documento en JSON que define permisos: recursos, acciones y condiciones.|
|**Rol IAM**|Permisos temporales para acceder a servicios de AWS, usados por usuarios o aplicaciones.|

#### Métodos de acceso a AWS

|Método|Descripción|
|---|---|
|**Programático**|Uso de **Access Key ID** y **Secret Access Key**. Ideal para APIs, SDKs y CLI.|
|**Consola web**|Acceso vía navegador. Se requiere ID de cuenta, nombre de usuario y contraseña.|

- Es recomendable activar **MFA (Multi-Factor Authentication)** para mayor seguridad.

!!! info "¿Qué principio se debe seguir al conceder permisos en AWS IAM?"

    → **Principio de mínimo privilegio**: conceder solo los permisos necesarios.

!!! info "¿Cuál es la diferencia entre un rol y un usuario IAM?"

    → Un **usuario IAM** es una identidad permanente; un **rol IAM** concede permisos **temporales**.

### Protección de cuentas y datos en AWS

La seguridad es uno de los pilares fundamentales de AWS, por lo que se recomienda seguir las buenas prácticas descritas en el **AWS Security Pillar (2020)**.

#### Recomendaciones para proteger la cuenta raíz

|Práctica recomendada|Descripción|
|---|---|
|**Habilitar MFA**|Activar **Multi-Factor Authentication** para añadir una capa de seguridad adicional.|
|**Eliminar claves de acceso**|Evitar el uso de claves asociadas a la cuenta raíz.|
|**Crear usuarios IAM**|Utilizar cuentas individuales con permisos mínimos necesarios.|
|**Uso de grupos IAM**|Asignar permisos a grupos, no directamente a los usuarios.|
|**Política de contraseñas**|Configurar contraseñas seguras y robustas.|
|**Usar roles IAM**|Evitar compartir credenciales, utilizar roles temporales.|
|**Monitorizar con CloudTrail**|Registrar y auditar la actividad de la cuenta.|

!!! info "¿Qué se debe hacer con las claves de acceso de la cuenta raíz?"

    → **Eliminarlas** y evitar su uso.

#### Servicios de AWS para mejorar la seguridad

|Servicio|Función principal|
|---|---|
|**AWS Organizations**|Gestión centralizada de cuentas y aplicación de **políticas SCP**.|
|**AWS KMS**|Gestión de claves de cifrado para proteger datos en AWS.|
|**Amazon Cognito**|Control de acceso a aplicaciones web y móviles, integración con redes sociales.|
|**AWS Shield**|Protección contra ataques de **denegación de servicio (DDoS)**.|
|**AWS Certificate Manager**|Gestión de certificados SSL/TLS para cifrado de datos en tránsito.|
|**AWS Storage Gateway**|Almacenamiento híbrido, integra entornos on-premises con AWS.|

#### Servicios de AWS relacionados con cumplimiento y protección de datos

| Servicio                | Función principal                                                 |
| ----------------------- | ----------------------------------------------------------------- |
| **AWS Config**          | Evaluar y auditar configuraciones de recursos en AWS.             |
| **AWS Artifact**        | Acceso a documentos de cumplimiento y certificaciones.            |
| **AWS Service Catalog** | Administración de catálogos de servicios aprobados.               |
| **Amazon Macie**        | Identificación y protección de **información personal sensible**. |
| **Amazon Inspector**    | Evaluación de seguridad y buenas prácticas de configuración.      |
| **Amazon GuardDuty**    | Detección de amenazas y actividades maliciosas.                   |

!!! info "¿Qué servicio permite gestionar claves de cifrado en AWS?"

    → **AWS Key Management Service (KMS)**.

!!! info "¿Qué servicio facilita la detección de información personal (PII)?"

    → **Amazon Macie**.

!!! info "¿Qué herramienta debes usar para monitorizar la actividad de la cuenta?"

    → **AWS CloudTrail**.

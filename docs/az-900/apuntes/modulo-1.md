# M1 - Conceptos básicos

## 1. Modelos de nube

### Qué son

> Prestación de servicios informáticos (como almacenamiento, servidores, bases de datos, redes o software) a través de Internet, bajo demanda y con pago por uso.

### Elementos que componen un modelo de nube

- Capacidad de procesamiento
- Redes de comunicaciones
- Almacenamiento
- Capacidades de análisis

### Tipos de modelos de nube

#### Nube Pública

Servicios e infraestructura gestionados por un proveedor externo y compartidos entre múltiples organizaciones a través de Internet.

- No hay gastos para escalar verticalmente.
- Las aplicaciones pueden aprovisionarse y desaprovisionarse.
- Solo pagas por lo que consumes.

**Uso habitual:** ideal para startups, entornos de desarrollo y pruebas, o cuando se busca escalar rápidamente sin gran inversión inicial.

#### Nube Privada

Infraestructura dedicada exclusivamente a una organización, ya sea ubicada en sus instalaciones o alojada por un proveedor, con mayor control y personalización.

- Costes de adquisición y mantenimiento del hardware.
- Control total sobre recursos y seguridad.
- Mantenimiento y actualización

**Uso habitual:** utilizada por empresas con altos requisitos de seguridad, cumplimiento normativo o control total sobre sus datos.

#### Nube Híbrida

Modelo que combina nubes públicas y privadas, permitiendo la interoperabilidad entre ambas para optimizar cargas de trabajo, seguridad y escalabilidad.

- Mayor flexibilidad
- Las organizaciones determinan donde se ejecutan las apps.
- Se controla la seguridad y los requisitos legales.

**Uso habitual:** recomendada cuando se necesita mantener ciertos datos sensibles en local pero aprovechar la escalabilidad de la nube pública.

## 2. Beneficios y consideraciones

|     | Beneficio               | Descripción                         |
| --- | ----------------------- | ----------------------------------- |
| 1   | **Alta disponibilidad** | Asegura continuidad frente a fallos |
| 4   | **Escalabilidad**       | Vertical u horizonal                |
| 2   | **Agilidad**            | Reducción del time to market        |
| 3   | **Elasticidad**         | Escalabilidad automatizada          |
| 5   | **Tolerancia a fallos** | Backups y replicación               |

### Tipos de gastos

- **Gastos de capital (CapEx):** El gasto inicial que invertimos en la infraestructura física a utilizar, se amortizan con el tiempo.

    > Las organizaciones pueden deducir el gasto de sus impuestos a lo largo de la vida del bien adquirido (varias anualidades).

- **Gastos operativos (OpEx):** Gastos en productos o servicios según sean necesarios (pago por uso o necesidad).

    > La facturación de los costes es inmediata (mensual), y las organizaciones pueden deducir el gasto de sus impuestos en el mismo año que realizan el gasto.

| Gastos de Capital (CapEx)            | Gastos Operativos (OpEx)             |
| ------------------------------------ | ------------------------------------ |
| Compra de servidores físicos         | Suscripción a servicios en la nube   |
| Instalación de redes y cableado      | Alquiler de servidores virtuales     |
| Licencias perpetuas de software      | Soporte técnico externalizado        |
| Contratación puntual para despliegue | Salarios del personal operativo      |
|                                      | Recursos consumibles y mantenimiento |
|                                      | Actualizaciones de software en nube  |

### Modelo basado en el consumo

Es un modelo de pago en el que solo se abona por los recursos que se utilizan, sin necesidad de realizar grandes inversiones iniciales. Es típico en servicios en la nube, donde el coste se ajusta al uso real (por ejemplo, almacenamiento, procesamiento o ancho de banda).

### Ventajas

- **Escalabilidad económica:** se adapta al crecimiento del proyecto sin gastos fijos elevados.
- **Eficiencia de costes:** se evitan pagos por recursos infrautilizados.
- **Flexibilidad:** permite ajustar los recursos según la demanda en tiempo real.
- **Reducción de riesgos:** menor inversión inicial y más control sobre los costes operativos.

## 3. Servicios en la nube

### IaaS (Infrastructure as a Service)

Servicios que proporcionan acceso a recursos de infraestructura básica como cómputo, red y almacenamiento. El usuario gestiona el sistema operativo, el middleware y las aplicaciones.

**Ejemplos:**

- Azure Virtual Machines (máquinas virtuales)
- Azure Virtual Network (redes virtuales)
- Azure Load Balancer
- Azure Storage (almacenamiento en disco)

### PaaS (Platform as a Service)

Servicios que ofrecen un entorno gestionado para desarrollar, compilar, probar y desplegar aplicaciones sin preocuparse por la infraestructura subyacente.

**Ejemplos:**

- Azure App Service (despliegue de apps web y APIs)
- Azure SQL Database (base de datos relacional como servicio)
- Azure Functions (computación sin servidor)
- Azure Logic Apps (automatización de flujos)

### SaaS (Software as a Service)

Aplicaciones completas ofrecidas por el proveedor y ejecutadas en la nube. El usuario solo interactúa con la interfaz y configura ciertas opciones, sin acceso al código ni a la infraestructura.

**Ejemplos:**

- Microsoft 365 (correo, Office, Teams, etc.)
- Dynamics 365 (CRM/ERP)
- Outlook.com
- OneDrive

### Modelo de responsabilidad compartida

| **Tu administras** | El proveedor administra |
| ------------------ | ----------------------- |

| Local (Nube privada)    | IaaS                    | PaaS                | SaaS                |
| ----------------------- | ----------------------- | ------------------- | ------------------- |
| **Datos y acceso**      | **Datos y acceso**      | **Datos y acceso**  | **Datos y acceso**  |
| **Solicitudes**         | **Solicitudes**         | **Solicitudes**     | **Solicitudes**     |
| **Tiempo de ejecución** | **Tiempo de ejecución** | Tiempo de ejecución | Tiempo de ejecución |
| **Sistema operativo**   | **Sistema operativo**   | Sistema operativo   | Sistema operativo   |
| **Máquina virtual**     | **Máquina virtual**     | Máquina virtual     | Máquina virtual     |
| **Proceso**             | Proceso                 | Proceso             | Proceso             |
| **Redes**               | Redes                   | Redes               | Redes               |
| **Almacenamiento**      | Almacenamiento          | Almacenamiento      | Almacenamiento      |

### Serverless computing

Se refiere a servicios del proveedor donde no es necesario gestionar la infraestructura subyacente de las aplicaciones. Únicamente se carga el código de la aplicacióon.

- Azure Functions (Web Apps sencillas)
- Logic Apps (Flujos de tareas, máquinas de estado)

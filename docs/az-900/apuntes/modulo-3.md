# M3 - Soluciones principales

## 1. Soluciones principales

### IoT (Internet of Things)

Dispositivos convencionales que recopilan y envían constantemente información a la nube.

| Servicio              | Tipo       | Descripción                                                                                                      |
| --------------------- | ---------- | ---------------------------------------------------------------------------------------------------------------- |
| **Azure IoT Central** | **_SaaS_** | Plataforma que te permite conectar y gestionar dispositivos IoT sin escribir casi nada de código.                |
| **Azure IoT Hub**     | **_PaaS_** | Servicio base para recibir, enviar y autenticar mensajes de millones de dispositivos IoT. Tú construyes encima.  |
| **Azure Sphere**      | **_ND_**   | Solución hardware + software para crear dispositivos IoT seguros desde el chip, con su propio sistema operativo. |

!!! info "Nota para el examen"

    - **IoT Central**: solución lista para usar. Ojo, si la pregunta dice algo como “sin escribir código”, esta es la opción correcta.
    - **IoT Hub**: suele aparecer como la opción más flexible. Si en la pregunta se menciona integración con sistemas externos, autenticación por dispositivo o millones de mensajes al día, es esta.
    - **Azure Sphere**: no es servicio en la nube. Si ves algo de seguridad en hardware, esta es la clave.

### Analytics

| Servicio                    | Tipo       | Descripción                                                                 |
|-----------------------------|------------|-----------------------------------------------------------------------------|
| **Azure Synapse Analytics** | **_PaaS_** | Plataforma analítica que combina almacenamiento de datos y análisis en tiempo real con SQL o Spark. Ideal para BI y reporting. |
| **Azure HDInsight**         | **_PaaS_** | Servicio que permite usar clústeres de tecnologías Big Data como Hadoop, Spark o Kafka ya configurados. |
| **Azure Databricks**        | **_PaaS_** | Entorno colaborativo basado en Apache Spark para análisis avanzado y machine learning, optimizado para Azure. |
!!! info "Nota para el examen"

    - **Synapse**: atención, puede confundirse con Databricks. Si la pregunta menciona consultas SQL, integración con Power BI o almacenamiento analítico, es Synapse.
    - **HDInsight**: si ves tecnologías específicas como Hadoop, Spark o Kafka, esta es la respuesta. Suele usarse para mantener compatibilidad con herramientas Big Data ya existentes.
    - **Databricks**: si la pregunta menciona ciencia de datos colaborativa, notebooks o entrenamiento de modelos Spark, apunta a esta.

### Inteligencia Artificial

| Servicio                   | Tipo       | Descripción                                                                 |
|----------------------------|------------|-----------------------------------------------------------------------------|
| **Azure Machine Learning** | **_PaaS_** | Plataforma para entrenar, desplegar y gestionar modelos de machine learning a escala. |
| **Cognitive Services**     | **_PaaS_** | APIs listas para usar que permiten añadir visión, lenguaje, voz y análisis de texto sin entrenar modelos. |
| **Azure Bot Service**      | **_PaaS_** | Servicio para crear, conectar y gestionar bots que interactúan con usuarios a través de canales como Teams, web o Telegram. |

!!! info "Nota para el examen"

    - **Azure Machine Learning**: si ves una pregunta sobre entrenar un modelo personalizado, elegir este.
    - **Cognitive Services**: importante: son APIs preentrenadas, no necesitas datos ni entrenamiento. En preguntas sobre visión por computadora, análisis de texto, voz o traducción automática, suelen ir por aquí.
    - **Bot Service**: si ves una opción que implica interacción con usuarios y texto hablado o escrito, esta es la correcta. Puede integrarse con Cognitive Services para tener respuestas inteligentes.

### Serverless Computing

Modelo en el que no gestionas la infraestructura, solo te centras en el código o lógica del flujo. La escalabilidad es automática y solo pagas por el tiempo de ejecución.

| Servicio             | Tipo       | Descripción                                                                 |
|----------------------|------------|-----------------------------------------------------------------------------|
| **Azure Functions**  | **_PaaS_** | Ejecuta código en respuesta a eventos sin gestionar servidores. Ideal para tareas pequeñas o automatizaciones. |
| **Azure Logic Apps** | **_PaaS_** | Automatiza flujos de trabajo con conectores sin escribir código. Ideal para integraciones entre servicios. |

!!! info "Nota para el examen"

    Ambos son considerados servicios *serverless*, pero:
    - **Functions** es más para desarrolladores (código).
    - **Logic Apps** es más visual y orientado a usuarios no técnicos.

### DevOps

| Servicio               | Tipo       | Descripción                                                                 |
|------------------------|------------|-----------------------------------------------------------------------------|
| **Azure DevOps**       | **_PaaS_** | Conjunto de servicios para gestión de proyectos, repositorios, CI/CD y testing. Ideal para equipos organizados en Azure. |
| **GitHub Actions**     | **_SaaS_** | Herramienta de automatización de flujos CI/CD integrada en GitHub. Ejecuta acciones tras commits, pull requests, etc. |
| **Azure DevTest Labs** | **_ND_**   | Servicio para crear entornos de desarrollo y pruebas de forma rápida y controlada, optimizando costes. |

!!! info "Nota para el examen"

    - **Azure DevOps**: ojo con las preguntas donde se mencionan *repositorios*, *pipelines* o *entrega continua*. Muy importante: Azure DevOps se puede usar **con código que no esté en Azure**, incluso con AWS o on-premises.
    - **GitHub Actions**: si aparece una pregunta que menciona GitHub directamente, esta será la opción CI/CD correcta. Cada vez más usada, pero **Azure DevOps sigue siendo más completo** en funcionalidades.
    - **DevTest Labs**: cuidado con preguntas sobre **optimizar costes en entornos de desarrollo y pruebas**. Este servicio permite autoapagado de máquinas y límites por usuario, suele aparecer como trampa frente a una VM suelta.

## 2. Herramientas de administración

### Herramientas de administración I

| Servicio                   | Descripción                                                                                                          |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Azure Portal**           | Interfaz web gráfica para gestionar y visualizar todos los recursos de Azure.                                        |
| **Azure Mobile App**       | Aplicación móvil para monitorizar recursos de Azure y recibir alertas desde el móvil.                                |
| **API REST Azure**         | Permite interactuar programáticamente con los servicios de Azure mediante peticiones HTTP.                           |
| **Azure PowerShell**       | Herramienta de línea de comandos basada en PowerShell para automatizar tareas en Azure.                              |
| **CLI**                    | Herramienta de línea de comandos multiplataforma para gestionar recursos de Azure desde la terminal.                 |
| **Azure Cloud Shell**      | Consola accesible desde el navegador con CLI y PowerShell preinstalados, sin necesidad de configuración local.       |
| **Azure Resource Manager** | Motor de despliegue y gestión que procesa todas las solicitudes para crear, actualizar o eliminar recursos en Azure. |

!!! info "Nota para el examen"

    - **Azure Portal** es la opción correcta cuando se pregunta por una interfaz gráfica basada en navegador.
    - **CLI** y **Azure PowerShell** suelen aparecer en preguntas sobre automatización. Recuerda: CLI es más universal (funciona en Windows, macOS, Linux), PowerShell está más integrado con el entorno Microsoft.
    - **Azure Cloud Shell** permite usar CLI o PowerShell **desde el propio portal**, sin instalar nada. Si ves algo como “sin configurar herramientas localmente”, es esta.
    - **API REST** se menciona en preguntas sobre integraciones programáticas desde apps externas.
    - **Azure Resource Manager (ARM)** es clave: si la pregunta menciona plantillas, control de dependencias o despliegues consistentes, es ARM.


### Herramientas de administración II

| Servicio               | Función principal                                              | Claves para el examen                                                                                       |
|------------------------|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Azure Advisor**      | Da recomendaciones personalizadas para optimizar tus recursos | Buenas prácticas: coste, rendimiento, seguridad. No lo confundas con Monitor (métricas) o Policy (reglas).  |
| **Azure Monitor**      | Supervisa métricas y logs de recursos                         | Si ves alertas, métricas o diagnósticos, es Monitor. No lo confundas con Advisor, Policy o Network Watcher.|
| **Azure Service Health** | Informa sobre incidencias o mantenimiento en servicios de Azure | Notificaciones sobre interrupciones. Si es personalizado por suscripción, es este (no Azure Status Page).   |
| **Plantillas ARM**     | Define infra como código en JSON para desplegar recursos      | Modelo declarativo. Preguntas sobre automatización e IaC. ARM es nativo, Terraform es multicloud. |

#### Azure Advisor

Servicio que analiza tu configuración y uso de recursos en Azure y te da recomendaciones personalizadas para mejorar rendimiento, seguridad, fiabilidad, optimización de costes y excelencia operativa.

- Seguridad
- Rendimiento
- Optimización de coste
- Excelencia operativa.

!!! info "Nota para el examen"

    - **Azure Advisor** aparece en preguntas sobre recomendaciones de buenas prácticas.  
    - Si ves algo como “sugerencias para reducir costes” o “mejorar seguridad y rendimiento”, esta es la respuesta correcta.  
    - No confundir con **Azure Monitor** (recoge métricas) o **Azure Policy** (impone reglas).

#### Azure Monitor

Servicio que recopila, analiza y visualiza métricas y logs de los recursos en Azure (y externos) para ayudarte a supervisar el estado, rendimiento y disponibilidad de tus aplicaciones e infraestructura.

- Métricas (por ejemplo, uso de CPU, latencia)
- Logs (eventos, diagnósticos)
- Alertas
- Paneles e integración con otras herramientas (como Log Analytics o Grafana)

!!! info "Nota para el examen"

    - **Azure Monitor** aparece en preguntas sobre supervisión, alertas o visualización de métricas y logs.  
    - Si la pregunta menciona “detectar problemas de rendimiento” o “generar alertas en tiempo real”, es Monitor.  
    - No confundir con **Azure Advisor** (da recomendaciones), ni con **Azure Policy** (aplica reglas), ni con **Network Watcher** (monitoriza redes).


#### Azure Service Health

Servicio que informa sobre el estado de los servicios de Azure y notifica incidentes, mantenimientos programados o cambios que puedan afectar a tus recursos.

- Alertas de incidentes activos
- Información sobre mantenimiento planificado
- Historial de problemas en tu región o servicios usados
- Integración con alertas personalizadas

!!! info "Nota para el examen"

    - **Azure Service Health** aparece en preguntas sobre **incidentes o mantenimiento que afectan a servicios de Azure**.  
    - Si ves algo como “informar a los equipos de caídas o interrupciones”, esta es la opción correcta.  
    - No confundir con **Azure Monitor** (supervisa tus recursos), ni con **Azure Status Page**, que muestra el estado global de Azure pero no personalizado a tu suscripción.


#### Plantillas ARM

Plantillas ARM (Azure Resource Manager) son archivos en formato JSON que definen la infraestructura y configuración de recursos en Azure de forma declarativa, permitiendo despliegues repetibles y consistentes.

- Infraestructura como código (IaC)
- Despliegues automáticos y controlados
- Se pueden versionar y reutilizar
- Permiten definir dependencias entre recursos

!!! info "Nota para el examen"

    - **Plantillas ARM** suelen aparecer en preguntas sobre **despliegues consistentes**, **automatización** o **infraestructura como código**.  
    - Recuerda: definen *qué* recursos quieres, no *cómo* se crean (modelo declarativo).  
    - No confundir con **Azure Bicep** (lenguaje simplificado que genera plantillas ARM), ni con scripts CLI o PowerShell (modelo imperativo).  
    - **Diferencia con Terraform**: ARM es nativo de Azure, mientras que Terraform es una herramienta de terceros que permite gestionar recursos de múltiples nubes, no solo Azure.

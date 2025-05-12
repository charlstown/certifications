# Examen

Test de 49 preguntas con formato similar al examen oficial de la certificación.

!!! info ""

    Puedes ver la solución a cada pregunta haciendo click al icono _:octicons-light-bulb-16: Mostrar pista_.

:::{quizdown}

---
primaryColor: "#00bda4"
shuffleQuestions: false
shuffleAnswers: true
---

## ¿Qué modelo de nube es un esfuerzo colaborativo en el que la infraestructura se comparte entre varias organizaciones con intereses comunes?

1. [x] Comunidad (Community cloud)
2. [ ] Nube pública (Public cloud)
3. [ ] Nube privada (Private cloud)
4. [ ] Nube híbrida (Hybrid cloud)

> El cloud comunitario permite que varias organizaciones compartan infraestructuras por intereses comunes.

## ¿Qué beneficio de Azure Cloud Services ayuda a gestionar costes cuando hay picos de tráfico web por campañas de anuncios?

1. [ ] Alta disponibilidad (high availability)
2. [ ] Alta latencia (high latency)
3. [ ] Balanceo de carga (load balancing)
4. [x] Elasticidad (elasticity)

> La elasticidad permite adaptar recursos automáticamente a los picos de demanda.

## Selecciona las afirmaciones correctas sobre el Azure Trust Center (elige dos).

- [x] Los clientes que no cumplan con GDPR pueden recibir multas de hasta el 4% de la facturación global anual o €20 millones.
- [ ] Azure Trust Center se basa en los tres principios fundamentales de confianza.
- [x] Azure está certificado en K-ISMS.
- [ ] Azure Sentinel es una herramienta de gestión de cumplimiento disponible en Trust Center.

> Azure Trust Center informa sobre multas por GDPR y certificaciones relevantes como K-ISMS.

## ¿Qué característica de Azure puede proteger aplicaciones de un fallo en un datacenter?

1. [ ] Conjunto de escalado de máquinas virtuales (Virtual machine scale set)
2. [ ] Dominio de fallo (Fault domain)
3. [x] Zona de disponibilidad (Availability zone)
4. [ ] Dominio de actualización (Update domain)

> Solo las Zonas de disponibilidad aíslan físicamente aplicaciones frente a caídas de datacenter.

## Para cada declaración sobre Azure App Service, selecciona solo aquellas que sean verdaderas

- [x] Azure App Service detecta y diagnostica anomalías en las aplicaciones web.
- [ ] Azure App Service proporciona una plataforma serverless que permite escribir menos código.
- [x] Puedes usar la característica WebJobs para ejecutar programas en el mismo contexto que una app móvil, web o API.
- [x] Azure App Service permite alojar aplicaciones web nativamente en Linux.
- [ ] Azure App Service es el servicio HTTP/HTTPS que aloja aplicaciones web.

> App Service permite diagnósticos, WebJobs y despliegues en Linux, pero no es estrictamente serverless ni solo un servicio HTTP/HTTPS.

## Para cada declaración selecciona la afirmación solo si es verdadera sobre Azure Arc

- [x] Azure Arc proporciona una forma centralizada de usar operaciones tradicionales de TI (ITOps) y prácticas DevOps para patrones cloud-native.
- [x] Azure Arc aclara el gobierno y la administración al ofrecer servicios multicloud y una plataforma de gestión local.
- [ ] Usando Azure Arc, no puedes administrar ni gobernar clústeres de Kubernetes a escala.
- [x] Usando Azure Arc, puedes configurar extensiones de VM para usar servicios de administración de Azure para monitorizar, proteger y actualizar tus servidores.

> Azure Arc centraliza la gestión y soporta DevOps, multicloud y extensión de servicios de administración.

## Ordena los pasos para evitar que las máquinas virtuales de cada departamento se comuniquen entre sí

1. Crear una tabla de rutas personalizada para restringir la comunicación entre SubnetA, SubnetB y SubnetC.
2. Instalar un firewall en la red virtual de Azure.
3. Configurar endpoints de servicio entre las subredes.

> Se debe definir la segmentación (tabla de rutas), después aplicar filtrado (firewall) y finalmente configurar los endpoints.

## Para cada declaración sobre buenas prácticas de políticas de acceso condicional, selecciona solo si es verdadera

- [x] Configurar cuentas de acceso de emergencia.
- [ ] Aplicar una única política de acceso condicional para todas las aplicaciones de la organización.
- [ ] Desactivar el modo solo informe (report only).
- [x] Agrupar las aplicaciones con los mismos requisitos y aplicar una sola política de acceso condicional para ese conjunto de aplicaciones.
- [x] Evaluar tus políticas de acceso condicional usando la herramienta What If.

> Las mejores prácticas incluyen cuentas de emergencia, agrupar políticas por requisitos y usar "What If" para evaluar.

## ¿Qué herramienta debes usar para copiar datos de un almacenamiento local a una cuenta de Azure Storage?

1. [x] AzCopy (herramienta de línea de comandos)
2. [ ] App Service Migration Assistant
3. [ ] Microsoft Data Migration Assistant
4. [ ] Azure Migrate: Discovery and assessment

> AzCopy es la herramienta oficial y recomendada para transferir datos a Azure Storage.

## Selecciona solo las afirmaciones verdaderas sobre la característica de Iniciativas en Azure (elige tres)

- [x] El alcance de una definición de iniciativa debe ser un grupo de administración o una suscripción.
- [ ] El número máximo de definiciones de iniciativa por tenant es 100.
- [x] Los parámetros de la iniciativa ayudan a simplificar la gestión reduciendo redundancias.
- [x] Una definición de iniciativa es un conjunto de definiciones de políticas que pueden usarse para un objetivo común.

> Una iniciativa agrupa políticas, permite usar parámetros para simplificar y se aplica a suscripciones o grupos de administración.


## ¿Qué herramienta de Azure es una solución basada en la nube que permite a las organizaciones descubrir, clasificar y proteger documentos y correos electrónicos aplicando etiquetas al contenido?

1. [x] Azure Information Protection (AIP)
2. [ ] Credential Manager
3. [ ] Azure Functions
4. [ ] Azure Cosmos DB
5. [ ] Azure Key Vault

> Azure Information Protection permite descubrir y proteger información aplicando etiquetas y reglas de clasificación.

## Eres el administrador de Azure para Nutex Corporation. Quieres asegurarte de que solo los usuarios del departamento de Marketing puedan acceder a la aplicación CompanyApp mediante autenticación multifactor desde el trabajo y desde casa.

1. [ ] Establecer las reglas de acceso en OFF, aplicar a todos los usuarios excepto Marketing, y requerir MFA.
2. [x] Establecer las reglas de acceso en ON, aplicar a grupos, añadir el grupo Marketing y requerir MFA.
3. [ ] Establecer reglas de acceso en ON, aplicar a todos los usuarios excepto Marketing, y requerir MFA.
4. [ ] Establecer reglas de acceso en OFF, aplicar a grupos, añadir Marketing y requerir MFA.

> Solo la opción de habilitar reglas, aplicar a grupos e incluir Marketing con MFA asegura que solo ellos accedan mediante multifactor.

## Tu empresa planea desarrollar nuevas aplicaciones, desplegar nuevas máquinas virtuales e implementar Microsoft 365 usando el modelo Platform as a Service (PaaS).

- [x] Los usuarios no necesitan configurar servidores para ejecutar aplicaciones.
- [ ] Es el modelo de nube más flexible.
- [x] Los usuarios pueden personalizar las herramientas de desarrollo del proveedor.
- [x] Los usuarios no tienen gastos de capital (CapEx).

> PaaS elimina la gestión de servidores, permite personalizar herramientas y evita inversiones CapEx.

## ¿Qué solución de Microsoft proporciona un servicio de gobierno de datos para gestionar datos en local, en Azure o en SaaS?

1. [ ] Microsoft Intune Endpoint Privilege Management (EPM)
2. [ ] Microsoft Security Compliance Toolkit (SCT)
3. [x] Microsoft Purview
4. [ ] Microsoft Identity and Access Management (IAM)

> Microsoft Purview es la solución para gobierno de datos en entornos híbridos y SaaS.

## Nutex Corporation quiere un servicio de Azure que inspeccione recursos y notifique al equipo de administración sobre incidencias.

- [x] Panel personalizado para reportar el estado y problemas de servicio.
- [ ] Archivar el historial de eventos de servicio indefinidamente.
- [x] Análisis de causa raíz y explicaciones descargables de incidencias activas.
- [x] Integración con ServiceNow usando un webhook.
- [x] Alertas personalizadas para incidentes, mantenimiento y avisos de salud.

> Service Health permite paneles, integración, alertas y análisis de causa, pero no archiva eventos indefinidamente.

## Ordena los conceptos relacionados con plataformas serverless en Azure: 1-Azure Functions, 2-Logic Apps, 3-Event Grid

1. Permite ejecutar código en base a eventos especificados.
2. Configura flujos de trabajo y coreografía de procesos.
3. Orquesta y dirige eventos que pueden disparar código o lógica.

> Functions ejecuta código por eventos, Logic Apps orquesta flujos, Event Grid gestiona y dirige eventos.

## Necesitas diseñar autenticación multifactor (MFA) para tu despliegue Azure, usando MFA Server on-premises para apps publicadas vía Entra Application Proxy y apps Microsoft. ¿Cumple este diseño el requisito de MFA con llamada telefónica como segundo factor?

1. [ ] Sí
2. [x] No

> MFA Server local no es válido para proteger aplicaciones publicadas vía Entra App Proxy ni apps cloud.

## Cuando usas un proveedor cloud, ¿qué aspectos son responsabilidad del cliente en cuanto a seguridad?

1. [x] Configuración de firewalls
2. [ ] Sitios físicos
3. [ ] Infraestructura de hardware
4. [ ] Red cloud

> El cliente debe asegurar la configuración de firewalls; el resto corresponde al proveedor cloud.

## Tienes una aplicación con muchas transacciones pequeñas y baja latencia. ¿Qué tipo de cuenta de almacenamiento recomiendas?

1. [ ] Standard general-purpose v2
2. [ ] Cool
3. [x] Premium block blobs
4. [ ] Archive
5. [ ] Hot

> Premium block blobs ofrecen mejor rendimiento y baja latencia para transacciones frecuentes.

## Josephine debe optimizar el uso de ancho de banda y la topología de peering entre las VNets de Nutex para los entornos Dev y Prod, evitando comunicación innecesaria entre entornos.

- [ ] Debe hacer peering entre Nutex_VNetA y la subred on-premises.
- [ ] Debe hacer peering entre DevWeb_VNetB y ProdWeb_VNetC.
- [x] Debe hacer peering entre Nutex_VNetA y ProdWeb_VNetC.
- [x] Debe hacer peering entre Nutex_VNetA y DevWeb_VNetB.

> El peering debe conectar la VNet central (Nutex_VNetA) con cada entorno, evitando peering directo entre Dev y Prod.

## Debes migrar una copia única de PDFs y gráficos desde un recurso compartido local a Azure Blob Storage con el mínimo esfuerzo administrativo.

1. [x] Azure Storage Explorer
2. [ ] SQL Server Integration Services
3. [ ] Python
4. [ ] Shared Access Signature

> Azure Storage Explorer permite subir archivos a Azure Blob de manera simple y rápida.

## Tienes una aplicación web crítica con errores intermitentes. Quieres usar Azure Monitor para encontrar la causa raíz del problema.

1. [x] Azure Log Analytics
2. [ ] Azure Functions
3. [ ] Azure Advisor
4. [ ] Azure Databricks

> Log Analytics centraliza los logs y permite investigar la causa de errores en aplicaciones.

## ¿Qué debe implementar Nutex para evitar "configuration drift" al desplegar aplicaciones en la nube que requerirán varias revisiones?

1. [x] Infrastructure as Code (IaC)
2. [ ] Azure DevOps Dependency Tracker
3. [ ] Continuous Delivery (CD)
4. [ ] Continuous Integration (CI)

> IaC permite mantener la configuración bajo control y evitar desviaciones.

## ¿Cuáles de las siguientes afirmaciones sobre máquinas virtuales de Azure son verdaderas?

- [ ] Azure cobra en tiempo real por tamaño y sistema operativo de la VM.
- [ ] Las VMs en estado Stopped generan cargos de cómputo.
- [x] Las VMs usan discos duros virtuales para almacenar sistema operativo y datos.
- [x] Las VMs en estado Deallocated no generan costes de cómputo.
- [x] Los discos del sistema operativo pueden redimensionarse.
- [ ] Se pueden añadir VMs existentes a un availability set.

> Solo las opciones sobre VHD, estado deallocated y redimensionar discos son verdaderas para VMs de Azure.

## ¿Cuáles son beneficios del modelo de consumo de Azure? (Elige tres)

- [x] Sin coste inicial.
- [x] No es necesario comprar ni gestionar infraestructura.
- [ ] Se reembolsa lo no usado.
- [x] Pagas por recursos adicionales sólo si los necesitas.

> El modelo de consumo elimina inversión inicial, gestiona infra por ti y es elástico en costes.

## Usas Azure DNS y quieres gestionar el comportamiento de sobrescritura de un registro DNS de testnutex.com.

1. [x] Etag
2. [ ] Metadata
3. [ ] Apex
4. [ ] DNSSec

> El componente Etag controla la sobrescritura de registros DNS en Azure DNS.

## ¿Cuáles de las siguientes afirmaciones sobre modelos de precios cloud son verdaderas?

- [ ] Cloud computing ofrece servicios solo con modelo pay-as-you-go.
- [ ] El proveedor controla los costes operativos y tú no tienes control.
- [ ] Fixed price es lo mismo que pay-as-you-go.
- [x] En el modelo de consumo pagas solo por lo que usas.
- [x] El modelo de consumo es eficiente para alto uso de recursos y analizar costes base.

> El modelo de consumo se basa en pago por uso y es eficiente para ajustar costes a la utilización real.

## Tu empresa alquila infraestructura IT, VMs, almacenamiento, redes y sistemas operativos en Azure con pago por uso. ¿Qué modelo de cloud es este?

1. [ ] FaaS
2. [x] IaaS
3. [ ] PaaS
4. [ ] SaaS

> IaaS describe el alquiler de infraestructura y recursos básicos de TI.

## Tu equipo despliega productos en Azure para diferentes geografías. ¿Qué afirmaciones sobre pricing geográfico de Azure son ciertas?

- [ ] Los servicios de Azure cuestan igual en todas las geografías.
- [x] Una región en Azure es un conjunto de geografías que respeta residencia de datos y cumplimiento.
- [ ] Todos los productos de Azure están disponibles en todas las regiones.
- [x] Azure Australia tiene dos regiones destacadas Australia Central.

> Los precios varían por región y no todos los servicios están en todas las regiones; las regiones también determinan residencia y cumplimiento.

## Quieres que Azure monitorice el uso de CPU en tus VMs. ¿Qué acciones puedes configurar cuando el uso de CPU supera el umbral? (Selecciona todas las que apliquen)

- [ ] Ejecutar un script de PowerShell
- [x] Llamar a un webhook
- [ ] Llamar a un contador de rendimiento de un objeto de gestión de rendimiento
- [x] Iniciar la ejecución de un runbook de Azure
- [ ] Ejecutar un archivo por lotes
- [x] Enviar notificaciones por correo electrónico

> Puedes automatizar notificaciones, webhooks y runbooks cuando la CPU supere el umbral.

## Ordena los modelos de despliegue cloud y su descripción: 1-Platform as a Service, 2-Software as a Service, 3-Infrastructure as a Service

1. Permite desplegar servidores web, bases de datos y herramientas de desarrollo en la nube.
2. Permite ejecutar aplicaciones en la nube.
3. Permite desplegar máquinas virtuales, servidores y almacenamiento en la nube.

> PaaS: servidores y desarrollo; SaaS: ejecutar aplicaciones; IaaS: VMs y almacenamiento.

## Dreamsuites quiere usar Azure Blueprints para un mejor gobierno de suscripciones. ¿Qué artefactos están disponibles actualmente en Blueprints? (Elige cuatro)

- [x] Asignación de roles
- [x] Asignación de políticas en recursos de Azure
- [ ] Contenedores de Azure
- [x] Grupos de recursos
- [x] Plantillas ARM

> Blueprints permite usar roles, políticas, grupos de recursos y plantillas ARM como artefactos.

## Ordena el tipo de cloud con su definición correcta: 1-SaaS, 2-IaaS, 3-PaaS, 4-NaaS, 5-DSaaS

1. Aplicaciones centralizadas y licenciadas por suscripción.
2. Infraestructura computacional alquilada y gestionada en la nube.
3. Desarrollar apps sin mantener la infraestructura subyacente.
4. Externaliza routers, subredes y conectividad.
5. Externaliza la entrega de datos y análisis avanzados.

> SaaS: apps y suscripción; IaaS: infraestructura; PaaS: desarrollo sin infra; NaaS: conectividad; DSaaS: análisis de datos.

## Tienes una app que debe persistir datos en un contenedor, ejecutándose en varias VMs con acceso a los mismos archivos. Un compañero sugiere usar un "bind mount". ¿Cumple la solución la necesidad?

1. [x] No
2. [ ] Sí

> Un bind mount solo persiste datos localmente en una VM, no entre varias VMs.

## Vas a almacenar información fiscal histórica en Azure y usuarios deben montar una unidad de red para acceder a los datos. Planteas usar Azure Information Protection (AIP). ¿Cumple la solución con las necesidades del departamento fiscal?

1. [x] No
2. [ ] Sí

> AIP protege y clasifica, pero no expone los datos como una unidad de red compartida.

## Selecciona solo aquellas sentencias que correspondan a la autenticación (deja las de autorización sin marcar)

- [x] El proceso de autenticación a veces usa un test Captcha.
- [x] Este proceso utiliza credenciales como usuario y contraseña.
- [x] Multi-factor se usa en este proceso para añadir varios niveles de seguridad independientes.

> La autenticación se basa en validar identidad con credenciales, MFA y, opcionalmente, Captcha.

## Ordena los atributos/configuración de Azure Functions: 1-Durable Functions, 2-dynamicThrottlesEnabled, 3-matchCondition, 4-Schedule, 5-Binding

1. Permite escribir funciones con estado en entorno serverless.
2. Revisa contadores de rendimiento del sistema como conexiones, procesos y memoria.
3. Define una única superficie API para varias apps de función.
4. Dispara la función usando una expresión CRON de seis campos.
5. Extrae datos de servicios externos.

> Cada ajuste cubre desde orquestación con estado, rendimiento, binding, scheduling y APIs.

## Necesitas recolectar archivos de log en tu suscripción de Azure para que los admin puedan consultarlos en un solo workspace.

1. [ ] Azure Security Center
2. [ ] Azure Network Watcher
3. [ ] Azure Service Health
4. [x] Azure Log Analytics

> Azure Log Analytics centraliza logs en un solo workspace para consultas.

## El Nutex Corporation quiere cumplir con privacidad y regulaciones; debes investigar las ofertas y compromisos de Microsoft. ¿Qué afirmaciones del Azure Service Trust Portal son verdaderas? (Elige tres)

- [x] Microsoft no usará tu email, chat, archivos ni otros datos personales para publicidad dirigida.
- [ ] Todas las transacciones con Azure Storage vía portal se realizan por HTTPS.
- [x] Si un tenant de Azure se desactiva, Microsoft elimina permanentemente los datos en Service Trust Portal en 24 horas.
- [x] Service Trust Portal ofrece Blueprints de Seguridad y Cumplimiento para ayudar con la regulación.
- [ ] Si una suscripción cloud expira, Microsoft elimina los datos en 90 días sin notificar.

> Microsoft protege tu privacidad, borra datos de Trust Portal al desactivar tenant y ofrece blueprints de cumplimiento.

## Ordena las propiedades con el servicio de cómputo apropiado: 1-Azure Batch, 2-Azure Container Apps, 3-Azure App Service, 4-Azure Kubernetes Service

1. Al menos 1 nodo
2. Serverless
3. Sin estado (Stateless)
4. Sin estado o con estado (Stateless or stateful)

> Azure Batch: al menos 1 nodo; Container Apps: serverless; App Service: stateless; Kubernetes Service: stateless or stateful.

## Quieres reducir costes implementando Azure Spot Virtual Machines. ¿Cuáles de las siguientes afirmaciones son ciertas? (Elige dos)

- [x] Pueden ser desalojadas según el precio máximo que determines.
- [ ] Tienen el mismo SLA que las VMs normales.
- [ ] Son compatibles con series B, D y E.
- [x] Pueden ser desalojadas según la capacidad.
- [ ] Deben ser eliminadas manualmente si son desalojadas.

> Las Spot VMs pueden ser desalojadas por precio o capacidad, y no garantizan el mismo SLA.

## El equipo de análisis de producto debe obtener un informe de rentabilidad basado en los costes de datos en Azure. ¿Qué afirmaciones sobre costes de entrada y salida (ingress/egress) en Azure son correctas? (Selecciona todas las que apliquen)

- [x] En conexiones VPN site-to-site y point-to-site, los primeros 5 GB de salida (egress) son gratuitos al mes.
- [ ] En ExpressRoute medido, se cobran tanto entrada como salida.
- [x] En peering de VNet se cobran entrada y salida.
- [x] La entrada a Azure desde entornos on-premises no se cobra.
- [x] Hay diferencias de precios de entrada y salida entre peering en la misma región y entre regiones.

> Egress en VPN tiene 5GB gratuitos, peering puede cobrar entrada/salida, y la entrada desde on-premises no se cobra.

## Ordena el modelo o categoría de cloud con su descripción: 1-Public cloud, 2-Private cloud, 3-SaaS, 4-IaaS

1. Varias organizaciones comparten la infraestructura del proveedor.
2. La organización despliega su propia infraestructura cloud, normalmente tras un firewall.
3. El proveedor aloja las aplicaciones en servidores en la nube.
4. El proveedor mantiene todo el hardware necesario para la nube.

> Public cloud: compartido; Private cloud: propio y seguro; SaaS: apps alojadas por el proveedor; IaaS: proveedor gestiona hardware.

## ¿Cuáles de los siguientes son ejemplos de SaaS? (Elige dos)

- [ ] Microsoft Azure
- [x] Google Apps
- [ ] Amazon Web Services Elastic Beanstalk
- [ ] Google Compute Engine
- [x] Salesforce

> Google Apps y Salesforce son SaaS; los demás son PaaS o IaaS.

## ¿Qué servicio de Azure proporciona un entorno portátil para aplicaciones virtualizadas, permitiendo ejecutar múltiples instancias de una aplicación en un solo host?

1. [ ] Azure App Service
2. [x] Azure Container Instances
3. [ ] Azure Functions
4. [ ] Azure virtual machines

> Azure Container Instances permite ejecutar apps aisladas y portables en contenedores sobre un único host.

## Tienes seis bosques de Active Directory, algunos con dominios hijo, y solo un trust entre metroil.com y nutex.com. ¿Cuál es el número mínimo de dominios personalizados verificados que debes añadir a Entra ID para que todos los usuarios tengan SSO en Office 365?

1. [ ] 2
2. [ ] 1
3. [x] 5
4. [ ] 10

> Se necesita un dominio verificado por cada bosque para SSO: 5 bosques, 5 dominios.

## Debes reducir costes de almacenamiento en blobs y propones Azure Hybrid Benefit. ¿Qué afirmaciones sobre Azure Hybrid Benefit son verdaderas? (Elige dos)

- [x] Permite usar licencias locales con servidores en Azure.
- [x] Licencias válidas son SQL Server y Windows Server con Software Assurance activo.
- [ ] También incluye Exchange Server.
- [ ] Software fuera de soporte no es elegible.
- [ ] Permite usar licencias cloud en on-premises.

> Hybrid Benefit permite trasladar licencias activas de SQL/Windows Server a Azure.

## ¿Para qué se usa correctamente una plantilla ARM de Azure?

1. [ ] Para actuar como broker de colas de mensajes y topics.
2. [x] Para la creación automática de recursos de Azure.
3. [ ] Para desplegar analítica predictiva.
4. [ ] Para organizar recursos y suscripciones.

> Una plantilla ARM automatiza el despliegue de recursos en Azure.

## Selecciona solo aquellas afirmaciones que son verdaderas para la nube híbrida

- [x] Escalabilidad
- [ ] No es necesario comprar hardware o software
- [ ] El proveedor de servicios proporciona el mantenimiento
- [ ] Pagar solo por el servicio que usas
- [ ] El mayor nivel de control y seguridad
- [x] Pagar solo por potencia extra cuando se necesita
- [x] Útil para migrar servicios a la nube

> La nube híbrida se caracteriza por su escalabilidad, pago flexible por potencia adicional y su utilidad para migrar servicios.

:::

# M1 - Conceptos básicos

Test de 13 preguntas relacionadas con el [módulo 1](../apuntes/modulo-1.md) de conceptos básicos en Azure.

!!! info ""

    Puedes ver la solución a cada pregunta haciendo click al icono _:octicons-light-bulb-16: Mostrar pista_.

:::{quizdown}

---
primaryColor: "#00bda4"
shuffleQuestions: false
shuffleAnswers: true
---

## Para cada declaración con respecto a la nube pública, seleccione solo las declaraciones que sean verdaderas.

- [ ] La nube pública requiere mucho conocimiento técnico para su configuración. 
- [x] Las conexiones a la nube pública generalmente ocurren a través de Internet.
- [ ] Una instancia de nube pública no puede tener usuarios invitados.

> La nube pública no requieren muchos conocimientos técnicos, ya que la configura un proveedor de alojamiento. Las conexiones a la nube pública generalmente ocurren a través de Internet. La nube pública pueden tener usuarios invitados, dependiendo de la naturaleza de la configuración del directorio de red.

## Usted, como administrador, necesita encontrar una solución en la nube donde los usuarios puedan conectarse a su negocio a través de un sitio web. Los datos del sitio web deben almacenarse en una ubicación altamente segura. ¿Qué tipo de nube se ajusta mejor a este escenario?

1. [ ] Nube privada
2. [x] Nube híbrida
3. [ ] Nube de la comunidad
4. [ ] Nube pública

> Este escenario requiere aspectos tanto de una nube pública (el sitio web) como de una nube privada (la base de datos altamente segura). Por lo tanto, una nube híbrida es la mejor solución para este escenario.

## ¿Qué herramienta de Azure proporciona un método de puntuación para ayudar a las organizaciones a rastrear el progreso y proporciona formas de auditoría para ayudar a reducir la exposición al riesgo?

1. [ ] Azure Government Services
2. [ ] Portal Service Trust
3. [ ] Trust Center
4. [x] Compliance Manager

> Compliance Score, forma parte del Compliance Manager en Azure, y ayuda a las organizaciones a rastrear el progreso y reducir la exposición al riesgo mediante la priorización de los controles de auditoría.

## Para cada servicio de Azure, selecciona solo el servicio que está disponible después de que la prueba gratuita haya expirado.

- [ ] AD / Entra ID
- [x] VMs
- [x] Datos de almacenamiento

> Las máquinas virtuales y los datos de almacenamiento siguen estando disponibles después de que haya caducado una prueba gratuita de Azure. Active Directory no está disponible a menos que una suscripción se actualice Pago por uso o superior.

## ¿Cuáles son las características de las nubes privadas? (Escoja dos)

- [x] CapEx es más alto que el de las nubes híbridas y públicas.
- [ ] El cumplimiento normativo es automático.
- [ ] Las nubes privadas nunca se usan para aplicaciones heredadas.
- [x] Las organizaciones tienen control total de los recursos y la seguridad.

> En una nube privada, las organizaciones tienen el control total de los recursos y la seguridad. Las nubes privadas tienen altos gastos de capital por adelantado (CapEx) en comparación con las nubes híbridas y públicas, ya que el hardware para la nube privada debe comprarse por adelantado.

## Ordena el tipo de servicio de Azure con la característica implícita del servicio: __1 - IaaS, 2 - PaaS, 3 - SaaS__.

1. VMs
2. Linux
3. Microsoft Office 365

> Los servidores y el almacenamiento (como las máquinas virtuales) son parte de Infraestructura como servicio (IaaS). Los sistemas operativos (como Linux) son parte de Platform as a Service (PaaS). Microsoft Office 365 es parte de Software as a Service (SaaS).

## ¿Cuáles son los beneficios de un modelo basado en el consumo para servicios en la nube? (Escoja dos)

- [x] Sin costos iniciales
- [ ] No pagar por el almacenamiento cuando las máquinas virtuales que usan almacenamiento no están en uso.
- [x] No pagar por recursos que ya no son necesarios.
- [ ] Un CapEx más alto

> Los beneficios de un modelo basado en el consumo incluyen costos iniciales, menos necesidad de comprar infraestructura y la capacidad de pagar solo por recursos cuando sea necesario.

## Evalúe la siguiente declaración y elija la frase correcta para la parte subrayada de la declaración. Si el enunciado es correcto tal como está, indíquelo. [Economías de escala] son el concepto en el que los costos informáticos son más bajos cuando se opera a una escala mayor.

1. [x] La declaración es correcta
2. [ ] Balanza de costos
3. [ ] Escala OpEx
4. [ ] Escala CapEx

> Las economías de escala son el concepto en el que los costos informáticos son más bajos cuando se opera a una escala mayor.

## Ordena el concepto de informática en la nube con su definición: 1 - Elasticidad, 2 - Agilidad, 3 - Escalabilidad.

1. Es la flexibilidad de poder aumentar o disminuir fácilmente los recursos, como un incremento en los servidores virtuales en una granja de servidores.
2. Es la capacidad de disposición o no disposición de servicios rápidamente.
3. Es la capacidad de aumentar o disminuir los recursos dinámicamente.

> La escalabilidad es la flexibilidad de poder aumentar o disminuir fácilmente los recursos, como un incremento en los servidores virtuales en una granja de servidores. La agilidad es la capacidad de disposición o no disposición de servicios rápidamente. La elasticidad es la capacidad de aumentar o disminuir los recursos dinámicamente.

## Para cada producto de Azure, elija el porcentaje de tiempo de actividad de SLA. 1- Aplicaciones Web, 2 - Base de Datos SQL

1. 99.95%
2. 99.99%

> Actualmente en Azure, las aplicaciones web tienen un tiempo de actividad del 99.95% y las bases de datos SQL tienen un tiempo de actividad del 99.99%, de acuerdo con el Acuerdo de Nivel de Servicio (SLA) para cada una.

## ¿Qué servicio en la nube incluye servidores, máquinas virtuales, almacenamiento y redes pero no herramientas o aplicaciones de desarrollo?

1. [ ] SEaaS
2. [x] IaaS
3. [ ] SaaS
4. [ ] PaaS

> Infrastructure as a service (IaaS) incluye servicios en la nube como servidores, máquinas virtuales, almacenamiento y redes.

## ¿Cuáles son dos ejemplos de SaaS? (Escoja dos)

- [x] Microsoft Dynamics CRM online
- [x] Skype
- [ ] Hyper-V
- [ ] Azure DevOps

> Skype y Microsoft Dynamics CRM Online son ejemplos de software como servicio (SaaS).

## ¿Qué servicios se incluyen en IaaS y PaaS? (Elija dos)

- [x] Servidores de almacenamiento
- [ ] Herramientas de desarrollo
- [ ] Sistemas Operativos
- [x] Firewalls

> Los firewalls y los servidores de almacenamiento se incluyen tanto en IaaS como en Paas.
:::

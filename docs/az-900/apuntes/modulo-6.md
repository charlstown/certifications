# M6 Precios y ciclo de vida

## 1. Planificación y gestión de costes

### Factores que afectan a los costes

| Factores                 | Descripción                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Tipos de recurso         | Costes específicos del recurso y sus capacidades.                                                                           |
| Servicios                | Tasas de uso y planes.                                                                                                      |
| Ubicación                | El coste del servicio en la región varía en función del coste de la luz, etc.                                               |
| Ancho de banda           | El trafico entrante es gratuito, en cambio el tráfico saliente no es gratuito.                                              |
| Instancias reservadas    | Reservas de Az. que nos permite ahorrar instancias de VMs por ejemplo si sabemos que vamos a estar usándolas de 1 a 3 años. |
| Ventaja híbrida de Azure | Solo aplica a clientes con licencias contínuas de Assurance, pudiendo usar esas licencias locales a un coste reducido.      |

### Calculadoras de costes (gratis y abiertas)

#### Calculadora de precios 

Nos ayuda a estimar el coste de los productos de Azure.

Permite configurar:
- Región
- Opciones de facturación
- Soporte
- Programas y ofertas
- Precios de desarrollo y pruebas

#### Calculadora de coste total de propiedad (TCO)

Herramienta que nos ayuda a estimar los ahorros que se pueden conseguir migrando la infraestructura a Azure.

Permite comparar costes de infraestructura local Vs. Nube.

### Azure Cost Management

Servicio de Azure que permite gestionar y consultar la información de costes de nuestros recursos.

Ofrece:
- Crear informes de facturación
- Fijar presupuestos
- Alertas
- Recomendaciones de costes

### Opciones para reducir los costes

| Inicial | Opciones                                         |
| ------- | ------------------------------------------------ |
| __RE__  | __Realizar__ análisis de costes (calculadoras)   |
| __SU__  | __Supervisar__ el uso con Azure Advisor          |
| __ES__  | __Establecer__ límites de gastos                 |
| __AP__  | __Aprovechar__ reservas de azure                 |
| __EL__  | __Elegir__ regiones y ubicaciónes de bajo coste  |
| __OB__  | __Observar__ ofertas recientes                   |
| __AP__  | __Aplicar__ etiquetado para identificar recursos |

## 2. Ciclo de vida de los servicios y SLA de Azure

### SLA  de Azure

_Service level agreement:_  describe los compromisos de Microsoft con respecto al tiempo de actividad y la conectividad por sus servicios.

- Los SLAs representan servicios de forma individual.
- Los servicios o características en versión preliminar o sean gratuitos no ofrecen SLA.

El SLA se traduce en __tiempo de actividad y garantía de uso.

El rendimiento esperado debe de ser un porcentaje con un valor entre 99%- 99,999%.

| SLA     | Inactividad mensual |
| ------- | ------------------- |
| 99%     | 7 horas             |
| 99,9%   | 45 minutos          |
| 99,999% | 26 segundos         |

### Factores que afectan al SLA

Para elevar el SLA necesitamos usar despliegues multi-AZ o redundantes (varias regiones).

| SLA Superior                        | SLA inferior                      |
| ----------------------------------- | --------------------------------- |
| Availability zones                  | Uso de varios servicios           |
| Sistemas redundantes (Multi-región) | Elegir servicios gratis o sin SLA |

#### Versión preliminar de los servicios (nunca en producción)

| Tipos                       | SLA | Coste   | Descripción                 |
| --------------------------- | --- | ------- | --------------------------- |
| Privada                     | No  | Menor   | Por invitación de Microsoft |
| Pública                     | No  | Menor   | Todos tiene acceso          |
| Disponibilidad General (GA) | Si  | Oficial | Todos tiene acceso          |

#### Planes de soporte de Azure

| Planes              | Precio | Descripción                                                            |
| ------------------- | ------ | ---------------------------------------------------------------------- |
| Basic               | 0$     | Recomendaciones de precio                                              |
| Developer           | 30$    | Guias de arquitectura                                                  |
| Standard            | 100$   | Soporte por gravedad mejora por nivel.                                 |
| Professional Direct | 1000$  | Grupos de expertos de arquitectura y operaciones y formación gratuita. |
### Ciclo de vida de servicios en Azure

### Planes de soporte
# Módulo 2 - Servicios principales

Test de 10 preguntas relacionadas con el [módulo 2](../apuntes/modulo-2.md) de servicios principales en Azure.

!!! info ""

    Puedes ver la solución a cada pregunta haciendo click al icono _:octicons-light-bulb-16: Mostrar pista_.

:::{quizdown}

---
primaryColor: "#00bda4"
shuffleQuestions: false
shuffleAnswers: true
---

## Seleccione solo las afirmaciones que sean ciertas

- [ ] Las regiones son ubicaciones físicas formadas por uno o más centros de datos.
- [x] Azure Resource Manager le ayuda a  crear, configurar, administrar y eliminar recursos.
- [x] Las geografías ayudan a los clientes a mantener los datos en diferentes regiones.

> Availability zones (zonas de disponibilidad), no las regiones, son ubicaciones físicas formadas por uno o más centros de datos.

## Ordena cada opción de suscripción para que coincida con sus características: 1 - Gratis, 2 - Pay-As-You-Go

1. Es válida por 30 días.
2. Requiere una tarjeta de débito o de crédito.

## Seleccione solo las afirmaciones que sean ciertas relativas a los grupos de gestión en Azure

- [x] Un grupo de gestión puede admitir varias suscripciones.
- [ ] Un grupo de gestión puede tener varios padres.
- [x] Un grupo de gestión puede soportar RBAC.

> Mientras que un grupo de gestión puede tener muchos hijos, un grupo de gestión sólo puede tener un padre.

## Un administrador quiere asegurarse de que una máquina virtual y una aplicación estén disponibles incluso cuando el centro de datos que aloja esos recursos se desconecte. Qué debería utilizar el administrador para la máquina virtual y la aplicación para cumplir este requisito?

1. [x] Zonas de disponibilidad
2. [ ] Regiones
3. [ ] Conjunto de disponibilidad
4. [ ] Actualizar dominios

> Las zonas de disponibilidad, de las que hay un mínimo de tres en cada región, están formadas por uno o más centros de datos, cada uno de los cuales tiene su propia red, energía y refrigeración. Si uno de los centros de datos se cae, los otros centros de datos se encargan de la carga de trabajo. Las zonas de disponibilidad se encuentran dentro de las regiones.

## Selecciona las dos afirmaciones sobre regiones y los pares de regions que son ciertas

- [x] Las actualizaciones planificadas se producen en una sola región a la vez dentro de un par de regiones.
- [ ] Los pares de regiones emparejan regiones en la misma zona geográfica y a menos de 300 millas de distancia.
- [x] Las regiones pueden estar especializadas para fines gubernamentales.
- [ ] Todas las regiones contienen múltiples centros de datos.

> Mientras que algunas regiones contienen múltiples centros de datos, no todas las regiones contienen múltiples centros de datos. Los pares de regiones emparejan regiones en la misma zona geográfica pero con una distancia mínima de 300 millas.

## ¿Cuál es la capa más externa en el concepto de seguridad de defensa en profundidad?

1. [ ] Perímetro
2. [x] Seguridad física
3. [ ] Identidad y acceso
4. [ ] Red

> De lo externo a lo interno, las capas de defensa en profundidad son la seguridad física, la identidad y el acceso, el perímetro, la red, el cálculo, la aplicación y los datos.

## Tiene datos en una red para el departamento de ventas, una red virtual de Azure. Debe asegurarse de que los datos estén encriptados a medida que viajan de ida y vuelta al departamento de Operaciones, una red local. ¿Qué servicio principal de Azure debe usar para garantizar que los datos estén encriptados?

1. [ ] Azure Key Vault
2. [ ] Content Delivery Network
3. [x] VPN Gateway
4. [ ] Application Gateway

> Un gateway VPN se usa para enviar tráfico cifrado entre una red local y una red virtual de Azure.

## Selecciona solo aquellas afirmaciones que sean ciertas sobre los servicios de bases de datos de Azure

- [ ] Azure SQL database se utiliza para datos sin esquema y aplicaciones Siempre activas.
- [x] Azure SQL database es un motor de base de datos relacional.
- [x] Azure SQL Data Warehouse permite ejecutar análisis de datos a muy alta escala.

> Azure Cosmos DB se usa para datos sin esquema y aplicaciones siempre activas.

## Ordena cada término de cumplimiento para que coincida con sus características: 1 - GDPR, 2 - ISO, 3 - NIST

1. Ley de privacidad Europea.
2. Contiene el código de prácticas 27018.
3. Tiene el marco de seguridad cibernética.

## Ordena cada término de cumplimiento para que coincida con sus características: 1 - Azure Virtual Network, 2 - VPN gateway, 3 - Azure Application Gateway, 4 - Content Delivery Network.

1. Permite que las máquinas virtuales de Azure se comuniquen entre sí de forma segura.
2. Se utiliza para enviar tráfico cifrado hacia y desde una ubicación local.
3. Permite la gestión del tráfico a las aplicaciones web.
4. Ayuda a minimizar la latencia.

:::

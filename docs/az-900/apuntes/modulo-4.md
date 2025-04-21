
# M4 Seguridad

## 1. Seguridad en Azure

### Security center

Servicio de supervisión (el antivirus) dentro de Azure y en los CPDs. 

- Proporciona recomendaciones de seguridad y uuna puntuación de nuestra implementación.
- Bloquea malware.
- Analiza posibles ataques.
- Control de accesos a puertos.

_Se integra con Azure Advisor._

### Sentinel
Herramienta SOAR (Security Orchestration and Response) que nos ayuda a tratar con amenazas.

- Recopila logs
- Responde con acciones

### Key vault

Almacen de secretos en la nube. Se puede realizar una petición get HTTP para cargar un secreto o con SDK.

- Generación de claves en plan premium


### Host dedicados

Servidor físico que aloja varias máquinas virtuales y que garantiza que será dedicado enteramente a la organización que lo solicite.

## 2. Conectividad de red Segura

### Defensa en profundidad

Concepto de defensa en un modelo por capas, en el que se añade un mecanismo de seguridad en cada una de las capas hasta llegar a los datos.

- Seguridad física
- Identidad y acceso
- Perímetro -> NSGs + Gateway
- Red -> Firewall
- Proceso
- Aplicación
- Datos

### Modelo de seguridad compartida

Conceptos que recaen sobre nuestra responsabilidad o sobre la del proveedor.

| Responsabilidad   | IaaS        | PaaS        | SaaS        |
| ----------------- | ----------- | ----------- | ----------- |
| Centro de datos   | _Microsoft_ | _Microsoft_ | _Microsoft_ |
| Red física        | _Microsoft_ | _Microsoft_ | _Microsoft_ |
| Host físico       | _Microsoft_ | _Microsoft_ | _Microsoft_ |
| Sistema operativo | Cliente     | _Microsoft_ | _Microsoft_ |
| Controles de red  | Cliente     | M/C         | _Microsoft_ |
| Aplicación        | Cliente     | M/C         | _Microsoft_ |

### Grupos de segurida y firewall

#### Network Security Groups (NSGs)

Filtran el tráfico de la red hacia y desde los recursos de Azure en redes virtuales.

- Dirección IP
- Puerto
- Protocolo origen y destino
- Sin límite de reglas
- Prioridad en las reglas

#### Firewall

Se trata de un servicio con estado administrado totalmente por Azure, permitiendo o denegando el acceso de la dirección IP, origen o destino.


```ad-info
title: Azure Application Gateway

Es un SaaS que permite exponer una única URL a internet y con un proxy inverso redirigir el tráfico.
```

### Protección frente a DDoS

Azure ofrece un servicio gestionado de prevención de DDoS.

- __Servicio básico:__ Gratuito y solo filtra tráfico sospechoso pero sin logging ni alertas.
- __Estándar:__ Con coste (3K), con capacidades como loggin, alertas, ML, etc.

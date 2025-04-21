# M5 Gobierno

## 1. Servicio principales identidad Azure

## Autenticación Vs Autorización

- __Autenticación:__ Identificar que usuario o servicio intenta acceder a un recurso concreto.
	- Requiere credenciales
- __Autorización:__ Determina el nivel de acceso de un usuario o servicio autenticados previamente sobre un recurso.

## Azure MFA

Autenticación mediante MFA de Azure. Proporciona seguridad adicional.

## Azure AD

Active Directory es el servicio de administración de identidad y acceso basado en la nube de Microsoft.

Proporciona:
- Autenticación
- Inicio de sesión único
- Administración de apps
- Administración de servicios

### Acceso condicional (CA)

Un sistema de Azure AD que reune señales, toma decisiones y aplica directivas de la organización referentes a la autenticación.

Señales:
- Usuario y/o grupo
- Ubicación de la IP
- Dispositivo o aplicación


## 2. Gobernanza en Azure

### Acceso Basado en Roles (RBAC)

Acceso específico a recursos utilizando un rol. Permite la separación de tareas dentro del equipo. Cada rol tiene acceso únicamente a los recursos que necesita.

### Bloqueo de recursos

Podemos proteger recursos de Azure de la eliminación o modificación  accidental.

Activación:
- A nivel suscripción para todos los recursos
- A nivel grupo (RG)
- A nivel individual

### Etiquetas

No tienen una funcionalidad técnica, nos sirve para generar taxonomías en pares clave valor. Son útiles a efectos de facturación.

### Azure Policy

Ayuda a cumplir los estándares que una organización haya definido a la hora de gestionar los recursos de las suscripciones.

Tipos:
- Deny
- Audit
- Audit-if-not-exist
- Deploy-if-not-exist
- Modify

### Blueprints

Permite que los equipos de desarrollo puedan construir y poner en marcha entornos de trabajo rápidamente.

__El blueprint incluye todo, roles, políticas, etc.__

### Cloud Adoption Framework

Las diferentes fases que, según Microsoft, debe seguir una empresa que quiera migrar o crear infraestructura en su nube.

## 3. Privacidad y cumplimiento

### Términos y requisitos de cumplimiento

Microsoft ofrece un conjunto de ofertas de cumplimiento más completo que el de cualquier otro proveedor de servicios en la nube.

- CJIS
- HIPAA
- ...

### Declaración de privacidad y condiciones de uso

La declaración de privacidad de Microsoft proporciona información acerca de cómo Microsoft maneja los datos.

- Qué datos procesa
- De que forma los procesa
- Para qué los usa

### Condiciones y protecciones de datos

- __Condiciones de servicios en línea:__ La licencia define los términos y condiciones de productos y servicios en linea.
- __Anexo de protección de datos:__ Establece obligaciones de Azure con respecto al procesamiento y la seguridad de los datos del cliente.

### Regiones Soberanas

Regiones físicamente separadas de otras de uso público, destinadas al gobierno de algunos países.
- Azure china
- Azure Goverment
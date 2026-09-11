# Club Mirabueno BPM

Proyecto académico desarrollado para la asignatura de Sistemas de Información Empresariales (BPM), cuyo objetivo es modelar y automatizar diferentes procesos operativos del Club Mirabueno mediante **Bonita BPM**.

## Descripción del Proyecto

Este proyecto implementa una solución BPM para digitalizar y automatizar procesos clave de gestión dentro de un club deportivo, mejorando la eficiencia operativa, la trazabilidad de las actividades y la coordinación entre los distintos empleados.

El sistema ha sido desarrollado utilizando **Bonita Studio** e integra diferentes funcionalidades como:

- Gestión de usuarios, roles y organizaciones.
- Modelado de datos mediante Objetos de Negocio (BDM).
- Formularios y contratos personalizados.
- Validaciones de datos.
- Gestión documental.
- Filtros de actores.
- Integración con sistemas externos mediante **n8n** y **Odoo**.
- Aplicación personalizada para facilitar el uso del sistema.

---

## Configuración Inicial

Durante la fase inicial se realizaron las siguientes tareas:

### Organización

Se definió la estructura organizativa del club incluyendo:

- Grupos
- Roles
- Usuarios
- Relaciones entre usuarios y roles

### Control de Versiones

El proyecto se integró con GitHub para facilitar el desarrollo colaborativo y el control de versiones.

---

## Modelo de Datos

Se diseñó un conjunto de **Objetos de Negocio (Business Data Model)** para almacenar toda la información necesaria de los distintos procesos gestionados por el sistema.

Estos objetos permiten:

- Gestionar incidencias.
- Administrar socios.
- Gestionar empleados.
- Almacenar información de suscripciones.
- Gestionar documentación asociada a los trabajadores.

---

# Procesos Implementados

## 1. Gestión de Incidencias

Automatiza el tratamiento de averías o problemas detectados en las instalaciones del club.

### Flujo del proceso

1. Un trabajador registra una incidencia.
2. El jefe de mantenimiento evalúa el coste de reparación.
3. Se toma una decisión:
   - Si el coste es menor o igual a 50 € → aprobación automática.
   - Si el coste supera los 50 € → requiere aprobación del gerente.
4. Se resuelve la incidencia.
5. La información se registra automáticamente en Odoo mediante una integración con n8n.

### Actores

- Recepcionista
- Monitor
- Jardinero
- Jefe de mantenimiento
- Gerente

### Características destacadas

- Formularios personalizados.
- Contratos basados en objetos de negocio.
- Integración externa con Odoo.
- Automatización de aprobaciones por importe.

---

## 2. Alta de Nuevo Socio

Permite gestionar la incorporación de nuevos miembros al club.

### Flujo del proceso

1. El recepcionista registra la solicitud.
2. El gerente revisa y aprueba la solicitud.
3. Si no se valida en un plazo de tres días, se envía un recordatorio automático.
4. Se crea la suscripción del socio.
5. El recepcionista entrega las llaves, credenciales o material correspondiente.

### Actores

- Recepcionista
- Gerente

### Características destacadas

- Recordatorios automáticos.
- Gestión de suscripciones.
- Validación administrativa previa al alta.

---

## 3. Baja de Socio

Gestiona la salida de socios del club.

### Flujo del proceso

1. El recepcionista registra la solicitud de baja.
2. El gerente analiza los motivos e intenta aplicar estrategias de retención.
3. El socio confirma la baja.
4. Se actualiza la suscripción en el sistema.
5. Se envía automáticamente una encuesta de satisfacción.
6. El gerente revisa el informe final y cierra el proceso.

### Actores

- Recepcionista
- Gerente

### Características destacadas

- Estrategias de retención.
- Encuestas automáticas.
- Seguimiento completo del proceso de baja.

---

## 4. Contratación de Nuevo Empleado

Gestiona la incorporación de nuevos trabajadores al club.

### Flujo del proceso

1. El gerente registra al nuevo empleado.
2. Se crea su ficha en el sistema.
3. Se adjunta su CV mediante gestión documental.
4. El recepcionista realiza el onboarding inicial.
5. Si el empleado es monitor:
   - El gerente asigna un instructor.
   - Se realiza una formación básica.

### Actores

- Gerente
- Recepcionista
- Monitor instructor

### Características destacadas

- Gestión documental de currículums.
- Filtros de actores.
- Asignación dinámica de instructores.
- Formación específica para monitores.

---

# Validaciones Implementadas

Para garantizar la calidad de los datos se implementaron las siguientes restricciones:

| Validación | Restricción |
|------------|------------|
| Edad mínima de socio | ≥ 12 años |
| Edad mínima de empleado | ≥ 18 años |
| Correo electrónico | Debe contener "@" |
| Teléfono | Exactamente 9 dígitos |
| DNI | 8 números y 1 letra |
| IBAN español | 2 letras y 22 números |

---

# Aplicación Personalizada

Además de los procesos BPM, se desarrolló una aplicación personalizada para facilitar la interacción de los usuarios con el sistema.

## Centro de Control de Incidencias

Página destinada a la visualización y gestión de incidencias.

Características:

- Tabla conectada al Business Data Model.
- Consulta centralizada de incidencias.
- Gestión simplificada para el personal del club.

## FAQ para Recepcionistas

Página de ayuda que recopila preguntas frecuentes sobre:

- Gestión de socios.
- Gestión de incidencias.
- Gestión de empleados.
- Uso general de la aplicación.

---

## Tecnologías Utilizadas

- Bonita Studio
- Bonita BPM
- Business Data Model (BDM)
- GitHub
- n8n
- Odoo

---

## Objetivos Alcanzados

- Digitalización de procesos internos.
- Automatización de tareas repetitivas.
- Mejora de la trazabilidad de las operaciones.
- Integración con sistemas externos.
- Validación de datos de entrada.
- Desarrollo de una aplicación de soporte para usuarios finales.

---

## Contexto Académico

Este proyecto fue realizado como trabajo universitario con el objetivo de aplicar conceptos de:

- Business Process Management (BPM)
- Modelado de procesos
- Automatización de flujos de trabajo
- Integración de sistemas
- Gestión organizativa
- Diseño de aplicaciones empresariales

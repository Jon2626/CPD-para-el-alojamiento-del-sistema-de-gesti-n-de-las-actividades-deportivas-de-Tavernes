#  Proyecto CPD: Sistema de Gestión de Actividades Deportivas de Tavernes

##  Resumen General
Este proyecto tiene como objetivo la planificación e implementación de un Centro de Proceso de Datos (CPD) que aloje un sistema de gestión deportiva. Se busca ofrecer una infraestructura segura, escalable y eficiente para soportar las reservas, pagos, gestión de usuarios y comunicaciones asociadas a las actividades deportivas municipales.

##  Objetivos 
En la sección de objetivos, se estableció claramente lo que se pretende lograr con la creación del CPD (Centro de Procesamiento de Datos). Se dejó en claro que este CPD estará dedicado exclusivamente a gestionar las actividades deportivas de Tavernes. Los objetivos se enfocan en asegurar un funcionamiento eficiente, seguro y escalable del sistema, incluyendo características como la centralización de la información de usuarios, pistas y reservas; la automatización de tareas para minimizar la intervención manual; el envío de notificaciones automáticas; la integración de herramientas para planificar horarios y disponibilidad; la implementación de copias de seguridad y un plan de recuperación ante desastres; el desarrollo de una app móvil para reservas; el soporte técnico continuo; la conexión con sistemas de pago y la capacidad de escalar el sistema según las necesidades futuras. Esta sección establece la dirección de todo el proyecto.

## Requisistos
El análisis de requisitos se organizó en dos partes: una para el sistema de gestión y otra para el CPD.

Primero, los requisitos del sistema de gestión se enfocaron en las funciones que estarán al alcance del usuario. Esto incluye el inicio de sesión con credenciales, la opción de recibir correos de confirmación tras hacer reservas, un sistema de carrito para manejar las pistas o espacios deportivos que el usuario desea reservar, una pasarela de pago segura y una interfaz amigable que sea accesible para personas de todas las edades.

Luego, los requisitos del CPD se centraron en garantizar que el sistema funcione de manera óptima a nivel técnico. Se definieron métricas de rendimiento, como que la respuesta del sistema no exceda los 2 segundos, y se consideraron aspectos de seguridad, como el cifrado RSA en las comunicaciones. También se incluyó la necesidad de que el servicio esté disponible de forma continua, la integridad de los datos, la capacidad de recuperación ante fallos en menos de 30 minutos, el soporte para hasta 1000 usuarios simultáneos, la confidencialidad de la información personal de los usuarios y la compatibilidad con múltiples plataformas, incluyendo Windows y Linux.

## WBS (Work Breakdown Structure)
En esta sección, hemos creado un desglose detallado de todas las tareas del proyecto, dividiéndolo en partes más pequeñas y manejables. Esta estructura es clave para organizar, planificar y asignar responsabilidades dentro del equipo. Sin embargo, en el documento, esta información se presenta únicamente a través de un gráfico, lo que significa que no se describen los elementos de forma textual. Por lo tanto, aunque se realizó un desglose visual de las tareas, no podemos ofrecer una explicación detallada aquí debido a la falta de texto complementario.

## Cronograma
Se elaboró un cronograma que ilustra las diferentes fases del proyecto durante el primer sprint. Este cronograma nos ayuda a ver claramente la secuencia de actividades, las fechas de inicio y finalización, y cómo se conectan las tareas a lo largo del tiempo. Al igual que en el caso anterior, esta sección está disponible únicamente en formato de imagen, lo que impide ofrecer una explicación detallada sobre el contenido específico de cada fase.

## Roles y Responsabilidades
Se han asignado formalmente tres roles: el Líder del Proyecto, el Administrador de Infraestructura TI y el Gestor de Riesgos.

El Líder del Proyecto es quien se encarga de la planificación general, dividiendo el proyecto en tareas, asignando responsables y asegurándose de que se cumplan los plazos y objetivos. Por otro lado, el Administrador de Infraestructura TI tiene la tarea de seleccionar y configurar el hardware y software, mantener la red y la seguridad, y garantizar que se cumplan las normativas. Finalmente, el Gestor de Riesgos se ocupa de identificar posibles amenazas, desarrollar estrategias para mitigarlas, gestionar incidentes y hacer un seguimiento continuo de los riesgos.

## Tareas Asignadas
Cada miembro del equipo tenía su propia tarea asignada. Jonman Jiménez, en su rol como Líder del Proyecto, se encargó de planificar y dividir el proyecto utilizando la estructura WBS. También elaboró un cronograma detallado, asignó responsabilidades y coordinó todo el proceso. Jaime Climent, como Administrador TI, se dedicó a identificar las necesidades de hardware y software, además de evaluar las capacidades necesarias. Por su parte, Frances Simó, en su papel de Gestor de Riesgos, planificó la adquisición de recursos, hizo una lista de lo que se necesitaba y desarrolló planes de contingencia. Cada tarea fue programada con fechas de inicio y fin para garantizar que se cumplieran dentro del sprint.

## Tareas en Equipo
Además de las tareas individuales, se realizaron varias actividades en conjunto. El equipo colaboró para establecer los objetivos generales del CPD, definió tanto los requisitos funcionales como los no funcionales, revisó todo el plan del proyecto para asegurarse de que fuera sólido y buscó la aprobación del profesor o de los responsables asignados. Estas acciones reflejan el trabajo en equipo y la coordinación grupal durante la fase inicial del desarrollo.

##  Equipo de Desarrollo
- Frances Simó Olma  
- Jaime Climent Cardona  
- Jonman Jiménez Mendoza


##  Arquitectura del CPD

### Infraestructura
- **Ubicación física:** Sala de servidores con ventilación, seguridad y accesibilidad óptimas.
- **VLANs configuradas:**
  - **VLAN de estaciones**: Aísla el tráfico de usuarios.
  - **VLAN de servidores**: Mayor control y seguridad.
  - **VLAN de backups**: Almacenamiento y gestión de copias de seguridad.

### Servidores
- **Servidor principal:** Alojamiento de la base de datos y servicios web.
- **Servidor de respaldo:** Ubicado en otra instalación para recuperación ante desastres y balanceo de carga.

##  Seguridad y Disponibilidad
- **Cifrado de comunicaciones:** Protocolos seguros como RSA y TLS.
- **Backups automáticos:** Copias diarias en local y remoto.
- **Alta disponibilidad:** Sistema replicado para garantizar continuidad.
- **Control de accesos:** Autenticación por roles.

##  Recuperación del Sistema

### Procedimientos ante fallos:
1. **Caída del servidor principal:** Activación del servidor de respaldo mediante balanceador de carga.
2. **Fallo de red interna:** Reconfiguración automática de VLANs prioritarias.
3. **Pérdida de datos:** Restauración desde backups automáticos almacenados en remoto.
4. **Desastre físico (incendio/inundación):** Migración de servicios al CPD alternativo previamente sincronizado.


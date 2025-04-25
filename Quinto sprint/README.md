# 1. Proyecto CPD: Sistema de Gestión de Actividades Deportivas de Tavernes

## 1.1 Resumen General
Este proyecto tiene como objetivo la planificación e implementación de un Centro de Proceso de Datos (CPD) que aloje un sistema de gestión deportiva. Se busca ofrecer una infraestructura segura, escalable y eficiente para soportar las reservas, pagos, gestión de usuarios y comunicaciones asociadas a las actividades deportivas municipales.

## 1.2 Objetivos 
En la sección de objetivos, se estableció claramente lo que se pretende lograr con la creación del CPD (Centro de Procesamiento de Datos). Se dejó en claro que este CPD estará dedicado exclusivamente a gestionar las actividades deportivas de Tavernes. Los objetivos se enfocan en asegurar un funcionamiento eficiente, seguro y escalable del sistema, incluyendo características como la centralización de la información de usuarios, pistas y reservas; la automatización de tareas para minimizar la intervención manual; el envío de notificaciones automáticas; la integración de herramientas para planificar horarios y disponibilidad; la implementación de copias de seguridad y un plan de recuperación ante desastres; el desarrollo de una app móvil para reservas; el soporte técnico continuo; la conexión con sistemas de pago y la capacidad de escalar el sistema según las necesidades futuras. Esta sección establece la dirección de todo el proyecto.

## 1.3 Requisistos
El análisis de requisitos se organizó en dos partes: una para el sistema de gestión y otra para el CPD.

Primero, los requisitos del sistema de gestión se enfocaron en las funciones que estarán al alcance del usuario. Esto incluye el inicio de sesión con credenciales, la opción de recibir correos de confirmación tras hacer reservas, un sistema de carrito para manejar las pistas o espacios deportivos que el usuario desea reservar, una pasarela de pago segura y una interfaz amigable que sea accesible para personas de todas las edades.

Luego, los requisitos del CPD se centraron en garantizar que el sistema funcione de manera óptima a nivel técnico. Se definieron métricas de rendimiento, como que la respuesta del sistema no exceda los 2 segundos, y se consideraron aspectos de seguridad, como el cifrado RSA en las comunicaciones. También se incluyó la necesidad de que el servicio esté disponible de forma continua, la integridad de los datos, la capacidad de recuperación ante fallos en menos de 30 minutos, el soporte para hasta 1000 usuarios simultáneos, la confidencialidad de la información personal de los usuarios y la compatibilidad con múltiples plataformas, incluyendo Windows y Linux.

## 1.4 WBS (Work Breakdown Structure)
En esta sección, hemos creado un desglose detallado de todas las tareas del proyecto, dividiéndolo en partes más pequeñas y manejables. Esta estructura es clave para organizar, planificar y asignar responsabilidades dentro del equipo. Sin embargo, en el documento, esta información se presenta únicamente a través de un gráfico, lo que significa que no se describen los elementos de forma textual. Por lo tanto, aunque se realizó un desglose visual de las tareas, no podemos ofrecer una explicación detallada aquí debido a la falta de texto complementario.

## 1.5 Cronograma
Se elaboró un cronograma que ilustra las diferentes fases del proyecto durante el primer sprint. Este cronograma nos ayuda a ver claramente la secuencia de actividades, las fechas de inicio y finalización, y cómo se conectan las tareas a lo largo del tiempo. Al igual que en el caso anterior, esta sección está disponible únicamente en formato de imagen, lo que impide ofrecer una explicación detallada sobre el contenido específico de cada fase.

## 1.6 Roles y Responsabilidades
Se han asignado formalmente tres roles: el Líder del Proyecto, el Administrador de Infraestructura TI y el Gestor de Riesgos.

El Líder del Proyecto es quien se encarga de la planificación general, dividiendo el proyecto en tareas, asignando responsables y asegurándose de que se cumplan los plazos y objetivos. Por otro lado, el Administrador de Infraestructura TI tiene la tarea de seleccionar y configurar el hardware y software, mantener la red y la seguridad, y garantizar que se cumplan las normativas. Finalmente, el Gestor de Riesgos se ocupa de identificar posibles amenazas, desarrollar estrategias para mitigarlas, gestionar incidentes y hacer un seguimiento continuo de los riesgos.

## 1.7 Tareas Asignadas
Cada miembro del equipo tenía su propia tarea asignada. Jonman Jiménez, en su rol como Líder del Proyecto, se encargó de planificar y dividir el proyecto utilizando la estructura WBS. También elaboró un cronograma detallado, asignó responsabilidades y coordinó todo el proceso. Jaime Climent, como Administrador TI, se dedicó a identificar las necesidades de hardware y software, además de evaluar las capacidades necesarias. Por su parte, Frances Simó, en su papel de Gestor de Riesgos, planificó la adquisición de recursos, hizo una lista de lo que se necesitaba y desarrolló planes de contingencia. Cada tarea fue programada con fechas de inicio y fin para garantizar que se cumplieran dentro del sprint.

## 1.8 Tareas en Equipo
Además de las tareas individuales, se realizaron varias actividades en conjunto. El equipo colaboró para establecer los objetivos generales del CPD, definió tanto los requisitos funcionales como los no funcionales, revisó todo el plan del proyecto para asegurarse de que fuera sólido y buscó la aprobación del profesor o de los responsables asignados. Estas acciones reflejan el trabajo en equipo y la coordinación grupal durante la fase inicial del desarrollo.

## 2. Diseño de la arquitectura

<img src="/img/sprint1/1. Diseño de la arquitectura del diseñov2.jpg" width="50%" height="auto" alt="Mi Foto">

Vlans:
Vlan Estaciones: 192.168.10.0
Vlans Servidores: 192.168.20.0
Vlan Backups: 192.168.30.0

Se ha elegido esta sala de servidores porque cumple con los requisitos de seguridad, ventilación y accesibilidad necesarios para un correcto funcionamiento. Además, ofrece el espacio adecuado para la instalación y mantenimiento del equipo, garantizando una infraestructura estable y eficiente.

Por otra parte, se han creado tres VLANs: una destinada a las estaciones, con el fin de no mezclar información y evitar la saturación de la red; otra para los servidores, con el objetivo de incrementar la seguridad y la fiabilidad; y una tercera para backups, ya que se requiere un espacio separado para almacenar toda la información. Además, se ha instalado un servidor de respaldo en otro edificio como medida de prevención ante riesgos como incendios, inundaciones, etc., con el propósito de no perder los datos almacenados y permitir el balanceo de carga, es decir, transferir toda la información al servidor de respaldo en caso necesario.

## 2.1 Selección de hardware y software 

### 2.1.2 Hardware 

| **ELEMENTO** | **CANTIDAD** | **COSTE (unidad)** | **COSTE TOTAL** |
| ------------------------ | - | - | - |
| Servidor de aplicaciones  | 1 | 3.776€ | 3.776€ |
| Servidor de bases de datos | 1 | 4.777€ | 4.777€ |
| Servidor de respaldo | 2 | 3.000 € | 6.000 € |
| NAS (10TB escalable) | 1 | 1.500 € | 1.500 € |
| Estaciones de trabajo | 3 | 800 € | 2.400 € |
| Switches de red Gigabit (paquete 24) | 2 | 215€ | 430€ |
| Routers | 2 | 210€ | 420€ |
| AP Wifi | 1 | 137€ | 137€ |
| Medidas de seguridad físicas | 1 | 3.500 € | 3.500 € |
| SAI | 1 | 278€ | 278€ |
| **TOTAL** | | | **28.318 €** |

**Servidor de aplicaciones:**  

- Hemos utilizado un servidor Dell en concreto el PowerEdge R740, ideal para aplicaciones empresariales exigentes y virtualización  
- Soporta hasta dos procesadores Intel Xenon escalables, nosotros nos hemos decantado por el Intel Xenon Platinum 8253 2.2G 
- Hasta 1 TB pero puede ser escalable de RAM DDR4 (brutal para bases de datos y cargas pesadas). 
- Soporte para NVMe SSDs (velocidad de almacenamiento extrema). 
- Muy usado para virtualización (en nuestro caso Hyper-V), bases de datos y servidores web. 

**Servidor de base de datos:**

- Hemos utilizado un servidor Dell en concreto el PowerEdge R750, ideal especialmente si buscas rendimiento, escalabilidad y confiabilidad en entornos empresariales. 
- Alto rendimiento con procesadores Intel Xeon de última generación. 
- Gran capacidad de memoria RAM (hasta 4 TB) 
- Almacenamiento ultrarrápido con SSD NVMe muy bueno para nuestra empresa ya que nos hace falta fluideza. 

**Servidor de respaldo:** 

- Hemos utilizado un servidor Dell en concreto el PowerEdge R650XS, un servidor de rendimiento equilibrado para respaldo, bases de datos o virtualización
- El R650XS está diseñado para empresas que necesitan un servidor potente pero sin pagar de más por características que quizás no usen.
- Soporta hasta 12 discos (SATA, SAS o NVMe), lo que lo hace ideal para 
- Más memoria permite almacenar más caché en RAM, acelerando bases de 

  datos y reduciendo la dependencia del disco.

**NAS:**

- Hemos utilizado un NAS Synology DS1821ya que es una excelente opción si buscas un NAS potente, escalable y fiable para almacenamiento en red, copias de seguridad o incluso virtualización.
- Gran capacidad de almacenamiento y escalabilidad (8 bahias para discos escalable a 18) 
- Procesador potente con buena eficiencia energética (Usa un AMD Ryzen V1500B) 
- Expansión de RAM hasta 32 GB (Viene con 4 GB DDR4) 

**Estación de trabajo:** 

- Hemos utilizado las estaciones de la marca Dell, en concreto la Dell OptiPlex 7020 ya que es una gran opción si buscas un ordenador de sobremesa potente, fiable y eficiente para oficina, teletrabajo o tareas empresariales.
- Rendimiento potente con Intel Core i5-14500 
- Memoria DDR5 a 4800 MHz, mucho más rápida que la DDR4 (16GB RAM) 
- Disco SSD NVMe de 512GB, hasta 5 veces más rápido que un HDD.

**Switch de red Gigabyte:** 

- Hemos utilizado el switch Tenda TEG1118P-16-250W ya que un switch PoE de 18 puertos Gigabit con funcionalidades avanzadas como VLAN, QoS y transmisión extendida hasta 250 metros, lo que lo hace ideal para redes empresariales, cámaras IP, VoIP y puntos de acceso WiFi.  

**Router:** 

- Hemos utilizado el MikroTik hAP ax³ (C53UiG+5HPaxD2HPaxD) es un router WiFi 6 de alto rendimiento con potente hardware, seguridad avanzada y gran 
flexibilidad, ideal para usuarios exigentes, oficinas y empresariales pequeñas. 
- Procesador potente para multitarea y redes exigentes

**SAI:** 

- Hemos utilizado el SAI Online 1000 VA LCD SH ya que este modelo es ideal para empresas pequeñas y medianas. 
- Proporciona alimentación ininterrumpida en caso de corte de energía, 

  asegurando que tus dispositivos sigan funcionando sin interrupciones.

- El SAI protege contra sobrecargas y cortocircuitos y cuenta con apagado automático cuando la batería está baja para evitar dañar tus dispositivos.

### 2.1.3 Software 

| ELEMENTO                                                  | LICENCIAS | COSTE (unidad) | COSTE TOTAL |
|-----------------------------------------------------------|-----------|----------------|-------------|
| Sistema operativo servidores (Windows Server)             | 4         | 0 €            | 0 €         |
| Soporte empresarial (MySQL)                               | 1         | 2.000 €        | 2.000 €     |
| Software de backup (Aomei Backup)                         | 1         | 700 €          | 700 €       |
| Sistema de virtualización (VMWare Workstation Pro)        | 1         | 193 €          | 193 €       |
| Antivirus y herramientas de seguridad (F-Secure)          | 10        | 10 €           | 100 €       |
| Monitorización (Pandora FMS)                              | 1         | 34 €           | 34 €        |
| **TOTAL**                                                 |           |                | **3.027 €** |


**Sistema operativo servidores:**

- Hemos utilizado Windows Server ya que es idela para empresas pequeñas que no quieren complicarse con otros sistemas operativos.
- Ofrece muchas funciones de seguridad avanzadas (Windows Defender Antivirus y Firewall). 
- Escalabilidad a medida que creces (WS se adapta a las b¡necesidades cambiantes de tu empresa).

**Soporte empresarial:** 

- Hemos utilizado MySQL ya que para una empresa es una opción muy popular debido a su fiabilidad, escalabilidad y flexibilidad, especialmente en entornos 
de bases de datos donde se requiere alta disponibilidad y buen rendimiento.
- MySQL es un sistema de gestión de bases de datos gratuito y de código abierto. 
- MySQL es conocido por su velocidad y eficiencia, manejando con facilidad tanto pequeñas aplicaciones como grandes volúmenes de datos.

**Software de backup:** 

- Hemos utilizado Aomei Backupper ya que es una herramienta de respaldo y recuperación de datos que puede ser muy útil para empresas de cualquier tamaño.  
- AOMEI Backupper permite realizar copias de seguridad completas, incrementales o diferenciales.
- AOMEI Backupper es fácil de usar, incluso para usuarios sin mucha experiencia técnica, con una interfaz gráfica intuitiva.

**Sistema de virtualización:** 

- Hemos utilizado VMWare Workstation Pro ya que es una herramienta de virtualización de escritorios de alto rendimiento que puede ser increíblemente útil para empresas, especialmente en entornos de desarrollo, pruebas y administración de sistemas.
- VMware Workstation Pro permite crear y gestionar múltiples máquinas virtuales en un solo equipo físico. 
- La virtualización permite ejecutar varios sistemas operativos en un solo equipo, lo que reduce la necesidad de hardware adicional y optimiza los recursos.
- Proporciona opciones de cifrado de máquinas virtuales y control de acceso.

## 2.2 Diseño de la seguridad del sistema
Se implementaron diversas defensas para protegerse de posibles ciberataques, incluyendo firewalls, autenticación multifactor, cifrado de datos y auditorías de seguridad. Para minimizar las interrupciones en la red, se propusieron conexiones redundantes, balanceo de carga y medidas de protección contra ataques DDoS. En lo que respecta a la seguridad física, se sugirió el uso de tarjetas de acceso, cámaras de videovigilancia y personal de seguridad. Para hacer frente a desastres naturales y cortes de energía, se incorporaron infraestructuras resistentes, sistemas de extinción, sensores ambientales, SAI y generadores de respaldo.

### 2.2.1 Amenazas internas
Se propuso capacitar al personal, gestionar adecuadamente los accesos con privilegios mínimos, monitorear la actividad interna y asegurar la protección antivirus en las estaciones de trabajo.

### 2.2.2 Políticas de acceso
Se establecieron reglas como la obligación de utilizar VPN cifradas para accesos remotos, la implementación de contraseñas seguras que se actualizan cada tres meses, y la asignación de permisos mínimos necesarios para cada usuario.



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


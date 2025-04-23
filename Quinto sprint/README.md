#  Proyecto CPD: Sistema de Gestión de Actividades Deportivas de Tavernes

##  Resumen General
Este proyecto tiene como objetivo la planificación e implementación de un Centro de Proceso de Datos (CPD) que aloje un sistema de gestión deportiva. Se busca ofrecer una infraestructura segura, escalable y eficiente para soportar las reservas, pagos, gestión de usuarios y comunicaciones asociadas a las actividades deportivas municipales.

##  Objetivos del Proyecto
- Centralizar la información en una base de datos segura.
- Automatizar procesos administrativos y operativos.
- Integrar herramientas de planificación y reserva de actividades.
- Establecer protocolos de respaldo y recuperación ante fallos.
- Garantizar escalabilidad y alta disponibilidad del sistema.
- Incorporar una app móvil para mejorar la experiencia del usuario.

## 🛠 Arquitectura del CPD

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

##  Equipo de Desarrollo
- Frances Simó Olma  
- Jaime Climent Cardona  
- Jonman Jiménez Mendoza

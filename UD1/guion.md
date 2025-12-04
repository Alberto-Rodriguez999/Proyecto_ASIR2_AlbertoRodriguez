# 6. 📝 Guion inicial del proyecto (Roadmap)

![Roadmap](https://img.shields.io/badge/Roadmap%20%7C%20Fases%20%7C%20Planificación--2C3E50?style=for-the-badge&logo=trello)

El desarrollo del sistema **SMEGI** se estructura en cinco fases secuenciales que guiarán la implementación técnica del proyecto:

### 🗓️ FASE 1: Diseño de la Arquitectura 
* **Objetivo:** Definir sobre el papel cómo será la infraestructura antes de implementar.
* **Tareas clave:**
    * Diseño de los diagramas de red (Lógico y Físico).
    * Planificación del direccionamiento IP y definición de las VLANs (Gestión, IoT, Oficina).

### 🏗️ FASE 2: Infraestructura Base 
* **Objetivo:** Instalar los cimientos del sistema: virtualización y servidores.
* **Tareas clave:**
    * Instalación del **hardware físico** y del Hypervisor (**Proxmox VE**).
    * Despliegue de las Máquinas Virtuales (Linux) que alojarán los servicios.

### 🛡️ FASE 3: Seguridad y Red Core 
* **Objetivo:** Segmentar la red y asegurar el perímetro.
* **Tareas clave:**
    * Configuración del **Firewall (PfSense)** y reglas de filtrado entre VLANs.
    * Implementación de servicios básicos (DHCP/DNS) y acceso remoto seguro (**VPN**).

### 📊 FASE 4: Implementación del Sistema SMEGI 
* **Objetivo:** Desplegar la solución de monitorización (el núcleo del proyecto).
* **Tareas clave:**
    * Instalación del servidor de monitorización (**Zabbix**) e integración de sensores.
    * Creación de paneles de visualización de datos en tiempo real con **Grafana**.

### 🏁 FASE 5: Cierre y Aseguramiento 
* **Objetivo:** Proteger el trabajo realizado y documentar.
* **Tareas clave:**
    * Configuración de copias de seguridad automatizadas (Política 3-2-1).
    * Pruebas de estrés y redacción de la documentación técnica final.

![Captura del entorno](./img/fianl.png)

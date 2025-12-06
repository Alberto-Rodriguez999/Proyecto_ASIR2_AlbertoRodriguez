[Volver al índice general](../README.md)

# UD1 – Análisis del entorno y detección de necesidades tecnológicas

## Índice de apartados


# 1. 🍇 Análisis del Sector Tecnológico: Vitivinicultura en Andalucía

![Análisis Sectorial](https://img.shields.io/badge/Análisis%20%7C%20Vitivinicultura%20%7C%20Andalucía--2C3E50?style=for-the-badge&logo=github)

El sector tecnológico es el principal motor de crecimiento en la región de Andalucía, esta centrado en el Parque Científico y Tecnológico Cartuja. Segun el inform de actividad de 2023/2024 este ecosistema contiene 567 empresas y cuenta con una facturacion de casi 5 millones de euros, además, está dando empleo a casi 30 mil personas. Es un volumen de negocio que garantiza una demanda sostenida de adimisntradores de sistemas para gestionar centros de datos y redes coporativas que requieren una alta dispoinibilidad.

Por otro lado Sevilla es la líder en tecnología con el cluster Andalucía Aerospace y la Agencia Espacial Española. De hecho, el inform del Sector Aeroespacial en Andalucía en 2023 registró 2700 millones de euros en facturación, demandando perfiles especializados en cuberseguridad y redes. Por otro lado tenemos inciativas como el proyecto Sevilla NODE que impulsan la necesidad de integrar IoT (Internet de las cosas) apoyandose en servidores seguros y validando la pertinencia técnica.

![Captura del entorno](./img/presentacion.png)


# 2. 🍇 Selección de la empresa o contexto de trabajo

![Seleccion](https://img.shields.io/badge/Selección%20%7C%20Empresa%20%7C%20Andalucía--2C3E50?style=for-the-badge&logo=github)

Este proyecto se basa en Bodegas Finca El Roble S.L., una empresa familiar ficticia pero realista ubicada en la zona de Cazalla de la Sierra (sierra norte de Sevilla). Esta empresa simula las empresas reales de andalucía que se dedican a la producción de vinos tinto bajo la normativa IGP Sierra Norte. En este caso la empresa esta en una fase de expansión internacional por lo que han visto necesario cumplir con los estándares de calidad europeos. Su estructura organizativa tiene una base tradicional, con departamentos de produccion y administración pero carece de un deparetamento dedicado a la informática interna.

La situacion tecnologica actual de la empresa resulta en un riesgo critico ya que la bodega opera con una red plana sin segmentación, por lo que mezclan trafico de red de maquinarias, invitados y trabajadores internos. Por esto vemos que sus datos más críticos están alojados en PCs individuales sin ningún tipo de copias de seguridad. Por otro lado el control de temperatura de las naves donde se cria el vino se hace individualmente, algo demasiado tosco y desactualizado para el nivel de expandión que está alcanzando la empresa.

![Captura del entorno](./img/banner1.png)

##### *Nos hemos basado en una empresa ficticia: Bodegas Finca El Roble S.L *


# 3. 🍇  Identificación de necesidades tecnológicas


![Seleccion](https://img.shields.io/badge/Identificación%20%7C%20Tecnología%20%7C%20Andalucía--2C3E50?style=for-the-badge&logo=github)

El análisis técnico de **Bodegas Finca El Roble** no se ha realizado de forma aislada, sino contrastando la situación de la empresa con los estándares y recomendaciones actuales del sector en España. Basándonos en documentación oficial del **Ministerio de Agricultura (MAPA)** y el **Instituto Nacional de Ciberseguridad (INCIBE)**, se han detectado brechas críticas que justifican la intervención.

### 3.1. Justificación Documental del Análisis

La auditoría interna ha revelado tres problemas estructurales que coinciden con las deficiencias habituales del sector:

1.  **Desconexión de Datos (Justificación de Monitorización):**
    Según el *II Estudio del Observatorio de la Digitalización del Sector Agroalimentario (MAPA)*, una de las mayores barreras de competitividad es la "falta de integración automatizada de datos". La bodega gestiona la temperatura manualmente, lo cual, según la *Hoja de Ruta de la OIVE*, impide garantizar la calidad constante del producto.
    * **Solución:** Se requiere un sistema **SMEGI** (Zabbix+Grafana) que automatice la captura de datos, eliminando el error humano.

2.  **Vulnerabilidad de la Red (Justificación de Seguridad/VLANs):**
    Actualmente, la red de la bodega es plana (todos los equipos en la misma red). La *Guía de Ciberseguridad para el sector Agroalimentario del INCIBE* alerta explícitamente de que "la convergencia de redes IT (Oficina) y OT (Operación/Maquinaria) sin segmentación aumenta drásticamente el riesgo de ciberataques".
    * **Solución:** Es imperativo implementar **segmentación de red mediante VLANs** y un **Firewall perimetral** (PfSense) para aislar los sensores industriales de la red administrativa.

3.  **Riesgo de Continuidad (Justificación de Virtualización):**
    La dependencia de ordenadores personales para procesos críticos incumple los principios básicos de disponibilidad.
    * **Solución:** Siguiendo las mejores prácticas de administración de sistemas, se debe migrar a una arquitectura de **Virtualización (Proxmox)** que permita copias de seguridad integrales y recuperación ante desastres.

  ![Captura del entorno](./img/innova.jpg)
  ---

### 3.2. Matriz de Necesidades y Solución Tecnológica

En base a la normativa y los informes citados, se define la siguiente matriz de necesidades que guiará el proyecto:

| 📉 Problema Detectado | 📜 Fuente / Justificación | 🚀 Solución propuesta |
| :--- | :--- | :--- |
| **Gestión Manual de Temperaturas** | *OIVE:* La falta de datos en tiempo real afecta a la calidad del vino. | **Sistema de Monitorización:** Despliegue de **Zabbix** para lectura de sensores y alertas automáticas. |
| **Red Plana e Insegura** | *INCIBE:* Riesgo alto por mezclar tráfico de gestión y maquinaria. | **Seguridad de Red:** Diseño de **VLANs** (VLAN 10 Gestión, VLAN 20 IoT) y reglas de **Firewall**. |
| **Servidores en "Hierro" (PC)** | *MAPA:* Baja resiliencia ante fallos en PyMEs. | **Virtualización:** Cluster o nodo único con **Hypervisor** para alta disponibilidad de servicios. |
| **Acceso Remoto Inexistente** | Necesidad operativa de control 24/7. | **Conectividad Segura:** Implementación de **VPN** (OpenVPN/Wireguard) para administración remota. |

# 4. 🍇  Oportunidades y viabilidad del proyecto
![Viabilidad](https://img.shields.io/badge/Viabilidad%20%7C%20Técnica%20%7C%20Económica--2C3E50?style=for-the-badge&logo=google-analytics)

Tras el análisis de necesidades, la implementación del sistema **SMEGI** (Sistema de Monitorización y Gestión Energética Inteligente) se presenta no solo como una solución a problemas actuales, sino como una oportunidad estratégica de crecimiento para **Bodegas Finca El Roble**.

---

### <ins>4.1. Análisis de Oportunidades</ins>

* **🌱 Sostenibilidad y Ahorro (Eficiencia Energética):**
    Al monitorizar en tiempo real el consumo de las máquinas de frío y correlacionarlo con la temperatura externa e interna, se pueden optimizar los ciclos de encendido. Esto transforma un gasto fijo descontrolado en un coste gestionable, reduciendo la factura eléctrica.

* **🍷 Excelencia en el Producto (Calidad Certificada):**
    El mercado internacional exige trazabilidad. El sistema permitirá generar informes históricos que demuestren que el vino ha mantenido una temperatura estable durante toda su crianza, aumentando el valor de marca del producto final (*Premiumización*).

* **🔄 Escalabilidad de Negocio:**
    Pasar de una infraestructura física obsoleta a un **entorno virtualizado** permite a la empresa crecer de forma ágil. Si mañana necesitan un ERP o una tienda online, la infraestructura base ya estará lista para alojarlo sin comprar nuevos servidores físicos.

![Captura del entorno](./img/implementa.png)

### <ins>4.2. Estudio de Viabilidad</ins>

#### 🛠️ Viabilidad Técnica
El proyecto no requiere el desarrollo de hardware propietario ni tecnologías experimentales. Se basa en **estándares de mercado consolidados**:
* **Arquitectura:** Servidores estándar x86-64.
* **Protocolos:** Uso de protocolos abiertos y documentados (SNMP para red, MQTT para sensores, HTTPS para gestión).
* **Software:** Todas las herramientas propuestas (**Proxmox, Debian, Zabbix, PfSense**) son líderes en su sector y cuentan con amplia documentación y comunidad de soporte.

#### 💰 Viabilidad Económica
El enfoque del proyecto prioriza el **Retorno de Inversión (ROI)** mediante la reducción de costes de licenciamiento (CAPEX):
* **Modelo Open Source:** El uso de Software Libre elimina el coste recurrente de licencias (Windows Server, herramientas de monitorización de pago).
* **Hardware:** Se reutiliza y optimiza el hardware existente mediante virtualización, requiriendo una inversión mínima en sensores y electrónica de red (switches/firewall).


# 5. ⚖️ Obligaciones legales y normativas

![Legal](https://img.shields.io/badge/Legal%20%7C%20RGPD%20%7C%20Normativa--2C3E50?style=for-the-badge&logo=law)

La implementación del sistema **SMEGI** se adhiere estrictamente al marco legal vigente para garantizar la seguridad jurídica de **Bodegas Finca El Roble**.

### 5.1. Protección de Datos (RGPD y LOPDGDD)
El sistema gestiona accesos y logs de actividad de los empleados, lo que obliga al cumplimiento del **Reglamento (UE) 2016/679**.
* **Control de Acceso:** Se implementan usuarios nominales (no genéricos) para garantizar la trazabilidad.
* **Seguridad de los Datos:** Toda la información de gestión viaja cifrada mediante **VPN** y protocolos seguros (**HTTPS/SSH**).
* **Deber de Información:** Se notificará a los usuarios sobre el registro de logs de conexión por motivos de seguridad.

---

### 5.2. Propiedad Intelectual (Software)
El proyecto se basa en **Software Libre**, eliminando costes de licencias y garantizando la soberanía tecnológica.
* **Licenciamiento:** Se respetan rigurosamente las licencias **GPLv2/v3** (Linux, Zabbix) y **AGPL** (Proxmox), documentando su uso en el anexo técnico.
* **Legalidad:** No se utiliza ningún software propietario sin licencia (*crackeado*), asegurando una auditoría limpia.

---

### 5.3. Normativa de Instalaciones y PRL
La instalación física del hardware (Servidor y Rack) cumple con la normativa de seguridad industrial:
* **Seguridad Eléctrica (RBT):** Cumplimiento del Reglamento Electrotécnico para Baja Tensión (tomas de tierra y protecciones) para evitar riesgos en un entorno industrial.
* **Prevención de Riesgos (LPRL):** El equipamiento se ubicará en una zona ventilada y aislada acústicamente para cumplir con la normativa de ruido y ergonomía laboral.

![Captura del entorno](./img/legalidad.png)

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


## Enlaces a recursos de la unidad

- [Documentos de la unidad](./documentos/)
- [Imágenes](./img/)

![UD1](./img/banner2.png)


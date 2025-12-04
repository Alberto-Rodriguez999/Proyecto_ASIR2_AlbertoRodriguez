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

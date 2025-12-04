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

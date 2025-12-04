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

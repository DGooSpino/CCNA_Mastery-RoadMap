## La Nube y Servicios en la Nube
La computación en la nube se fundamenta en tres pilares esenciales: **centros de datos**, **computación en la nube** y **virtualización**. Los centros de datos son infraestructuras de gran escala que suministran la energía, refrigeración y ancho de banda requeridos. Dado el elevado costo de estas instalaciones, las organizaciones suelen arrendar estos servicios a proveedores de nube.
### Modelos de Servicios en la Nube
* **SaaS (Software como Servicio):** Aplicaciones completas accesibles a través de la red.
* **PaaS (Plataforma como Servicio):** Entornos orientados al desarrollo y despliegue de software.
* **IaaS (Infraestructura como Servicio):** Provisión de recursos básicos como procesamiento, red y almacenamiento.

### Modelos de Despliegue de Nube
* **Nubes Públicas:** Servicios abiertos a la población general a través de Internet, disponibles bajo esquemas gratuitos o de pago por uso.
* **Nubes Privadas:** Infraestructuras diseñadas para el uso exclusivo de una entidad (como empresas o gobiernos), con políticas estrictas de acceso y seguridad.
* **Nubes Híbridas:** Soluciones que integran dos o más tipos de nubes (públicas y privadas) interconectadas mediante una arquitectura común.
* **Nubes Comunitarias:** Entornos compartidos por organizaciones con requerimientos funcionales, de cumplimiento o seguridad similares (por ejemplo, el sector salud).

---
## Virtualización

La virtualización es la tecnología clave que posibilita la computación en la nube masiva, permitiendo la creación de versiones virtuales de hardware (como ejecutar Linux dentro de un sistema Windows).

### Ventajas Principales
* **Reducción de costos:**
  * **Menor equipamiento físico:** Consolidación de múltiples servidores en menos hardware.
  * **Eficiencia energética:** Disminución en el consumo eléctrico y requerimientos de climatización.
  * **Ahorro de espacio:** Optimización del espacio físico en el centro de datos.
* **Beneficios operativos:**
  * Prototipado y creación rápida de entornos de prueba aislando redes.
  * Aprovisionamiento acelerado de nuevos servidores.
  * Alta disponibilidad y tolerancia a fallas.
  * Estrategias optimizadas para la recuperación ante desastres.
  * Extensión del ciclo de vida de sistemas heredados.

### Tipos de Hipervisores
El **hipervisor** (o VMM) añade una capa de abstracción sobre el hardware físico para gestionar recursos como CPU, RAM, almacenamiento e interfaces de red entre las máquinas virtuales.

* **Hipervisor Tipo 1 (Bare-Metal / Tipo Nativo):**
  Se instala directamente sobre el hardware físico sin un sistema operativo previo. Es el estándar utilizado en servidores empresariales y centros de datos por su rendimiento y eficiencia.
* **Hipervisor Tipo 2 (Hosted / Alojado):**
  Se ejecuta como una aplicación sobre un sistema operativo anfitrión (Windows, macOS, Linux). Es ideal para entornos de desarrollo y laboratorios locales, ya que no requiere herramientas complejas de gestión dedicada.
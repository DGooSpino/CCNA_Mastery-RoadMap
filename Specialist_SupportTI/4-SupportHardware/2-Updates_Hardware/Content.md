## 1. Arquitectura del Sistema y Compatibilidad
* **Componentes Principales:** El sistema incluye CPU, placa base, RAM, almacenamiento (HDD/SSD), fuente de alimentación y GPU.
* **Interacción del Sistema:** El firmware (BIOS/UEFI) inicia el arranque y la CPU carga los datos en la RAM.
* **Tipos de Software:** El firmware controla el inicio; el sistema operativo gestiona recursos; los drivers traducen comandos; el software de aplicación ejecuta tareas específicas.
* **Compatibilidad:** Los zócalos, memorias y ranuras deben coincidir estrictamente usando listas QVL para evitar fallas.
---

## 2. Componentes de Hardware Esenciales
* **Gabinetes y Fuentes (PSU):** Convierten corriente AC a DC mediante estándares como ATX12V, EPS12V y ATX 3.0 con conectores específicos.
* **Placa Base y Chipset:** Conecta los componentes y gestiona el tráfico de datos mediante el puente norte y el puente sur.
* **CPU y Zócalos:** Intel utiliza zócalos LGA con pines en la placa, mientras que AMD utiliza PGA o sockets como AM4 y AM5.
* **Almacenamiento:** Los HDD usan platos magnéticos y RPM; los SSD emplean memoria flash mediante interfaces SATA y NVMe sobre PCIe.
---

## 3. Interfaces y Tecnologías de Expansión
* **PCI Express (PCIe):** Estándar para tarjetas gráficas y adaptadores mediante configuraciones de carriles (x1, x8, x16).
* **USB:** Soporta plug-and-play y hot-swapping, evolucionando desde USB 2.0 hasta USB4/Thunderbolt 4 con conectores Tipo-C.
* **Gráficos:** Se dividen en gráficos integrados (comparten RAM) y GPU discretas con VRAM y refrigeración propia.
* **Conectividad Inalámbrica:** Las tarjetas internas PCIe ofrecen mayor rendimiento, mientras que los adaptadores USB brindan mayor portabilidad.
---

## 4. Gestión de Controladores y Administrador de Dispositivos
* **Controladores (Drivers):** Programas traductores entre el sistema operativo y el hardware para asegurar su correcto funcionamiento.
* **Métodos de Instalación:** Incluyen Plug and Play automático, actualizaciones mediante Windows Update o instalaciones manuales.
* **Administrador de Dispositivos:** Utiliza iconos de estado y advertencia para identificar fallas de hardware.
* **Resolución de Problemas:** Permite ver detalles, buscar actualizaciones, revertir controladores o deshabilitar dispositivos.
---

## 5. Residuos Electrónicos y Eliminación Responsable
* **Peligros Ambientales:** Los componentes contienen metales pesados y sustancias tóxicas que dañan los ecosistemas si se desechan incorrectamente.
* **Seguridad de Datos:** Los dispositivos de almacenamiento retienen datos confidenciales; se requiere desinfección (NIST 800-88) o destrucción física.
* **Normativas y Reciclaje:** Existen leyes (WEEE, RCRA) y recicladores certificados bajo estándares como R2 o e-Stewards para recuperar materiales y proteger los datos.
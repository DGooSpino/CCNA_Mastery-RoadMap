# Resumen: Conceptos Básicos y Configuración de Redes Domésticas

## 1. Conceptos Básicos de Redes Domésticas
* **Estructura:** Constan de una red pública del proveedor de servicios y una red privada local (LAN). La mayoría de los enrutadores domésticos integran funciones cableadas e inalámbricas.
* **Ventajas de la LAN inalámbrica:** Ofrece movilidad, escalabilidad, flexibilidad, ahorro de costos, instalación rápida y confiabilidad en entornos hostiles.
* **Dispositivos compatibles:** Computadoras, sistemas de juegos, Smart TVs, impresoras, escáneres, cámaras de seguridad y termostatos inteligentes.
* **Puertos del enrutador:** Disponen principalmente de puertos Ethernet (cableados) y puertos de Internet, además de una antena integrada para el punto de acceso inalámbrico.

---

## 2. Tecnologías de Red en el Hogar
* **Espectro electromagnético:** Utiliza ondas para transportar información. Las frecuencias más comunes en redes domésticas son **2.4 GHz y 5 GHz** (compartidas con los estándares IEEE 802.11), mientras que Bluetooth opera también en 2.4 GHz pero a menor potencia y alcance.
* **Conectividad cableada:** El protocolo más utilizado es **Ethernet**, empleando cables de par trenzado no blindado (principalmente **Categoría 5e**, que cuenta con cuatro pares de hilos trenzados para reducir interferencias eléctricas). Si no hay cableado UTP, se pueden usar tecnologías alternativas como las líneas eléctricas.

---

## 3. Estándares Inalámbricos y Configuración del Enrutador
* **Estándar IEEE 802.11:** Rige las WLAN y es gestionado por la *Wi-Fi Alliance*.
* **Parámetros de configuración del enrutador:**
  * **Modo de red:** Define la tecnología admitida (ej. 802.11b, 802.11g, 802.11n o modo mixto).
  * **Nombre de la red (SSID):** Identifica la WLAN; todos los dispositivos deben compartir el mismo SSID para conectarse. Se recomienda **no** incluir la marca o modelo del dispositivo en el SSID para evitar exponer vulnerabilidades de seguridad.
  * **Canal estándar:** Especifica el canal de comunicación (por defecto en *Auto* para que el punto de acceso determine el óptimo).
  * **Transmisión de SSID (SSID Broadcast):** Activada por defecto para difundir el nombre de la red; si se desgrana u oculta, los dispositivos deben configurarse de forma manual.
* **Control de acceso y seguridad:**
  * **Filtrado MAC:** Permite autorizar específicamente qué dispositivos pueden conectarse a la red inalámbrica.
  * **Red de invitados:** Área de cobertura con SSID especial que provee acceso abierto limitado estrictamente a Internet.

---

## 4. Configuración Inicial del Enrutador
* **Conexión física:** Se conecta un cable Ethernet desde la computadora hacia un puerto LAN del enrutador.
* **Direccionamiento IP:** El equipo recibe una dirección IP de forma automática mediante un servidor DHCP local.
* **Buenas prácticas:** Antes de configurar la red mediante la interfaz web, es fundamental planificar el nombre del SSID de forma segura y definir las políticas de acceso.
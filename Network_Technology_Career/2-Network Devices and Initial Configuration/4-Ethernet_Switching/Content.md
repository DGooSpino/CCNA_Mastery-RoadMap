## 1. Fundamentos de Ethernet
* **Estándar de factores:** Es la tecnología predominante en redes LAN cableadas. Define la estructura de datos y su transmisión en las **Capas 1 (Física) y 2 (Enlace)** del modelo OSI.
* **Estándares IEEE:** El comité IEEE supervisa y mantiene estas tecnologías. Ethernet corresponde al estándar **IEEE 802.3**.
* **Procesamiento en el Host:** Cada tarjeta de red (NIC) evalúa la MAC de destino de las tramas que recibe. Si coincide con la suya, procesa el mensaje; de lo contrario, la descarta inmediatamente.

---

## 2. Estructura y Subcapas de la Trama
Ethernet opera bajo el modelo **IEEE 802 LAN/MAN** dividiendo la Capa 2 en dos subcapas:

1. **Subcapa LLC (IEEE 802.2):** Interconecta el software de capas superiores con el hardware inferior. Identifica el protocolo de red utilizado para que múltiples protocolos (ej. IPv4 e IPv6) compartan la misma interfaz física.
2. **Subcapa MAC (IEEE 802.3 / 802.11 / 802.15):** Implementada en hardware. Gestiona la encapsulación de datos (encabezado, direccionamiento MAC y detección de errores) y el control de acceso al medio.

### Propiedades de la Trama Ethernet
* **Ancho de banda soportado:** Desde 10 Mbps hasta 100 Gbps.
* **Modo Dúplex:** Las redes modernas usan Full-Duplex en switches, eliminando la necesidad de usar CSMA/CD.
* **Tamaño de trama:** Mínimo de **64 bytes** y máximo de **1518 bytes** (desde la MAC de destino hasta el FCS).
* **Campos principales:** Preámbulo y SFD, MAC Destino, MAC Origen, Tipo/Longitud, Datos, y FCS (Secuencia de Verificación de Trama).

---

## 3. Dirección MAC e Tipos de Transmisión
Una dirección MAC está formada por **48 bits binarios**, representados mediante **12 dígitos hexadecimales** (cada dígito equivále a 4 bits).

### Métodos de Envío de Tramas
* **Unicast:** Comunicación punto a punto entre un único emisor y un único receptor.
  * **Resolución de IP a MAC:** Usa el protocolo **ARP** en IPv4 y **Neighbor Discovery (ND)** en IPv6.
* **Broadcast (Difusión):**
  * MAC de destino: `FF-FF-FF-FF-FF-FF`.
  * El switch la reenvía por todos los puertos activos (excepto el de origen).
  * Los routers **no** reenvían tramas de broadcast.
* **Multicast (Multidifusión):**
  * MAC de destino especial: Empieza con `01-00-5E` para paquetes IPv4 o `33-33` para IPv6. (Existen direcciones específicas reservadas para STP o LLDP).
  * El switch la distribuye a todos los puertos a menos que se configure *IGMP Snooping*.
  * No atraviesa routers a menos que estén explícitamente configurados para enrutamiento multicast.

---

## 4. La Tabla de Direcciones MAC (CAM)
Los switches de Capa 2 toman decisiones de reenvío examinando únicamente las direcciones MAC de las tramas, de manera independiente a los datos del protocolo de capa superior.

### Funcionamiento del Switch
1. **Aprendizaje dinámico:** Lee la **MAC de origen** de la trama entrante y la registra en su tabla CAM asociada al puerto físico por donde ingresó.
2. **Decisión de reenvío:**
   * **Coincidencia en la tabla:** Si la MAC de destino ya está registrada, la trama se conmuta únicamente hacia ese puerto específico (filtrado).
   * **Unicast Desconocida:** Si la MAC de destino no figura en la tabla, el switch inunda la trama enviándola por todos los puertos activos excepto el puerto por donde ingresó.
3. **Múltiples MACs por puerto:** Un solo puerto de switch puede tener registradas varias direcciones MAC cuando está conectado a otro switch o concentrador.
4. **Comunicación remota:** Cuando el host de destino está en otra red, la trama Ethernet de capa 2 se dirige a la dirección MAC de la interfaz del **Gateway Predeterminado** (el router).
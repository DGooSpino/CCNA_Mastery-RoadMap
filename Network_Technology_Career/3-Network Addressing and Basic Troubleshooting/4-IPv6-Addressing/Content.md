## 1. Tipos de direcciones IPv6
* **Tipos de comunicación:** Existen tres tipos de direcciones IPv6: **Unidifusión (Unicast)**, **Multidifusión (Multicast)** y **Difusión por proximidad (Anycast)**.
* **Prefijo de red:** IPv6 no utiliza la notación decimal punteada de máscara de subred. Al igual que en IPv4, la longitud del prefijo se representa en notación de barra inclinada (`/`) e indica la porción de red de la dirección.
* **Direcciones Unidifusión (Unicast):** Identifican de forma exclusiva una interfaz en un dispositivo con IPv6 habilitado. Los dispositivos suelen tener dos direcciones unicast principales: **GUA** y **LLA**.
* **Direcciones Locales Únicas (ULA):** 
  * Se utilizan para direcciones locales dentro de un sitio o entre un número limitado de sitios.
  * Se emplean en dispositivos que no necesitan acceder a otra red y no se enrutan ni traducen globalmente a una dirección IPv6 global.
* **Direcciones de Difusión Global (GUA - Global Unicast Address):**
  * Son globalmente únicas y enrutables en Internet IPv6 (equivalentes a las IP públicas de IPv4).
  * **Estructura (3 partes):** Prefijo de enrutamiento global, ID de subred e ID de interfaz.
* **Dirección Local de Enlace (LLA - Link-Local Address):**
  * Permite que un dispositivo se comunique con otros dispositivos habilitados para IPv6 en el mismo enlace (únicamente en esa subred).
  * Se puede obtener de forma estática o dinámica.

---

## 2. Configuración estática de GUA y LLA
* **Comandos en Cisco IOS:**
  * **IPv4:** `ip address ip-address subnet-mask`
  * **GUA IPv6:** `ipv6 address ipv6-address/prefix-length`
* **Asignación estática vs. dinámica:** La configuración estática en clientes no escala bien en entornos grandes, por lo que se prefiere la asignación dinámica.
* **Configuración manual de LLA:** Se recomienda configurar manualmente la LLA en los enrutadores para crear direcciones fáciles de recordar y reconocer.
  * **Comando para LLA manual:** `ipv6 address ipv6-address link-local`

---

## 3. Direccionamiento dinámico para GUA IPv6
Los dispositivos obtienen su GUA dinámicamente mediante mensajes **ICMPv6**:

1. **Mensajes RA (Router Advertisement):** 
   * Enviados por los routers periódicamente (cada 200 segundos) a todos los dispositivos con IPv6 en la red, o en respuesta a una solicitud **RS (Router Solicitation)** de un cliente.
   * Incluyen: prefijo de red, longitud de prefijo, dirección de puerta de enlace predeterminada (LLA del router) y servidores DNS.

2. **Métodos de asignación mediante RA:**
   * **Método 1: SLAAC (Stateless Address Autoconfiguration):** El cliente usa la información del mensaje RA (prefijo e ID de interfaz) para armar su propia GUA.
   * **Método 2: SLAAC con DHCPv6 sin estado (Stateless):** El mensaje RA orienta al cliente a usar SLAAC para la IP/Gateway y consultar a un servidor DHCPv6 solo para datos adicionales (como DNS).
   * **Método 3: DHCPv6 con estado (Stateful):** El router le indica al cliente que pida toda su configuración (incluida la GUA) a un servidor DHCPv6 centralizado.

3. **Generación del ID de Interfaz (64 bits):**
   * **EUI-64:** Utiliza la dirección MAC Ethernet de 48 bits del cliente e inserta `FF:FE` (16 bits) en el medio para completar los 64 bits.
   * **Generado aleatoriamente:** Dependiendo del sistema operativo, el dispositivo puede generar un ID de interfaz aleatorio.

---

## 4. Direccionamiento dinámico para LLA de IPv6
* **Obligatoriedad:** Todos los dispositivos IPv6 deben tener una LLA.
* **Comportamiento en Cisco IOS:** 
  * Los routers Cisco crean automáticamente una LLA apenas se asigna una GUA a la interfaz.
  * Por defecto, usan **EUI-64** para generar el ID de interfaz de la LLA. En interfaces seriales, toman la dirección MAC de una interfaz Ethernet.
* **Verificación de configuración:**
  * `show ipv6 interface brief`
  * `show ipv6 route`
  * `ping`

---

## 5. Direcciones IPv6 de multidifusión (Multicast)
Existen dos tipos principales de direcciones de multidifusión en IPv6:

1. **Direcciones de multidifusión asignadas (conocidas):** Reservadas para grupos predefinidos de dispositivos.
   * `ff02::1` $\rightarrow$ Grupo de multidifusión de **todos los nodos** en el enlace.
   * `ff02::2` $\rightarrow$ Grupo de multidifusión de **todos los enrutadores** en el enlace.
2. **Direcciones de multidifusión de nodo solicitado:** Similares al grupo de todos los nodos, con la ventaja de que se asignan a una dirección especial de multidifusión en la capa Ethernet para mejorar la eficiencia del tráfico.
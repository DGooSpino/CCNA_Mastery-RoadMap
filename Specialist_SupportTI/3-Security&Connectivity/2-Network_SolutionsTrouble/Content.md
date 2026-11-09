## 1. Tipos de Redes
Documentar la red y usar iconos estandarizados (dispositivos finales, intermediarios y medios) es vital para el soporte técnico.

### Clasificación por Alcance
- **PAN (Personal):** Dispositivos de uso personal de muy corto alcance (ej. Bluetooth).
- **LAN (Local):** Conecta equipos en áreas reducidas (hogares, oficinas).
- **WLAN (Inalámbrica Local):** LAN que utiliza ondas de radio en lugar de cables.
- **WMN (Malla Inalámbrica):** Extiende la cobertura WLAN usando múltiples puntos de acceso.
- **MAN (Metropolitana):** Cobertura en un campus o ciudad entera.
- **WAN (Amplia):** Conecta redes distantes geográficamente (Internet es el mayor ejemplo).

### Medios de Red
- **Cableadas:** Usan Ethernet; ofrecen mayor velocidad, estabilidad y seguridad, pero limitan la movilidad.
- **Inalámbricas:** Brindan flexibilidad y movilidad, pero sufren interferencias o pérdida de velocidad con múltiples usuarios.
---

## 2. Redes Cableadas

- **Ethernet:** Tecnología predominante en LANs. Empaqueta datos en **tramas Ethernet** con direcciones MAC de origen y destino.
- **Tipos de Cableado:**
  - **Par trenzado (UTP):** Usa conectores RJ45. Es vulnerable a la interferencia electromagnética (EMI).
  - **Fibra óptica:** Transmite luz por un núcleo de vidrio. Inmune a EMI/RFI, soporta mayores distancias y mayor ancho de banda.
- **Problemas Comunes:** Cables dañados o que superan los 100 metros, puertos defectuosos en switches/routers e interferencia eléctrica.
---

## 3. Redes Inalámbricas

- **Frecuencias:** Operan principalmente en las bandas libres de **2.4 GHz** y **5 GHz**.
- **Estándar IEEE 802.11:** Rige la tecnología Wi-Fi (desde el estándar original de 2 Mbps hasta 802.11ax / Wi-Fi 6).
- **Componentes:** Tarjetas NIC inalámbricas, adaptadores USB y routers/puntos de acceso (AP).
- **Tipos de APs:**
  - **Autónomos:** Se configuran individualmente.
  - **Basados en Controlador (WLC):** Administración centralizada.
- **Proceso de Conexión (3 fases):** Descubrimiento de AP $\rightarrow$ Autenticación $\rightarrow$ Asociación.
---

## 4. Direccionamiento IP

### Direcciones MAC vs. IP
- **Dirección MAC:** Dirección física de 48 bits en hexadecimal, grabada en la fábrica (Capa 2).
- **Dirección IP:** Dirección lógica asignada según la ubicación en la red (Capa 3).

### Versiones de IP
| Características | IPv4 | IPv6 |
| :--- | :--- | :--- |
| **Tamaño** | 32 bits (4 octetos decimales) | 128 bits (hexadecimal) |
| **Ejemplo** | `192.168.200.8` | `2001:db8:cafe:200::8` |
| **Máscara / Prefijo** | Define red y host (ej. `/24`) | Prefijo de red asignado |
| **Tráfico** | Unicast, Broadcast y Multicast | Unicast, Multicast y Anycast (Sin Broadcast) |

### Tipos de Asignación y Rangos Privados
- **Asignación:** Estática (manual) o Dinámica (mediante DHCP).
- **Rangos Privados IPv4 (requieren NAT para salir a Internet):**
  - `10.0.0.0/8`
  - `172.16.0.0/12`
  - `192.168.0.0/16`
---

## 5. Comunicación entre Redes

- **Routers:** Interconectan redes distintas leyendo la IP de destino de los paquetes para determinar la mejor ruta.
- **Puerta de Enlace Predeterminada (Default Gateway):** Es la IP del router local que actúa como la "salida" hacia otras redes fuera de la LAN.
- **Destinos de Tráfico:** 
  1. *El propio equipo* (Loopback: `127.0.0.1` en IPv4 / `::1` en IPv6).
  2. *Equipos locales* (misma subred).
  3. *Equipos remotos* (pasan obligatoriamente por el Default Gateway).
---

## 6. Servicios DNS y DHCP

- **DNS (Domain Name System):** Traduce nombres de dominio legibles (ej. `www.cisco.com`) a direcciones IP numéricas. Utiliza caché local para optimizar las búsquedas.
- **DHCP (Dynamic Host Configuration Protocol):** Asigna configuraciones IP automáticamente.
  - **Proceso DHCP (4 pasos):** Descubrimiento (Discover) $\rightarrow$ Oferta (Offer) $\rightarrow$ Solicitud (Request) $\rightarrow$ Reconocimiento (Acknowledge).
- **Asignaciones Autogeneradas:**
  - **APIPA (IPv4):** Asigna un rango `169.254.x.x` cuando falla el servidor DHCP (sin acceso a Internet).
  - **SLAAC / LLA (IPv6):** Permite a los dispositivos generar automáticamente su dirección sin necesidad estricta de un DHCP.
---

## 7. Cortafuegos (Firewalls)

- **Función:** Controlar el tráfico filtrando el acceso entrante no autorizado y permitiendo respuestas al tráfico legítimo saliente.
- **Tipos:**
  - **De Red:** Protegen redes completas.
  - **De Host:** Programas de software instalados directamente en el equipo (ej. Windows Defender Firewall).
- **Gestión:** Permite configurar excepciones o "reglas de aplicación" para autorizar aplicaciones específicas.
---

## 8. Comandos Principales de Diagnóstico

| Comando (Windows) | Comando (Linux/Unix) | Función Principal |
| :--- | :--- | :--- |
| `ipconfig` | `ifconfig` / `ip addr` | Muestra la configuración de red (IP, Máscara, Gateway). |
| `ping` / `ping -6` | `ping` / `ping6` | Comprueba conectividad básica y latencia enviando paquetes ICMP. |
| `tracert` / `tracert -6` | `traceroute` | Muestra la ruta salto por salto hacia un destino para ubicar fallos. |
| `nslookup` | `nslookup` | Consulta servidores DNS para verificar la resolución de nombres. |
| `netstat -r` | `netstat` / `ss` | Muestra conexiones activas, puertos escuchando y tablas de enrutamiento. |
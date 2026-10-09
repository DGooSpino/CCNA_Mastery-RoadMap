## Servicios de Direccionamiento IP
En las redes de datos, las direcciones IP numéricas permiten identificar los dispositivos para el envío y recepción de información. Como las direcciones numéricas son difíciles de recordar, se diseñó el sistema de nombres de dominio (DNS), el cual asocia nombres sencillos a los recursos de red.
---
### Protocolo DNS (Domain Name System)
* **Formato de mensaje:** El protocolo DNS utiliza un formato único estándar denominado *"mensaje"* para todas las interacciones (solicitudes, respuestas, errores y transferencia de registros entre servidores).
* **Registros de recursos:** Un servidor DNS almacena registros que contienen el nombre, la dirección IP asociada y el tipo de registro correspondiente.
* **Estructura jerárquica y zonas:** 
  * Los nombres de dominio se organizan de forma jerárquica dividida en **zonas**.
  * Cada servidor administra la base de datos de su zona.
  * Si un servidor no puede resolver un nombre, reenvía la solicitud a otro servidor dentro de la zona adecuada, lo que hace que el sistema sea altamente escalable.
* **Herramienta `nslookup`:** 
  * Es una utilidad integrada en los sistemas operativos para realizar consultas manuales a los servidores DNS y diagnosticar problemas de resolución de nombres.
  * Al ejecutar el comando `nslookup`, muestra el servidor DNS predeterminado del host y permite ingresar nombres de dominio para consultar sus direcciones.

---

### Protocolo DHCP (Dynamic Host Configuration Protocol)
En redes de gran tamaño, es preferible la asignación dinámica de direcciones IPv4 e IPv6 mediante DHCP en lugar del direccionamiento estático.

#### Funcionamiento en IPv4:
1. **Período de concesión (Lease):** Las IP se asignan por un tiempo configurable.
2. **Liberación de dirección:** Si el período expira o el cliente envía un mensaje `DHCPRELEASE`, la IP regresa al estanque (pool) para ser reusada.
3. **Proceso de intercambio de mensajes:**
   * **`DHCPDISCOVER`:** El cliente transmite este mensaje para localizar servidores DHCP disponibles.
   * **`DHCPOFFER`:** El servidor responde ofreciendo una concesión de dirección IP.
   * **`DHCPREQUEST`:** El cliente solicita formalmente la oferta del servidor seleccionado.
   * **`DHCPACK` / `DHCPNAK`:** Si la IP sigue disponible, el servidor confirma el arrendamiento mediante `DHCPACK`. Si ya no está disponible, responde con `DHCPNAK` y el cliente debe reiniciar el proceso enviando otro `DHCPDISCOVER`.

#### Funcionamiento en IPv6 (DHCPv6):
* Ofrece funciones similares a IPv4, con la diferencia principal de que **no proporciona la dirección de puerta de enlace predeterminada (Gateway)**. Esta se obtiene dinámicamente mediante los mensajes *Router Advertisement* (Anuncio de Enrutador) del propio router.
* **Mensajes principales de DHCPv6:**
  * `SOLICIT`
  * `ADVERTISE`
  * `INFORMATION REQUEST`
  * `REPLY`
## 1. Unidifusión, difusión y multidifusión de IPv4
* **Unidifusión (Unicast):** 
  * Comunicación **uno a uno** entre dispositivos.
  * La IP de origen siempre es única; la de destino apunta a un único destinatario.
  * Su rango de host IPv4 abarca de `1.1.1.1` a `223.255.255.255`.

* **Difusión (Broadcast):** 
  * Comunicación **uno a todos** dentro de una red.
  * La IP de destino tiene la porción de host llena de unos (1) (ej. `255.255.255.255` en difusión limitada).
  * Es procesada por todo el dominio de difusión y, por norma general, los enrutadores no la reenvían.

* **Multidifusión (Multicast):** 
  * Envía un único paquete a un **grupo selecto de hosts suscritos**, reduciendo el tráfico de la red.
  * Utiliza el rango reservado de IPv4 de `224.0.0.0` a `239.255.255.255`. Los hosts suscritos procesan estos paquetes además de los de unidifusión.
---
## 2. Tipos de direcciones IPv4

* **Direcciones públicas:** 
  * Únicas a nivel global y enrutables por los ISP en Internet.
  * Administradas jerárquicamente por la IANA, los RIRs y los proveedores locales.

* **Direcciones privadas:** 
  * Usadas en redes internas (intranets) sin rutabilidad global; requieren **NAT** para salir a Internet.
  * *Rangos oficiales RFC 1918:* `10.0.0.0/8`, `172.16.0.0/12` y `192.168.0.0/16`.

* **Direcciones especiales:**
  * **Loopback (`127.0.0.0/8`):** Permite que un host se comunique consigo mismo (ej. `127.0.0.1`).
  * **Link-local / APIPA (`169.254.0.0/16`):** Autoconfiguración automática de IP cuando no hay un servidor DHCP disponible.

* **Clases históricas (RFC 790):**
  * **Clase A (`0.0.0.0/8` a `127.0.0.0/8`):** Redes gigantes (más de 16 millones de hosts).
  * **Clase B (`128.0.0.0/16` a `191.255.0/16`):** Redes medianas a grandes (hasta 65,000 hosts).
  * **Clase C (`192.0.0.0/24` a `223.255.255/24`):** Redes pequeñas (hasta 254 hosts).
  * **Clase D (`224.0.0.0` a `239.0.0.0`):** Exclusiva para multidifusión.
  * **Clase E (`240.0.0.0` a `255.0.0.0`):** Reservada para experimentación.

---

## 3. Segmentación de la red

* **Funcionamiento local:** 
  * Los dispositivos usan transmisiones y el protocolo **ARP** (tramas de Capa 2) para asociar IPs con direcciones MAC.
  * Los switches propagan las tramas de difusión por todas sus interfaces, excepto por la que ingresaron.

* **Dominios de difusión extensos:** 
  * Un tamaño de red excesivo con muchos hosts genera una saturación de tráfico de difusión que degrada el rendimiento.

* **Subneteo y beneficios:** 
  * Consiste en dividir la red en subredes más pequeñas usando bits de host.
  * **Ventajas:** Mitiga el tráfico innecesario, optimiza el rendimiento, mejora la seguridad (restringiendo accesos) y aísla fallos de hardware, configuración o ataques.
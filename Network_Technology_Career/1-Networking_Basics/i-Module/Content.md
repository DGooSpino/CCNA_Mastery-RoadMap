## 1. Unidifusión, difusión y multidifusión de IPv4

* **Unidifusión:** 
  * La transmisión de unidifusión se refiere a un dispositivo que envía un mensaje a otro dispositivo en comunicaciones uno a uno. 
  * Un paquete de unidifusión posee una dirección IP de destino que es una dirección de unidifusión destinada a un único destinatario. 
  * Una dirección IP de origen únicamente puede ser una dirección de unidifusión, dado que el paquete solo puede originarse en un único origen, sin importar si la IP de destino es de unidifusión, difusión o multidifusión. 
  * Las direcciones de host de unidifusión IPv4 se encuentran comprendidas en el rango de `1.1.1.1` a `223.255.255.255`.

* **Difusión (Broadcast):** 
  * Hace referencia a un dispositivo que envía un mensaje a todos los dispositivos presentes en una red a través de comunicaciones unipersonales. 
  * Los paquetes de difusión cuentan con una dirección IPv4 de destino conformada exclusivamente por números uno (1) en la porción destinada al host. 
  * Cada uno de los dispositivos que forman parte del mismo dominio de difusión procesa este tipo de paquetes. 
  * Esta transmisión puede ser de tipo dirigida o limitada; la difusión limitada se envía a `255.255.255.255`, y por regla general los enrutadores no se encargan de reenviar difusiones.

* **Multidifusión (Multicast):** 
  * Reduce el tráfico de la red al permitir que un host envíe un único paquete hacia un grupo selecto de hosts que se encuentren suscritos a un grupo de multidifusión. 
  * Un paquete de esta clase cuenta con una dirección IP de destino clasificada como dirección de multidifusión. 
  * El protocolo IPv4 reservó de manera específica el rango de `224.0.0.0` a `239.255.255.255` para operar como rango de multidifusión, donde cada grupo se representa mediante una sola dirección IP de destino. 
  * Cuando un host IPv4 se suscribe al grupo, procesa los paquetes dirigidos a esta dirección de multidifusión además de aquellos exclusivos de unidifusión.
---
## 2. Tipos de direcciones IPv4

* **Direcciones públicas:** 
  * Son aquellas en las que se efectúa un enrutamiento de manera global entre los routers pertenecientes a los ISP, requiriendo ser únicas. 
  * Son administradas por la IANA, la cual asigna bloques a los RIRs (como LACNIC, ARIN, RIPE NCC, etc.) para que estos a su vez los distribuyan entre los ISP y las organizaciones.

* **Direcciones privadas:** 
  * Bloques de direcciones empleados por organizaciones y redes domésticas con la finalidad de asignar numeración IP a los hosts internos o intranet. 
  * No poseen rutabilidad global, por lo que requieren traducir su IP de origen privada a una pública mediante NAT antes de poder reenviar paquetes hacia el exterior.
  * *Rangos oficiales RFC 1918:* `10.0.0.0/8`, `172.16.0.0/12` y `192.168.0.0/16`.

* **Direcciones especiales:**
  * **Loopback:** Identificadas comúnmente como `127.0.0.1` (dentro del rango `127.0.0.0/8`), se trata de direcciones especiales empleadas por los hosts para dirigir tráfico hacia sí mismos.
  * **Link-local (APIPA):** Comprendidas en el rango `169.254.0.0/16` (de `169.254.0.1` a `169.254.255.254`), son utilizadas de forma automática por un cliente DHCP con el propósito de autoconfigurarse ante la ausencia de servidores DHCP disponibles.

* **Clases históricas (RFC 790):**
  * **Clase A (`0.0.0.0/8` a `127.0.0.0/8`):** Creadas para dar soporte a redes de dimensiones sumamente extensas, albergando más de 16 millones de direcciones de host.
  * **Clase B (`128.0.0.0/16` a `191.255.0/16`):** Ideadas para suplir las necesidades de redes de escala moderada a grande, soportando hasta 65,000 direcciones de host.
  * **Clase C (`192.0.0.0/24` a `223.255.255/24`):** Diseñadas para admitir redes de menor tamaño con un límite máximo de 254 hosts.
  * **Clase D (`224.0.0.0` a `239.0.0.0`):** Bloque asignado específicamente para la multidifusión.
  * **Clase E (`240.0.0.0` a `255.0.0.0`):** Bloque reservado para fines experimentales.
---
## 3. Segmentación de la red

* **Funcionamiento local:** 
  * Dentro de una red de área local Ethernet, los dispositivos recurren a transmisiones y al protocolo ARP para localizar otros equipos. 
  * ARP emite tramas de capa 2 dirigidas a una dirección IPv4 conocida con el objetivo de descubrir la dirección MAC vinculada. 
  * De igual manera, los hosts obtienen su configuración inicial mediante DHCP y los switches se encargan de propagar el tráfico de difusión a través de todas sus interfaces exceptuando aquella por la cual ingresó el mensaje.

* **Dominios de difusión extensos:** 
  * Un dominio de difusión de gran tamaño conecta a una alta cantidad de hosts, lo que puede provocar un volumen excesivo de tráfico de difusión y perjudicar el rendimiento general de la infraestructura.

* **Subneteo y beneficios:** 
  * La solución consiste en disminuir las dimensiones de la red por medio de la división en subredes utilizando bits de host. 
  * Este procedimiento ayuda a mitigar el tráfico general, incrementar el rendimiento, optimizar la implementación de políticas de seguridad para restringir comunicación entre subredes y disminuir el impacto de fallos de configuración, problemas de hardware o acciones maliciosas.
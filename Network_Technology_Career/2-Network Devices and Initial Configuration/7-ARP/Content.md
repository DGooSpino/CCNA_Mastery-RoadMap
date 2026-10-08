# Protocolo ARP (Address Resolution Protocol)
Para enviar un paquete a otro host en la misma red IPv4 local, un host debe conocer la dirección IPv4 y la dirección MAC del dispositivo de destino. Las direcciones IPv4 de destino se conocen o se resuelven por el nombre del dispositivo. Sin embargo, las direcciones MAC deben ser descubiertas. 

Un dispositivo utiliza **ARP** para determinar la dirección MAC de destino de un dispositivo local cuando conoce su dirección IPv4. ARP proporciona dos funciones básicas:
1. Resolver direcciones IPv4 a direcciones MAC.
2. Mantener una tabla de asignaciones de direcciones IPv4 a MAC.
---
## Búsqueda en la Tabla ARP
El dispositivo emisor busca en su tabla ARP la dirección IPv4 de destino y la dirección MAC correspondiente:

* **Misma red:** Si la dirección IPv4 de destino del paquete está en la misma red que la dirección IPv4 de origen, el dispositivo busca la dirección IPv4 de destino en la tabla ARP.
* **Red diferente:** Si la dirección IPv4 de destino está en una red diferente a la dirección IPv4 de origen, el dispositivo busca la dirección IPv4 del *gateway* predeterminado.
En cada entrada o fila de la tabla ARP, se enlaza una dirección IPv4 con una dirección MAC (denominada asignación).
--
## Encapsulamiento y Solicitud ARP
Los mensajes de ARP se encapsulan directamente dentro de una trama de Ethernet (no se utiliza un encabezado de IPv4). La solicitud de ARP incluye la siguiente información de encabezado:

* **Dirección MAC de destino:** Es una dirección de *broadcast* que requiere que todas las NIC Ethernet de la LAN acepten y procesen la solicitud de ARP.
* **Dirección MAC de origen:** Dirección MAC del remitente de la solicitud ARP.
* **Tipo:** Los mensajes de ARP tienen un campo de tipo `0x806`. Esto informa a la NIC receptora que la porción de datos de la trama se debe enviar al proceso ARP.

> Como las solicitudes de ARP son de *broadcast*, el switch las envía por todos los puertos, excepto el de recepción. Sólo el dispositivo con la dirección IPv4 de destino asociada responderá con una respuesta ARP. Una vez recibida la respuesta, el dispositivo agrega la dirección IPv4 y la dirección MAC correspondiente a su tabla ARP.

---

## Comunicación fuera de la Red Local
Cuando la dirección IPv4 de destino no está en la misma red que la de origen, el dispositivo debe enviar la trama al *gateway* predeterminado (interfaz del router local). 

* El host encapsula el paquete en una trama con la dirección MAC de destino del router.
* La dirección IPv4 de la puerta de enlace predeterminada se almacena en la configuración IPv4 del host.
* Si el host no encuentra la dirección MAC del *gateway* en su tabla ARP, utiliza el proceso ARP para determinarla.

---
## Mantenimiento y Comandos de la Tabla ARP

Un temporizador de memoria caché ARP elimina las entradas que no se hayan utilizado durante un período especificado (varía según el sistema operativo).

### Comandos útiles:
* **Router Cisco:** `show ip arp` (para visualizar la tabla ARP).
* **Windows 10:** `arp -a` (para visualizar la tabla ARP).

---
## Consideraciones de Rendimiento y Seguridad

* **Impacto en red:** Todos los dispositivos procesan una solicitud ARP por ser una trama de difusión. Si se encienden muchos dispositivos simultáneamente, el rendimiento puede disminuir brevemente.
* **Suplantación ARP (ARP Spoofing / Envenenamiento ARP):** Es una técnica donde un atacante responde a una solicitud ARP enviando su propia dirección MAC asociada a la IP de otro dispositivo (como el *gateway* predeterminado). De esta manera, el receptor agrega la MAC incorrecta a su tabla ARP y redirige el tráfico al atacante.
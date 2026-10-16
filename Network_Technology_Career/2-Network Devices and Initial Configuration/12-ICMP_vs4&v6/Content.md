## Mensajes ICMP

* El protocolo ICMP proporciona mensajes de error e informativos para la comunicación de paquetes IP tanto en IPv4 (ICMPv4) como en IPv6 (ICMPv6).
* Los mensajes de eco (solicitud y respuesta de eco) sirven para probar la accesibilidad de un host en una red IP.
* Cuando no se puede entregar un paquete, se envía un mensaje de destino inalcanzable indicando mediante un código la razón del fallo.
* Los mensajes de Tiempo Superado de ICMPv4 se envían al host de origen cuando el campo de Tiempo de Duración (TTL) se reduce a cero en un router y el paquete es descartado. ICMPv6 ofrece una funcionalidad similar cuando el paquete caduca.
* ICMPv6 incluye cuatro nuevos protocolos dentro del Descubrimiento de Vecinos (ND/NDP):
  * Mensaje de RS (Solicitud de Router)
  * Mensaje de RA (Anuncio de Router)
  * Mensaje de NS (Solicitud de Vecino)
  * Mensaje de NA (Anuncio de Vecino)


## Pruebas de Ping y Traceroute

* El comando **ping** envía solicitudes de eco a una dirección IP para comprobar la conectividad y medir el tiempo transcurrido entre el envío y la respuesta.
* Se realizan tres tipos principales de pruebas de conectividad mediante ping:
  * **Ping a loopback local:** Prueba la configuración interna del protocolo IP en el host.
  * **Ping a la puerta de enlace predeterminada:** Confirma que la interfaz del enrutador local y el host están operativos en la red local.
  * **Ping al host remoto:** Verifica la comunicación local, la puerta de enlace y la ruta de routers hacia el destino remoto.
* La utilidad **traceroute** (`tracert`) muestra la lista de saltos (routers) a lo largo de una ruta para la solución de problemas.
* Permite identificar en qué salto se genera un problema o restricción de seguridad analizando la última dirección que respondió.
* Mide el tiempo de ida y vuelta (RTT) y utiliza un asterisco (*) para indicar un paquete perdido o no respondido.
* Funciona manipulando el campo TTL en IPv4 (o Límite de Salto en IPv6) junto con los mensajes de ICMP Tiempo Excedido.

# 15.3.1 ¿Qué aprendí en este módulo?

## TCP y UDP

* **UDP (User Datagram Protocol):**
  * Funciona como un sistema de entrega de "mejor esfuerzo" que no requiere confirmación de recepción.
  * Es el protocolo recomendado para aplicaciones como transmisiones de audio y voz por IP (VoIP).
  * Las confirmaciones de recepción reducirían la velocidad de la entrega, y las retransmisiones no son recomendadas.
  * Los paquetes toman una ruta desde el origen hasta el destino y es posible que se pierdan algunos paquetes, aunque generalmente no se nota.

* **TCP (Transmission Control Protocol):**
  * Los paquetes TCP toman una ruta desde el origen hasta el destino, pero cada uno de ellos cuenta con un número de secuencia.
  * Divide el mensaje en partes pequeñas conocidas como segmentos, los cuales se numeran en secuencia y se pasan al proceso IP para armarse en paquetes.
  * Realiza un seguimiento del número de segmentos enviados a un host específico desde una aplicación específica.
  * Si el remitente no recibe una confirmación antes de transcurrido cierto tiempo, asume que los segmentos se perdieron y los retransmite.
  * Solo se vuelve a enviar la parte del mensaje que se perdió, no el mensaje completo.

---

## Números de Puerto

* **Concepto general:**
  * Al enviar un mensaje usando TCP o UDP, los protocolos y servicios solicitados se identifican con un número de puerto.
  * Es un identificador numérico dentro de cada segmento que se usa para llevar un seguimiento de las conversaciones específicas entre un cliente y un servidor. Cada mensaje enviado contiene un puerto de origen y un puerto de destino.
  * Cuando un servidor recibe un mensaje, debe poder determinar qué servicio está solicitando el cliente. Los clientes se preconfiguran para usar un puerto de destino registrado en Internet para cada servicio.
  * Son asignados y administrados por la organización ICANN y se dividen en tres categorías que van del 1 al 65535:

* **Categorías de puertos:**
  * **Puertos Conocidos:** Asociados con aplicaciones de red comunes, se encuentran en el rango del 1 al 1023.
  * **Puertos Registrados:** Van del 1024 al 49151; se usan como puertos de origen o destino y las organizaciones los registran para aplicaciones específicas como las de mensajería instantánea (IM).
  * **Puertos Privados:** Van del 49152 al 65535; son usados con frecuencia como puertos de origen y pueden ser utilizados por cualquier aplicación.

* **Dinámica de los puertos:**
  * **Puerto de origen:** Generado de manera dinámica por el dispositivo emisor para identificar una conversación entre dos dispositivos, permitiendo establecer varias conversaciones simultáneamente (por ejemplo, enviar varias solicitudes de servicio HTTP a un servidor web al mismo tiempo).
  * **Puerto de destino:** Colocado por el cliente en el segmento para informar al servidor el servicio solicitado. Un servidor puede ofrecer múltiples servicios simultáneamente (por ejemplo, servicios web en el puerto 80 y FTP en el puerto 21).

* **Monitoreo y Seguridad (Netstat):**
  * Las conexiones TCP no identificadas pueden representar una amenaza a la seguridad o indicar accesos no autorizados al host local.
  * A veces es necesario conocer las conexiones TCP activas abiertas y en ejecución en el host de red.
  * **Netstat** es una utilidad de red importante que se usa para enumerar los protocolos en uso, la dirección local, los números de puerto, la dirección extranjera y el estado de la conexión.
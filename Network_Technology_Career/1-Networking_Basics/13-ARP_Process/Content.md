A veces un host debe enviar un mensaje conociendo solo la dirección IP de destino, por lo que necesita averiguar su dirección MAC mediante resolución de direcciones. En una LAN Ethernet existen dos direcciones principales:

* **Dirección física (la dirección MAC):** Se utiliza para comunicaciones de NIC a NIC dentro de la misma red Ethernet.
* **Dirección lógica (la dirección IP):** Se usa para enviar el paquete desde el origen hasta el destino, ya sea en la misma red o en una remota.

Si la IP de destino se encuentra en una red remota, la MAC de destino será la de la puerta de enlace predeterminada (la interfaz del router). Los routers analizan la IP de destino para hallar la mejor ruta. Al recibir una trama de Ethernet, desencapsulan la capa 2, identifican el siguiente salto mediante la dirección IP y vuelven a encapsular el paquete IP en una nueva trama adaptada al tipo de enlace. Si el siguiente salto es el destino final, la MAC de destino corresponde a la NIC Ethernet de dicho dispositivo.

# Contención de Difusiones

Un mensaje solo puede tener una dirección MAC de destino, permitiendo que un host envíe un mensaje de difusión hacia una dirección única reconocida por todos los equipos. La dirección MAC de transmisión de 48 bits se representa en hexadecimal como `FFFF.FFFF.FFFF`.

* **Dominio de difusión:** Red local donde los conmutadores reenvían los mensajes de difusión a cada equipo conectado.
* **Uso de enrutadores:** Se emplean para dividir una red local grande y limitar los dominios de difusión con el fin de mejorar el rendimiento y evitar tráfico excesivo.

En una red Ethernet local, una NIC acepta una trama únicamente si el destino es la dirección MAC de difusión o su propia dirección física. Dado que las aplicaciones emplean la IP de destino para ubicar servidores y clientes, el emisor utiliza el protocolo ARP para descubrir la MAC en la red local mediante un proceso de tres pasos:

1. **Solicitud de ARP:** El emisor crea y envía una trama dirigida a la MAC de difusión que incluye la dirección IPv4 que desea localizar.
2. **Respuesta de ARP:** Todos los equipos reciben la trama y comparan la IP; aquel cuya dirección coincide envía su propia dirección MAC como respuesta directa al emisor original.
3. **Tabla ARP:** El emisor recibe el mensaje y almacena la relación entre la dirección MAC y la dirección IPv4 en una tabla interna.

*Nota:* Para IPv6 se utiliza un mecanismo equivalente conocido como Detección de Vecinos.
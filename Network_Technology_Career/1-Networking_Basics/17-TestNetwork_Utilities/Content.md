## Comandos de solución de problemas

Hay disponibles varios programas de utilidad de software que pueden ayudar a identificar problemas de red. El sistema operativo proporciona la mayoría de estas utilidades como comandos CLI.

Éstas son algunas de las utilidades disponibles:

* **ipconfig** - Muestra información de la configuración IP
* **ping** - Prueba las conexiones con otros hosts IP
* **netstat** - Muestra las conexiones de red
* **tracert** - Muestra la ruta exacta recorrida hasta el destino
* **nslookup** - Directamente solicita al servidor de nombres información sobre un dominio de destino

El comando `ipconfig` se utiliza para ver información sobre la configuración IP actual de un host. Al ejecutar este comando desde la línea de comandos se muestra la información de configuración básica que incluye: dirección IP, máscara de subred y gateway predeterminado.

El comando `ipconfig /all` muestra información adicional, que incluye la dirección MAC y las direcciones IP de la puerta de enlace predeterminada y los servidores DNS. También indica si DHCP está activado, la dirección del servidor DHCP y la información de arrendamiento.

Si la información de direccionamiento IP se asigna dinámicamente, el comando `ipconfig /release` liberará los enlaces DHCP actuales. `ipconfig /renew` solicitará información de configuración actualizada del servidor DHCP. Un host puede contener información de configuración IP defectuosa o desactualizada; para volver a adquirir conectividad solo se requiere una simple renovación de esta información.

Probablemente la utilidad de red más usada sea **ping**. La mayoría de los dispositivos habilitados para IP admiten algún tipo de comando `ping` para probar si los dispositivos de red son accesibles o no a través de la red IP. Al enviar un comando `ping` a una dirección IP, se envía un paquete conocido como *solicitud de eco* a través de la red a la dirección IP especificada. Si recibe la solicitud de eco, el host de destino responde con un paquete denominado *respuesta de eco*. Si la fuente recibe la respuesta de eco, la respuesta de la dirección IP específica verifica la conectividad.
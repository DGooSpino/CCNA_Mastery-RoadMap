## Configuración Básica del Conmutador

* Los elementos para configurar en un conmutador LAN incluyen el nombre del host, la dirección IP de administración, las contraseñas y la información descriptiva.
* Una dirección de administración permite acceder al dispositivo mediante Telnet, SSH o clientes HTTP.
* La información IP que se debe configurar en un conmutador incluye la dirección IP, la máscara de subred y la puerta de enlace predeterminada.
* Para proteger un conmutador LAN, configure contraseñas en los distintos métodos de acceso a la línea de comandos, incluyendo el acceso remoto (Telnet, SSH, consola) y el modo privilegiado.
* Para el acceso remoto al conmutador, configure una dirección IP y una máscara de subred en el SVI mediante el comando global **interface vlan 1**, asigne la dirección IPv4 con **ip address dirección-ip máscara-de-subred** y active la interfaz con **no shutdown**.


## Configuración de los Ajustes Iniciales del Enrutador

* **Paso 1:** Configure el nombre del dispositivo.
* **Paso 2:** Proteja el modo EXEC con privilegios mediante una contraseña segura.
* **Paso 3:** Proteja el modo EXEC de usuario.
* **Paso 4:** Proteja el acceso remoto por Telnet o SSH.
* **Paso 5:** Proteja todas las contraseñas del archivo de configuración.
* **Paso 6:** Proporcione una notificación legal que advierta el acceso autorizado.
* **Paso 7:** Guarde la configuración para evitar pérdidas ante cortes de energía.


## Seguridad y Protección de Dispositivos

* Utilice contraseñas seguras que combinen caracteres alfanuméricos, símbolos, espacios o frases de contraseña compuestas por varias palabras.
* La contraseña de la consola se configura en el modo de configuración global para evitar accesos no autorizados directos desde el puerto físico.
* Las conexiones de red remotas utilizan las líneas vty. Se configuran por lo general 5 líneas (numeradas del 0 al 4) y es necesario establecer una contraseña en todas ellas.
* El comando **show running-config** permite verificar las contraseñas, las cuales se muestran inicialmente en texto sin cifrar.
* El comando global **service password-encryption** cifra de forma automática todas las contraseñas almacenadas en el dispositivo.


## Habilitación de SSH

* **Paso 1:** Verificar la compatibilidad con SSH usando **show ip ssh**.
* **Paso 2:** Configurar el dominio IP con **ip domain-name nombre-de-dominio**.
* **Paso 3:** Generar los pares de claves RSA con **crypto key generate rsa**.
* **Paso 4:** Configurar la autenticación de usuario con **username nombre-de-usuario secret contraseña**.
* **Paso 5:** Configurar las líneas vty.
* **Paso 6:** Habilitar la versión 2 de SSH con **ip ssh versión 2**.
* Use el comando **show ssh** para verificar las conexiones activas al servidor SSH.


## Configuración del Gateway Predeterminado

* La puerta de enlace predeterminada se utiliza únicamente cuando un host desea enviar un paquete a un dispositivo situado en una red diferente.
* Generalmente, la dirección del gateway es la interfaz del enrutador conectada a la red local del host, debiendo estar ambas en la misma red.
* Para administrar de forma remota un conmutador desde otra red mediante un SVI configurado, se debe establecer la puerta de enlace predeterminada globalmente con el comando **ip default-gateway dirección-ip**, usando la dirección IP de la interfaz local del router.
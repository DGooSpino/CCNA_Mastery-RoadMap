## Cómo enruta un host
Un host puede enviar un paquete a:
* **Sí mismo**
* **Otro host local**
* **Un host remoto**

### Determinación de destino:
* **IPv4:** El dispositivo de origen utiliza su propia máscara de subred junto con su propia dirección IPv4 y la dirección IPv4 de destino para determinar si el host de destino está en la misma red.
* **IPv6:** El enrutador local anuncia la dirección de red local (prefijo) a todos los dispositivos de la red para realizar esta determinación.

### Puerta de enlace predeterminada (*Default Gateway*):
Es el dispositivo de red (es decir, el enrutador) que puede enrutar el tráfico a otras redes.
* En una red, una puerta de enlace predeterminada suele ser un enrutador que tiene una dirección IP local en el mismo rango de direcciones que otros hosts de la red local.
* Puede aceptar datos en la red local y reenviar datos fuera de la red local, enrutando el tráfico a otras redes.
* Una tabla de enrutamiento de host generalmente incluirá una puerta de enlace predeterminada.

### Asignación de IP de la puerta de enlace:
* **IPv4:** El host recibe la dirección IPv4 de la puerta de enlace predeterminada de forma dinámica a través de **DHCP** o se configura manualmente.
* **IPv6:** El enrutador anuncia la dirección de la puerta de enlace predeterminada o el host se puede configurar manualmente.

> 💡 **Comando de verificación en Windows:**
> En un host de Windows, se puede usar el comando `route print` o `netstat -r` para mostrar la tabla de enrutamiento del host.

---
## Tablas de enrutamiento
Cuando un host envía un paquete a otro host, consulta su tabla de enrutamiento para determinar dónde enviar el paquete. Si el host de destino está en una red remota, el paquete se reenvía a la puerta de enlace predeterminada, que generalmente es el enrutador local.

### Procesamiento de un paquete en la interfaz del enrutador:
1. El enrutador examina la dirección IP de destino del paquete.
2. Busca en su tabla de enrutamiento para determinar dónde reenviar el paquete.
3. La tabla de enrutamiento contiene una lista de todas las direcciones de red conocidas (prefijos) y a dónde reenviar el paquete. Estos enlaces se conocen como **enlaces de ruta o rutas**.
4. El enrutador reenviará el paquete utilizando la mejor coincidencia de enlace de ruta (la coincidencia de prefijo más larga).
--

### Tipos de enlaces de ruta en una tabla de enrutamiento:
La tabla de enrutamiento de un enrutador almacena tres tipos de enlaces de ruta:
1. **Redes conectadas directamente**
2. **Redes remotas:** Aprendidas de forma manual o dinámica utilizando un protocolo de enrutamiento dinámico (como **OSPF** o **EIGRP**).
3. **Ruta predeterminada (*Default Route*)**

* **Rutas estáticas:** Son enlaces de ruta que se configuran manualmente. Incluyen la dirección de red remota y la dirección IP del enrutador de salto siguiente (*next-hop*).

 **Comando de verificación en Cisco IOS:**
> En modo EXEC privilegiado, el comando `show ip route` se utiliza para ver la tabla de enrutamiento IPv4 en el IOS de un enrutador Cisco.

---

### Códigos comunes de la tabla de enrutamiento IPv4:
Al principio de una tabla de enrutamiento IPv4 hay un código que identifica cómo se aprendió la ruta:

* `L` - Dirección IP de la interfaz local conectada directamente.
* `C` - Red directamente conectada.
* `S` - La ruta estática fue configurada manualmente por un administrador.
* `O` - Open Shortest Path First (**OSPF**).
* `D` - Enhanced Interior Gateway Routing Protocol (**EIGRP**).
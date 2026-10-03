## 1. La Necesidad del Enrutamiento
A medida que las redes crecen, es necesario dividirlas en subredes para mantener la eficiencia mediante los siguientes criterios:
* **Contención de difusión:** Los enrutadores limitan el envío masivo de difusiones a la red local.
* **Requerimientos de seguridad:** Permiten segmentar y aislar grupos de computadoras con información confidencial.
* **Ubicaciones físicas:** Interconectan redes locales separadas geográficamente.
* **Agrupación lógica:** Agrupan usuarios o departamentos con necesidades operativas comunes.

Un **enrutador** es un dispositivo de Capa 3 que interconecta redes IP independientes. A diferencia de los switches (que operan en Capa 2 usando direcciones MAC), los enrutadores toman decisiones de reenvío basándose en la **dirección IP de Capa 3** cuando las porciones de red de origen y destino no coinciden.

---

## 2. La Tabla de Enrutamiento y su Funcionamiento
Cada puerto de un enrutador se conecta a una red diferente y mantiene una tabla con las rutas conocidas.

* **Proceso de enrutamiento:** El router recibe una trama, la decodifica para obtener el paquete IP de destino, lo busca en su tabla de enrutamiento y lo encapsula en una nueva trama para enviarlo.
* **Direccionamiento MAC y ARP:** Para el reenvío entre dispositivos de Capa 2, utiliza la dirección MAC de destino o la de un router vecino obtenida mediante las **tablas ARP**.
* **Puerta de enlace predeterminada:** Es la IP de la interfaz del router en la red local que los equipos utilizan para enviar mensajes hacia redes remotas.
* **Entradas en la tabla:** Las rutas se pueden agregar mediante **actualización dinámica** con protocolos de enrutamiento o de forma **manual** por el administrador.

---

## 3. Arquitectura y Creación de una Red LAN
Una **LAN** es un conjunto de redes locales bajo un mismo control administrativo que usan protocolos Ethernet o inalámbricos de alta velocidad.

* **Red local única:** Los hosts se ven directamente porque comparten un dominio de difusión y usan ARP.
* **Redes segmentadas o remotas:** Reducen el tráfico y la congestión, pero requieren obligatoriamente **enrutamiento** para que los equipos se comuniquen entre diferentes subredes. Esto incrementa la complejidad de configuración y puede generar una leve latencia.
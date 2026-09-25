## 1. Propósito de la Dirección IPv4
* **Definición:** Es una dirección de red lógica de 32 bits que identifica de forma única a un host (dispositivo) en particular.
* **Funciones principales:**
  * **Comunicación Local:** Debe configurarse correctamente para ser única dentro de la red LAN.
  * **Comunicación Remota:** Debe configurarse correctamente para ser única a nivel global en Internet.
* **Asignación:** Se asigna a la interfaz de red del host (comúnmente una tarjeta NIC).
* **Paquetes:** Todo paquete enviado por Internet lleva una **dirección IP de origen** y una **dirección IP de destino** para asegurar la entrega y la devolución de las respuestas.

---

## 2. Estructura de la Dirección IPv4 y Direccionamiento Jerárquico
* **Composición:** Tiene una estructura jerárquica dividida en dos partes:
  1. **Porción de Red:** Identifica la red a la que pertenece el dispositivo.
  2. **Porción de Host:** Identifica al dispositivo individual dentro de esa red.
* **Ejemplo práctico:** 
  * Dirección IP: `192.168.5.11`
  * Máscara de subred: `255.255.255.0`
  * **Porción de red:** `192.168.5` (primeros tres octetos)
  * **Porción de host:** `11` (último octeto)
* **Ventaja para los enrutadores (Routers):** Los routers solo necesitan saber cómo llegar a cada *red* en lugar de memorizar la ubicación de cada *host* individual, optimizando el tráfico de la red.

---

## 3. Funcionamiento de la Máscara de Subred y Tipos de Redes
La máscara de subred actúa como un filtro que separa la parte de red de la parte de host:

* **¿Cómo se calcula?** Mediante una operación lógica AND entre la dirección IP y la máscara de subred.
* **Clases principales de máscaras:**
  * **Clase C (`255.255.255.0` / `/24`):** Los primeros 3 octetos son red y el último es para hosts (**254 hosts utilizables**). Típica para redes pequeñas o domésticas.
  * **Clase B (`255.255.0.0` / `/16`):** Los primeros 2 octetos son red y los últimos 2 para hosts (**65,534 hosts utilizables**). Típica para oficinas medianas.
  * **Clase A (`255.0.0.0` / `/8`):** El primer octeto es red y los 3 restantes para hosts (**~16.7 millones de hosts utilizables**). Típica para grandes corporaciones o ISPs.
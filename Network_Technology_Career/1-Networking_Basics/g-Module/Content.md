## 1. Encapsulación y la Trama de Ethernet

El proceso que consiste en colocar un mensaje dentro de otro formato de mensaje se denomina **encapsulamiento**. Cuando el destinatario revierte este proceso y quita la carta del sobre se produce la **desencapsulación** del mensaje. De la misma manera en que una carta se encapsula en un sobre para la entrega, los mensajes de las computadoras también deben encapsularse bajo reglas de formato específicas para que puedan ser entregados y procesados.

Los estándares del protocolo **Ethernet** definen la comunicación en red local (LAN) especificando el formato, tamaño, temporización y codificación de las tramas. Su estructura incluye:
* **Preámbulo:** 7 bytes para sincronización de reloj.
* **SFD (Start Frame Delimiter):** 1 byte que marca el inicio exacto de la trama.
* **Direcciones MAC de Origen y Destino:** Identificadores físicos de Capa 2.
* **Tipo / Longitud:** Define el protocolo de capa superior encapsulado.
* **FCS (Frame Check Sequence):** Secuencia de verificación para detectar errores de transmisión.

---

## 2. La Capa de Enlace de Datos y el Direccionamiento MAC

La Capa de Enlace de Datos (Capa 2 del modelo OSI) opera localmente mediante **direcciones MAC** (Físicas/Ethernet), a diferencia de la Capa 3 (IP), que se encarga del direccionamiento global o WAN.

* **Descubrimiento mediante Broadcast:** Cuando un host conoce la dirección IP de destino en la misma LAN pero desconoce su dirección MAC, utiliza un mensaje de difusión (*Broadcast* con dirección MAC `FF:FF:FF:FF:FF:FF`, como el protocolo **ARP**) para consultar quién posee dicha IP.
* **Ejemplos prácticos:** Impresoras de red en oficinas y sensores IoT en corporaciones/bancos que se comunican de forma local mediante tramas Ethernet antes de enrutar datos hacia el exterior.

---

## 3. Dispositivos de Red: Conmutadores (*Switches*) vs. Concentradores (*Hubs*)

### Concentradores (Hubs) - Obsoletos (Capa 1)
* Repiten la señal de forma indiscriminada por todos los puertos.
* Generan un medio compartido con frecuentes **colisiones de datos** y baja seguridad.
* Actualmente se consideran **obsoletos** y fueron totalmente reemplazados por los switches.

### Conmutadores (Switches) - Capa 2
* **Decisión de reenvío:** Utilizan la **dirección MAC de destino** para determinar por qué puerto específico enviar la trama de manera directa (unicast).
* **Manejo de destinos desconocidos (*Flooding*):** Si la MAC de destino no se encuentra registrada en la tabla interna del switch, este reenvía la trama por **todos los puertos excepto el puerto entrante**.
* **Aprendizaje dinámico:** El switch inspecciona la **dirección MAC de origen** de cada trama entrante para asociarla al puerto físico correspondiente y actualizar de forma dinámica su **tabla de direcciones MAC**.
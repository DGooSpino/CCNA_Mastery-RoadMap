
## 1. Direccionamiento Estático vs. Dinámico

La configuración de red de un host puede realizarse de dos formas principales:

### ⚙️ Asignación Estática
* **Definición:** El administrador de red configura manualmente los parámetros en cada dispositivo.
* **Parámetros mínimos requeridos:** Dirección IP, máscara de subred y puerta de enlace predeterminada.
* **Ventajas:** Proporciona un control absoluto y directo de los recursos de la red.
* **Desventajas:** Es un proceso lento, propenso a errores humanos y requiere llevar un registro estricto y preciso de qué IP se asigna a cada equipo.

### 🔄 Asignación Dinámica (DHCP)
* **Definición:** Las direcciones se asignan de forma automatizada mediante un servidor utilizando el protocolo **DHCP** (*Dynamic Host Configuration Protocol*).
* **Ventajas principales:** 
  * Reduce la carga operativa del personal de soporte técnico.
  * Elimina casi por completo los errores de configuración manual.
  * **Arrendamiento (*Lease*):** Las IPs no son permanentes; se prestan por un periodo de tiempo. Si un dispositivo se desconecta, la dirección regresa al *pool* (conjunto) para ser reutilizada por otro host.

---

## 2. Funcionamiento y Proceso de DHCPv4

El servidor DHCP gestiona un rango (*pool*) de direcciones IPv4 para entregarlas a los clientes que las soliciten mediante el proceso de intercambio de mensajes conocido como **DORA** (*Discover, Offer, Request, Acknowledge*):

1. **Descubrimiento DHCP (*DHCP Discover*):**
   * El cliente necesita una IP y envía un mensaje de difusión (*broadcast*).
   * **IP de destino:** `255.255.255.255` (32 unos).
   * **MAC de destino:** `FF-FF-FF-FF-FF-FF` (48 unos).
   * Todos los hosts de la red reciben la trama, pero solo el servidor DHCP responde.

2. **Oferta DHCP (*DHCP Offer*):**
   * El servidor responde ofreciendo una dirección IPv4 disponible para el cliente.

3. **Solicitud DHCP (*DHCP Request*):**
   * El host acepta la propuesta y solicita formalmente autorización para utilizar la dirección sugerida.

4. **Confirmación / Acuse de recibo (*DHCP ACK*):**
   * El servidor confirma la asignación y el cliente ya puede utilizar la IP de manera oficial en la red.

---

## 3. DHCP en Redes Domésticas y Pequeñas

* **El rol del Router Inalámbrico:** En hogares y PyMEs, el enrutador inalámbrico actúa simultáneamente como cliente DHCP (hacia el proveedor de internet - ISP) y como **servidor DHCP** (hacia los dispositivos de la red local).
* **Valores Predeterminados Comunes:** 
  * Por lo general, la interfaz interna del router viene configurada con la dirección IP `192.168.0.1` y la máscara de subred `255.255.255.0`.
  * Esta IP interna funciona como la **puerta de enlace predeterminada** para todos los equipos conectados a la red local.
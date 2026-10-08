## 1. Características de la capa de red
La **capa de red (Capa 3 del modelo OSI)** permite que los dispositivos finales intercambien datos a través de diferentes redes.

### Protocolos principales

- **IPv4 e IPv6:** principales protocolos de comunicación de la capa de red.
- **OSPF:** protocolo de enrutamiento.
- **ICMP:** protocolo de mensajería y diagnóstico.

### Funciones de la capa de red
Los protocolos de la capa de red realizan cuatro operaciones principales:

1. **Direccionamiento:** identifica los dispositivos de origen y destino.
2. **Encapsulación:** agrega un encabezado IP a los datos.
3. **Enrutamiento:** determina el camino que seguirá el paquete.
4. **Desencapsulación:** permite procesar los datos al llegar al destino.

### Características de IP

IP permite transportar datos desde un host de origen hasta un host de destino mediante paquetes.
El encabezado IP es examinado por los **routers y switches de Capa 3** durante el recorrido del paquete.
La dirección IP normalmente permanece igual desde el origen hasta el destino, excepto cuando es modificada mediante **NAT en IPv4**.

IP tiene tres características principales:

- **Sin conexión:** no establece una conexión dedicada antes de enviar los datos.
- **Mejor esfuerzo:** no garantiza que el paquete llegue correctamente al destino.
- **Independiente de los medios:** puede funcionar sobre diferentes medios, como:
  - Cable de cobre.
  - Fibra óptica.
  - Redes inalámbricas.

> **MTU (Maximum Transmission Unit):** tamaño máximo de la PDU que puede transportar un medio de red.
---
# 2. Paquete IPv4
El **encabezado IPv4** contiene información necesaria para entregar el paquete hasta su destino.

### Campos importantes del encabezado IPv4

- **Versión:** indica la versión de IP.
- **DS:** información relacionada con el servicio/tráfico.
- **TTL:** limita el tiempo de vida del paquete.
- **Protocolo:** identifica el protocolo de la capa superior.
- **Suma de verificación:** permite comprobar el encabezado.
- **Dirección IPv4 de origen:** identifica al emisor.
- **Dirección IPv4 de destino:** identifica al receptor.

Otros campos importantes:

- **IHL (Internet Header Length):** indica la longitud del encabezado.
- **Longitud Total:** indica el tamaño total del paquete.
- **Identificación, Señaladores y Desplazamiento de fragmentos:** permiten controlar los fragmentos de un paquete.

### Fragmentación IPv4
Un router puede necesitar **fragmentar un paquete IPv4** cuando debe enviarlo a través de un medio cuya **MTU es más pequeña**.
---

# 3. Paquete IPv6
IPv4 presenta algunas limitaciones:

- Agotamiento de direcciones IPv4.
- Falta de conectividad de extremo a extremo.
- Mayor complejidad de la red.

**IPv6** fue diseñado para solucionar estas limitaciones.

### Ventajas de IPv6

- Mayor espacio de direccionamiento.
- Mejor manejo de paquetes.
- Elimina la necesidad de NAT en muchos escenarios.

### Espacio de direcciones

IPv4 utiliza direcciones de **32 bits**, proporcionando aproximadamente:
**4.294.967.296 direcciones únicas.**
IPv6 utiliza direcciones de **128 bits**, proporcionando:
**340.282.366.920.938.463.463.374.607.431.768.211.456 direcciones.**
---
## 4. Encabezado IPv6
El encabezado IPv6 fue simplificado respecto a IPv4.
Sus principales campos son:
- **Versión**
- **Clase de tráfico**
- **Etiqueta de flujo**
- **Longitud de carga útil**
- **Siguiente encabezado**
- **Límite de salto**
- **Dirección IP de origen**
- **Dirección IP de destino**

### Encabezados de extensión (EH)
IPv6 puede utilizar **Encabezados de Extensión (EH)** para proporcionar información adicional de la capa de red.
Los EH son:
- **Opcionales.**
- Se colocan entre el encabezado IPv6 y los datos.
- Permiten funciones adicionales como:
  - Fragmentación.
  - Seguridad.
  - Movilidad.
  - Otras funciones de red.

### Diferencia importante entre IPv4 e IPv6

| Característica | IPv4 | IPv6 |
|---|---|---|
| Tamaño de dirección | 32 bits | 128 bits |
| Cantidad de direcciones | ~4,3 mil millones | ~3,4 × 10³⁸ |
| NAT | Puede utilizarse | No es necesario en muchos escenarios |
| Fragmentación | Puede realizarla un router | Los routers **no fragmentan** paquetes IPv6 |
| Encabezado | Más complejo | Simplificado |
| Encabezados de extensión | No es su mecanismo principal | Sí, son opcionales |

---


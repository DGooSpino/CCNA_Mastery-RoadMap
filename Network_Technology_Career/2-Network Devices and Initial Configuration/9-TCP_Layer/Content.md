# Resumen: Capa de Transporte (TCP vs UDP)

## 1. Fundamentos de la Capa de Transporte
    * **Función:** Administra la comunicación lógica entre aplicaciones en diferentes hosts (seguimiento de conversaciones, segmentación, reensamblaje y multiplexación).
    * **Direccionamiento (Sockets):** La combinación de una **IP + Puerto** forma un *Socket* (ej. `192.168.1.5:1099` a `192.168.1.7:80`).
    * **Rangos de Puertos (IANA):**
    * **Bien Conocidos (`0 - 1023`):** Servicios del sistema/infraestructura (HTTP 80, HTTPS 443, SSH 22, DNS 53).
    * **Registrados (`1024 - 49151`):** Bases de datos y servicios (MySQL 3306, Postgres 5432, Redis 6379, Node/React 3000/8080).
    * **Dinámicos / Efímeros (`49152 - 65535`):** Asignados temporalmente por el SO como puerto de origen del cliente.

---

## 2. Protocolo TCP (Transmission Control Protocol)
    Orientado a la conexión, con estado y altamente confiable. Ideal para bases de datos, APIs, SSH y peticiones web (HTTP/HTTPS).

    ### Características Clave:
    * **Conexión:** Requiere un apretón de manos de 3 vías (*3-Way Handshake*) para iniciar y finalizar la sesión.
    * **Fiabilidad y Orden:** Usa **Números de Secuencia (SEQ)** para ordenar datos y **Acuses de Recibo (ACK)** de expectativa para confirmar lo recibido y retransmitir lo perdido.
    * **Control de Flujo:**
    * **Tamaño de la Ventana (*Window Size*):** Campo de 16 bits que indica cuántos bytes puede recibir el destino antes de requerir un ACK. Evita saturar la memoria/CPU del receptor.
    * **MSS (*Maximum Segment Size*):** Tamaño máximo de datos (en bytes) por segmento, negociado en el enlace inicial.

### Campos Principales del Encabezado TCP:
    * Puertos Origen y Destino (16 bits c/u)
    * Número de Secuencia y Número de ACK (32 bits c/u)
    * Bits de Control (Flags: SYN, ACK, FIN, RST, etc.)
    * Tamaño de la Ventana, Suma de Comprobación y Urgente

---

## 3. Protocolo UDP (User Datagram Protocol)
    Protocolo liviano, sin conexión y sin estado (*best-effort*). Prioriza la velocidad sobre la fiabilidad. Ideal para VoIP, streaming en vivo y consultas DNS rápido.

### Características Clave:
    * **Sin Estado:** Ni el cliente ni el servidor rastrean la sesión.
    * **Baja Sobrecarga:** Encabezado compacto de solo **8 bytes** (vs los 20+ bytes de TCP).
    * **Sin Control de Flujo:** No garantiza orden, entrega ni retransmisión de paquetes perdidos (si la app necesita fiabilidad, debe gestionarla en la capa de aplicación).

### Campos del Encabezado UDP:
    * Puerto Origen (16 bits)
    * Puerto Destino (16 bits)
    * Longitud (16 bits)
    * Suma de Comprobación (16 bits)

---

## 4. Diagnóstico de Red
    * **`netstat`:** Utilidad esencial para inspeccionar conexiones activas, puertos abiertos, protocolos en uso (TCP/UDP) y el estado de la sesión local vs externa.
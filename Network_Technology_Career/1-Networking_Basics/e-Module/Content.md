

## 1. Protocolos de Comunicación

Los protocolos son las reglas necesarias para que las computadoras se comuniquen correctamente a través de la red. Estos definen aspectos fundamentales como:

* **Formato del mensaje:** Estructura específica que debe utilizarse al enviar un mensaje.
* **Tamaño del mensaje:** Reglas estrictas sobre el tamaño de los fragmentos transmitidos según el canal.
* **Sincronización:** Determina la velocidad de transmisión de los bits y cuándo un host puede enviar datos.
* **Codificación:** Conversión del mensaje en bits (sonidos, ondas de luz o impulsos eléctricos) según el medio de red.
* **Encapsulación:** Proceso de agregar un encabezado con información de direccionamiento (origen y destino) a los elementos de datos.
* **Patrón de mensaje:** Define si se requiere confirmación previa (solicitud y respuesta) o si los datos se transmiten directamente.

## 2. Estándares de Comunicación

* **Definición:** Un estándar es un conjunto de reglas que asegura que diferentes dispositivos en una red se comuniquen sin problemas bajo las mismas normas.
* **RFC (Request for Comments / Petición de Comentarios):** Documentos numerados que registran la evolución de los estándares de Internet desde su discusión hasta su aprobación final.
* **IETF (Internet Engineering Task Force):** Organización encargada de publicar y administrar los estándares de Internet y sus documentos RFC.

## 3. Modelos de Comunicación de Red

La interacción entre protocolos se organiza en una **pila de protocolos**, donde los niveles superiores dependen de los servicios de los niveles inferiores de forma independiente.

### Modelo TCP/IP
Consta de 4 capas principales:
1. **Aplicación:** Representa datos para el usuario, codificación y control de diálogo.
2. **Transporte:** Admite la comunicación entre varios dispositivos a través de diversas redes.
3. **Internet:** Determina la mejor ruta a través de la red.
4. **Acceso a la red:** Hardware y medios físicos que componen la red.

### Modelo de Referencia OSI
Creado por la ISO para el diseño, especificación y resolución de problemas de redes, dividido en 7 capas:
* **7 - Aplicación:** Comunicaciones de proceso a proceso.
* **6 - Presentación:** Representación común de los datos transferidos.
* **5 - Sesión:** Organiza el diálogo y gestiona el intercambio de datos.
* **4 - Transporte:** Segmenta, transfiere y reensambla los datos().
* **3 - Red:** Intercambio de datos individuales entre dispositivos finales identificados.
* **2 - Enlace de datos:** Intercambio de tramas de datos a través de un medio común.
* **1 - Físico:** Medios mecánicos, eléctricos y funcionales para transmitir bits(Last_segment).
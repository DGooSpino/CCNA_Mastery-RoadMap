# Apuntes : Módulo de Servicios de Aplicación

## 1. La Relación Cliente-Servidor
* **Servidor:** Host que ejecuta software para proporcionar información o servicios a otros hosts en la red (ej. servidor web).
* **Cliente:** Software (como Chrome o Firefox) que solicita servicios. Una única PC puede ejecutar varios tipos de software de cliente. Las interacciones complejas funcionan gracias a normas y protocolos acordados.
* **Dinámica clave:** El cliente envía una solicitud y el servidor responde realizando una función (ej. devolver el documento solicitado).
* **Identificadores (URI):** Cadena de caracteres que identifica un recurso de red específico. Sus especializaciones son:
  * **URN:** Identifica solo el espacio de nombres del recurso sin referencia al protocolo.
  * **URL:** Define la ubicación de red de un recurso específico. Las URL HTTP o HTTPS se usan con navegadores web; otros protocolos como FTP, SFTP y SSH también pueden usarse como URL.

---

## 2. Servicios de Aplicaciones de Red
Los servicios de Internet más comunes (búsquedas, redes sociales, streaming, compras en línea, correo y mensajería) dependen de la suite de protocolos **TCP/IP** para transmitir información de manera confiable entre clientes y servidores.
* **Servicios comunes:** DNS, SSH, SMTP, POP, IMAP, DHCP, HTTP y FTP.

---

## 3. Sistema de Nombres de Dominios (DNS)
* **Función:** Permite que los hosts soliciten la dirección IP de un servidor específico. Los nombres están organizados en dominios de alto nivel (ej. `.com`, `.edu`, `.net`).
* **Funcionamiento:** Cuando el servidor DNS recibe la solicitud, verifica su tabla para asociarla con la IP del servidor web. Si no la tiene de forma local, consulta a otro servidor DNS del dominio y devuelve la información al host.

---

## 4. Clientes y Servidores Web
* **HTTP (Puerto 80):** Protocolo no seguro utilizado por los exploradores para solicitar servicios web enviando solicitudes al puerto 80. Los datos pueden ser interceptados fácilmente.
* **HTTPS (Puerto 443):** Versión segura que utiliza protocolos de transporte cifrados enviando solicitudes al puerto 443.
* **Respuestas y Formato:** Al recibir una solicitud, el servidor responde enviando la página web codificada en **HTML**, la cual indica al navegador cómo formatear la página, gráficos y fuentes a usar. HTTP y HTML permiten que servidores y clientes de diferentes fabricantes funcionen sin problemas.

---

## 5. Clientes y Servidores FTP
* **Función:** Permite transferir archivos de una computadora a otra y administrar archivos de forma remota (subir, descargar, eliminar, renombrar).
* **Puertos de comunicación:**
  * **Puerto 21 TCP:** Utilizado para enviar solicitudes de control y establecer la sesión.
  * **Puerto 20 TCP:** Utilizado por el servidor para la transferencia real de los archivos de datos.
* **Interfaces:** Los sistemas operativos (Windows, Mac OS, Linux) incluyen interfaces de línea de comandos, y existen clientes GUI de arrastrar y soltar.

---

## 6. Terminales Virtuales
* **Telnet (Puerto 23 TCP):** Proporciona emulación de terminal basada en texto (sesión vty). **No es seguro:** no admite cifrado de datos; toda la información viaja en texto plano y puede ser interceptada fácilmente.
* **SSH (Secure Shell):** Proporciona inicio de sesión remoto seguro, autenticación sólida y transporte de datos cifrados. Los profesionales de la red deben usar SSH en lugar de Telnet siempre que sea posible.

---

## 7. Correo Electrónico y Mensajería
* **Almacenamiento y Acceso:** Los servidores almacenan correspondencia en buzones; los usuarios acceden mediante clientes de correo (como Outlook, Webmail, Gmail).
* **Protocolos principales:**
  * **SMTP (Puerto 25):** Utilizado por clientes para enviar mensajes al servidor local, o entre servidores de correo.
  * **POP3 (Puerto 110):** Descarga los mensajes al cliente. Por defecto, los mensajes **no** se retienen en el servidor una vez descargados.
  * **IMAP4 (Puerto 143):** A diferencia de POP, **conserva** los mensajes en los buzones del servidor a menos que el usuario los elimine explícitamente.
* **Mensajería Instantánea y VoIP:** La mensajería permite chatear en tiempo real mediante clientes web o integrados. La telefonía IP utiliza **VoIP** (tecnología peer-to-peer) para convertir señales de voz analógicas en datos digitales empaquetados para su transmisión.
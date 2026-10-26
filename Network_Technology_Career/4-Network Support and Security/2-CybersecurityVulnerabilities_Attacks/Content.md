## 📌 1. Introducción a las Amenazas y Dominio de Riesgo

Un **dominio de amenaza** es un área de control, autoridad o protección que los atacantes pueden aprovechar para acceder a un sistema. 

### Vectores de Entrada y Origen
* **Vectores de acceso:** Acceso físico, redes inalámbricas, dispositivos Bluetooth/NFC, correo electrónico malicioso, redes sociales, medios extraíbles y entornos en la nube.
* **Causas subyacentes:** Errores de software, errores humanos, sabotaje, robo, fallas de equipos, interrupción de servicios públicos y desastres naturales.
* **Tipos de amenazas:**
  * **Internas:** Provenientes de empleados antiguos o actuales.
  * **Externas:** Provenientes de atacantes aficionados o expertos.
---

## 🏢 2. Dominios de Seguridad
### A. Dominio de Usuario
Incluye a empleados, clientes y socios contractuales. A menudo se considera **el eslabón más débil** de la seguridad.
* **Riesgos comunes:** Falta de conciencia sobre seguridad, políticas mal aplicadas, robo de datos, descargas no autorizadas, visitas a sitios web no autorizados y destrucción intencional de datos/sistemas.

### B. Dominio de Dispositivos y LAN
* **Dispositivos:** Acceso no autorizado a sistemas desatendidos, descargas de malware y software desactualizado.
* **Red de Área Local (LAN):** Accesos no autorizados, vulnerabilidades del SO, puntos de acceso no autorizados, intercepción de datos en tránsito y mala configuración de firewalls.

### C. Dominio de Nube Privada y Aplicaciones
* **Nube Privada:** Sondeo de red, exploración de puertos, vulnerabilidades en software y acceso no autorizado a recursos internos.
* **Aplicaciones:** Interrupción/caída del servidor, fallas de hardware, pérdida de datos y vulnerabilidades en software cliente-servidor o aplicaciones web.

---
## 🔬 3. Conceptos Avanzados de Ciberseguridad
* **Amenazas Persistentes Avanzadas (APT):** Ataques prolongados y elaborados mediante malware.
* **Ataques de Algoritmo:** Explotan procesos de software para generar comportamientos no previstos.
* **Puertas Traseras (Backdoors):** Herramientas como *Netbus* o *Back Orifice* que usan Administradores Remotos (RAT) para omitir autenticaciones estándar.
* **Rootkits:** Malware diseñado para escalar privilegios, modificar archivos del sistema e interferir con herramientas forenses y de monitoreo (muy difíciles de detectar).

> ℹ️ **Estándares e Indicadores Globales:**
> * **CVE:** Base de datos de vulnerabilidades conocidas (patrocinada por US-CERT y DHS).
> * **IOC:** Indicadores de Compromiso que caracterizan a los ataques.
> * **STIX y TAXII:** Estándares automatizados para el intercambio estructurado de información de amenazas.

---
## 🎭 4. Ingeniería Social y Engaño

Estrategia no técnica para manipular a las personas a realizar acciones riesgosas o revelar información confidencial.

| Tipo de Ataque / Táctica | Descripción |
| :--- | :--- |
| **Pretexting** | Mentir con una historia elaborada para acceder a datos. |
| **Quid Pro Quo (Algo por algo)** | Ofrecer un beneficio/regalo a cambio de información. |
| **Fraude de Identificación** | Uso de datos robados para adquirir bienes o servicios. |
| **Shoulder Surfing** | Espiar por encima del hombro para capturar credenciales/PIN. |
| **Dumpster Diving** | Buscar información confidencial directamente en la basura. |
| **Piggybacking / Tailgating** | Seguir a alguien para acceder físicamente a áreas restringidas. |
| **Tácticas psicológicas** | Autoridad, intimidación, consenso, escasez, urgencia y familiaridad. |
| **Otros engaños** | Facturas falsas, Typosquatting (URLs falsas), Ataques de Abrevadero (Watering Hole) y campañas de influencia. |

### 🛡️ Defensas contra el Engaño
* Capacitar al personal para no revelar datos confidenciales a terceros.
* Identificar correos sospechosos y no hacer clic en enlaces no verificados.
* Cancelar descargas automáticas o no iniciadas.
* Resistir la presión social o de desconocidos.

---

## 💻 5. Ataques Cibernéticos y Malware

### Tipos de Malware
* **Virus:** Se replica ejecutándose en el sistema.
* **Gusanos:** Se replican de forma autónoma a través de redes.
* **Troyanos:** Se disfrazan de software legítimo.
* **Bombas Lógicas:** Se activan ante fechas, horas o eventos específicos.
* **Ransomware:** Cifra archivos/hardware para exigir un rescate.
* **Keyloggers:** Registran las pulsaciones de teclado para robar credenciales.

### Ataques de Red y Capa 2
* **Denegación de Servicio (DoS):** Abruma o interrumpe los servicios con volúmenes masivos de datos o paquetes maliciosos.
* **Ataques DNS:** Suplantación de dominio para redirigir nombres legítimos a IPs maliciosas.
* **Ataques de Capa 2:**
  * **MAC Spoofing & Inundación MAC:** Ocultar o inundar la red con direcciones MAC falsas para eludir la autenticación o colapsar conmutadores.
  * **ARP / IP Spoofing:** Vincular IPs legítimas a direcciones falsas u ocultar el origen de los paquetes.
* **Hombre en el Medio (MitM / MitMo):** Intercepción de datos en tránsito dentro de una red o dispositivo móvil.
* **Ataques de Día Cero (Zero-Day):** Explotación de vulnerabilidades desconocidas públicamente.

---

## 📱 6. Dispositivos Móviles e Inalámbricos

* **Grayware:** Aplicaciones no deseadas o molestas.
* **SMiShing:** SMS falsos para dirigir a sitios maliciosos o números fraudulentos.
* **Rogue APs / Evil Twins:** Puntos de acceso falsos para interceptar tráfico (MitM) o desautenticar usuarios.
* **Bluejacking / Bluesnarfing:** Envío de mensajes no solicitados o robo de información mediante Bluetooth.

### Protocolos y Recomendaciones Inalámbricas
* **Evolución:** Sustituir **WEP** (inseguro y sin gestión de claves) por **WPA2/WPA3**.
* **Buenas Prácticas:** 
  * Colocar APs fuera del perímetro si es necesario.
  * Usar herramientas como *NetStumbler* para detectar APs no autorizados.
  * Aislar la red Wi-Fi de invitados.
  * Exigir uso de **VPN** en redes Wi-Fi públicas.

---

## 🚀 7. Ataques a Aplicaciones y Correo Electrónico

### Vulnerabilidades en Aplicaciones
* **Cross-Site Scripting (XSS):** Inyección de código malicioso en sitios legítimos para ejecutar malware o robar sesión.
* **Inyecciones (SQL, XML, LDAP, DLL):** Inserción de datos mal formateados para manipular bases de datos, acceder a Windows o consultar servidores LDAP.
* **Ejecución Remota de Código (RCE):** Explotación de fallas para ejecutar comandos con privilegios en el servidor remoto.
* **Otros:** CSRF, condiciones de carrera, errores de entrada, fallas en APIs, ataques de reproducción, cruce de directorios y agotamiento de recursos.

### Amenazas por Correo Electrónico
* **Spam:** Correo no solicitado que puede contener código dañino.
* **Phishing:** Suplantación de identidad generalizada.
* **Spear Phishing:** Ataque dirigido a un individuo específico.
* **Whaling:** Phishing de alto nivel enfocado en ejecutivos o políticos.
* **Vishing / Pharming:** Ataques mediante voz (Vishing) o redirección de sitios web (Pharming).

---
## 🛡️ Medidas Globales de Defensa y Mitigación

1. **Código Seguro:** Aplicar validación de entradas en el desarrollo de software y pruebas de seguridad antes de producción.
2. **Actualizaciones:** Mantener parches al día en el sistema operativo y las aplicaciones.
3. **Control de Red:** Filtrar paquetes entrantes en firewalls y bloquear ICMP en el perímetro.
4. **Protección de Correo y Navegador:** Implementar antivirus, filtros antispam y programas de concientización para los usuarios.
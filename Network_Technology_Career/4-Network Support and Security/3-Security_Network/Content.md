## 1. Fundamentos de Seguridad

El cubo de ciberseguridad proporciona una forma útil de pensar en la protección de datos. La primera dimensión del cubo identifica los objetivos de **confidencialidad, integridad y disponibilidad (CIA)**:

* **Confidencialidad:** Se refiere a la prevención de la divulgación de información a personas no autorizadas.
* **Integridad:** Hace referencia a la precisión, la uniformidad y la confiabilidad de datos. Garantiza que los datos no sean alterados por entidades no autorizadas mientras se capturan, almacenan, recuperan, actualizan y transfieren.
  * **Métodos para garantizarla:** Función de hash, comprobaciones de validación de datos, comprobaciones de consistencia de datos y controles de acceso.
* **Disponibilidad:** Se refiere a la necesidad de hacer que los datos sean accesibles para todos los usuarios autorizados siempre que los necesiten. Los ataques cibernéticos y las fallas del sistema pueden desconectar a los usuarios de los datos que necesitan.
  * **Garantía de disponibilidad:** Mantenimiento adecuado de equipos, mantenimiento de software y sistemas actualizados, prueba de copias de seguridad y respaldos, implementación de nuevas tecnologías, monitoreo de la actividad de la red y análisis de vulnerabilidades para detectar amenazas.

### Conceptos Clave
* **Estados de los datos:** En tránsito, en reposo en almacenamiento o en proceso.
* **Pilares de la defensa:** Las personas, la tecnología, y las políticas y prácticas.
* **Tríada de la CIA:** Confidencialidad, Integridad y Disponibilidad (Confidentiality, Integrity, Availability).

---

## 2. Control de Acceso

### Tipos de Control de Acceso

1. **Control de Acceso Físico:**
   * Evita que usuarios no autorizados accedan físicamente a redes, datos y equipos.
   * Determina quién, dónde y cuándo las personas pueden ingresar o salir de una instalación.
   * **Ejemplos:** Guardias, vallas perimetrales, detectores de movimiento, cerraduras de dispositivos, puertas cerradas con tarjetas magnéticas o combinaciones, perros guardianes, cámaras de video y alarmas.

2. **Control de Acceso Lógico:**
   * Soluciones de hardware y software para administrar el acceso a recursos y sistemas.
   * Herramientas y protocolos para identificación, autenticación, autorización y contabilidad (AAA).
   * **Ejemplos:** Cifrado, tarjetas inteligentes con chips integrados, contraseñas, biometría, Listas de Control de Acceso (ACL), firewalls/cortafuegos y Sistemas de Detección de Intrusos (IDS).

3. **Control de Acceso Administrativo:**
   * Políticas y procedimientos que definen las organizaciones para implementar y hacer cumplir el control de acceso no autorizado.
   * **Ejemplos:** Políticas aprobadas, procedimientos definidos, verificaciones de antecedentes y clasificación de datos.

---

### Servicios de Seguridad AAA e Identidad

* **Autenticación:** Verifica la identidad de cada usuario para evitar el acceso no autorizado. La identificación aplica las reglas establecidas por la política de autorización mediante identificadores únicos (nombres de usuario, contraseñas, PINs, datos biométricos como huellas dactilares, escaneos de retina o reconocimiento de voz).
* **Autorización:** Determina a qué recursos pueden acceder los usuarios, junto con las operaciones que pueden realizar e incluso cuándo pueden realizarlas.
* **Contabilidad:** Realiza un seguimiento de lo que hacen los usuarios en la red (a qué acceden, cuándo acceden y qué hacen con ello). Rastrea una acción hasta una persona o proceso, recopila la información en registros e informa los datos de uso para auditorías o facturación.

### Gestión de Identidad y Autenticación Adicional
* **Gestión de Identidad Federada (FIM):** Permite a varias empresas autorizar a sus usuarios a utilizar las mismas credenciales para obtener acceso a las redes de todas las empresas del grupo. *Riesgo:* Si un atacante explota el sistema, obtendrá acceso a múltiples sistemas o aplicaciones.
* **Políticas de Contraseña:** Garantizan longitud y complejidad (mínimo 8 caracteres, combinación de mayúsculas, minúsculas, números y símbolos).
* **Autenticación Multifactor (MFA):** Combina otros medios de identidad junto con contraseñas.

---

## 3. Defensa de Sistemas y Dispositivos

### Gestión y Configuración del Sistema Operativo
* Se requiere un enfoque sistemático para establecer procedimientos de monitoreo de seguridad, evaluar actualizaciones e instalarlas mediante un plan documentado.
* **Líneas de Base (*Base lines*):** Ayudan a indicar el compromiso del sistema cuando el rendimiento se desvía significativamente de la línea de base.
* **Malware sin archivos (*Fileless malware*):** Difíciles de detectar ya que no dejan huella; explotan shells de comando programables (scripts en Python, Bash o VBA pueden ser maliciosos).
* **Administración de Parches:** El software debe parchearse de forma proactiva. Los administradores deben evaluar los parches antes de instalarlos. Los sistemas automatizados brindan control sobre fechas, horas e informes del estado de actualización.

---

### Seguridad en Puntos Finales (*Endpoint Security*)
* **Firewalls basados en Host:** Bloquean tráfico entrante y saliente.
* **HIDS (Host-based Intrusion Detection System):** Monitorean los sistemas, la seguridad de inicio de sesión y los eventos del sistema.
* **HIPS (Host-based Intrusion Prevention System):** Detectan actividad maliciosa, envían alarmas, registran eventos, restablecen conexiones o descartan paquetes.
* **EDR (Endpoint Detection and Response):** Solución integrada que monitorea y recopila datos continuamente de los puntos finales.
* **DLP (Data Loss Prevention):** Evita que los datos confidenciales se pierdan, se utilicen indebidamente o sean accedidos por usuarios no autorizados.
* **NGFW (Next-Generation Firewall):** Combinan cortafuegos tradicionales con funciones avanzadas de filtrado en dispositivos de red.

---

### Cifrado y Protección Física de Dispositivos

* **Cifrado de Host:**
  * **EFS (Encrypting File System):** Cifrado de archivos en Windows.
  * **BitLocker:** Cifrado de disco completo (FDE). Requiere un módulo de plataforma segura (**TPM**) en el BIOS.
  * **BitLocker To Go:** Cifrado para unidades extraíbles.
* **Integridad de Arranque (*Secure Boot*):** Estándar que garantiza que el dispositivo arranque únicamente con software confiable y no haya sido alterado.
* **Protección en macOS / Apple:** Incluye procesador de seguridad especial, integridad de arranque, motor de cifrado AES basado en hardware (*Apple Data Protection* y *FileVault*), aislamiento biométrico, función *Buscar mi dispositivo*, antimalware *XProtect*, herramienta *MRT* y *Gatekeeper* (garantiza la instalación exclusiva de software firmado digitalmente).
* **Protección Física de Dispositivos:** Uso de candados de cable, cerraduras de puertas con llave o cifradas, e inventario/seguimiento mediante identificación por radiofrecuencia (RFID).

---

## 4. Protección Antimalware

### Estrategia de Red y Tipos de Antimalware
Para proteger la red se requiere reforzar el perímetro mediante:
* Enrutadores reforzados (*hardened routers*) con servicios VPN.
* Firewalls de próxima generación (NGFW).
* Dispositivos IPS.
* Servidores de servicios AAA.

### Tipos de Programas Antimalware
1. **Basado en firmas (*Signature-based*)**
2. **Basado en heurística (*Heuristic-based*)**
3. **Basado en comportamiento (*Behavior-based*)**

### Arquitecturas de Antimalware y Firewalls en Host
* **Antivirus basado en agentes (*Agent-based*):** Se ejecuta localmente en cada máquina protegida.
* **Antivirus sin agente (*Agentless*):** Realiza escaneos en los hosts desde un sistema centralizado.
* **Firewall basado en host:** Restringe conexiones entrantes y salientes a conexiones iniciadas solo por ese host.
  * *Ejemplos:* Windows Defender Firewall con Seguridad Avanzada, `iptables`, `nftables` y **TCP Wrappers** en Linux.
* **Protección de Terminales en Redes Sin Fronteras:** Combina técnicas de red y host mediante herramientas como Cisco Secure Endpoint, Cisco Secure Email, Cisco Umbrella y Sistemas de Control de Admisión de Red (NAC).
* **Categorías de Antimalware:** Protección contra antivirus, adware, phishing y spyware.

---

## 5. Firewalls y Prevención de Intrusiones Basada en Host

### Funciones y Tipos de Firewalls
Los firewalls actúan como el único punto entre redes internas y externas, haciendo cumplir políticas de control de acceso, desinfectando el flujo de protocolos y bloqueando datos maliciosos.

| Tipo de Firewall | Capa del Modelo OSI | Características Principales |
| :--- | :--- | :--- |
| **Filtrado de paquetes (Sin estado / Stateless)** | Capas 3 y 4 | Evalúa información de red/transporte. Bajo impacto en rendimiento, pero vulnerable a suplantación de IP (*spoofing*) y paquetes fragmentados. Usa ACLs complejas. |
| **Con Estado (Stateful)** | Capas 3, 4 y 5 | Analiza el estado de las conexiones. Más efectivo contra tráfico no deseado, aunque no previene ataques a capa de aplicación ni rastrea bien puertos dinámicos. |
| **Puerta de Enlace de Aplicación (Proxy Firewall)** | Capas 3, 4, 5 y 7 | Filtra tráfico a nivel de aplicación e inspecciona el contenido de los paquetes. |
| **Próxima Generación (NGFW)** | Capas 3 a 7 | Combina la inspección con estado con prevención de intrusiones (IPS), inspección profunda de paquetes y control de aplicaciones. |
| **Transparente** | Capa 2 | Filtra el tráfico entre dos interfaces configuradas en modo puente (*bridge*). |
| **Híbrido** | Múltiples capas | Combina atributos de varios tipos de cortafuegos. |

---

## 6. Acceso Seguro Inalámbrico

### Amenazas en Redes Inalámbricas
* Intercepción de datos y ataques de Denegación de Servicio (DoS) por dispositivos mal configurados o interferencias.
* Puntos de acceso no autorizados (*Rogue APs*) utilizados para capturar direcciones MAC, paquetes de datos, u obtener acceso mediante ataques de intermediario (**MitM - Man in the Middle**).
* **Ocultación de SSID (*SSID Cloaking*):** Deshabilita la trama de baliza (*beacon frame*) del SSID.
* **Filtrado MAC:** Permite o deniega el acceso según la dirección física de hardware.

### Protocolos de Autenticación y Cifrado
* **Autenticación Abierta:** Solo debe usarse cuando la seguridad no sea una preocupación.
* **Autenticación de Clave Compartida:**
  * **WEP / WPA:** Obsoletos e inseguros.
  * **WPA2:** Mínimo recomendado. Utiliza **TKIP** o **AES** (Estándar de Cifrado Avanzado).
  * **WPA3:** Método recomendado según el estándar 802.11.
    * *WPA3-Personal:* Usa autenticación mediante contraseña previamente compartida.
    * *WPA3-Enterprise:* Requiere servidor de autenticación **RADIUS** (802.1X con EAP).
    * *Redes Abiertas / Públicas WPA3:* Utiliza Cifrado Inalámbrico Oportunista (**OWE**) para cifrar todo el tráfico sin requerir contraseña.
    * *Incorporación IoT:* Utiliza el Protocolo de Aprovisionamiento de Dispositivos (**DPP**).
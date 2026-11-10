## 1. Estado Actual de la Ciberseguridad
- **Evolución:** Las amenazas pasaron de virus experimentales en los años 70 a ataques globales sofisticados (Ransomware, APTs, ataques impulsados por IA) dirigidos a la nube, sistemas legados e infraestructura IoT.
- **Vectores de Ataque:**
  - **Externos:** Infiltración mediante conexiones a Internet dirigidas a la red corporativa.
  - **Internos:** Empleados que comprometen la red por accidente o malicia (fugas de datos, servidores comprometidos, interrupciones de red o introducción de dispositivos infectados). Tienen mayor peligro debido al acceso físico y conocimiento interno.
- **Protección de Datos y DLP:** Los datos representan el activo más valioso de las organizaciones. Se requiere implementar controles de Prevención de Pérdida de Datos (DLP) a nivel estratégico, operativo y táctico para evitar daños reputacionales y legales.
- **Vectores de Pérdida de Datos:** Correo electrónico/redes sociales, dispositivos sin cifrar, almacenamiento en la nube, medios extraíbles, documentos en papel y controles de acceso inadecuados.

---

## 2. Actores de Amenazas (Threat Actors)
- **Evolución de las Herramientas:** La automatización de las herramientas ha reducido la barrera de conocimiento técnico requerida para ejecutar ataques potentes (relación inversa entre la sofisticación de la herramienta y la destreza necesaria).
- **Tipos de Actores:**
  - **Script Kiddies:** Atacantes inexpertos que utilizan herramientas y programas existentes sin comprender del todo su funcionamiento interno.
  - **Intermediarios de vulnerabilidades (Vulnerability Brokers):** Descubren y reportan *exploits* o fallos de seguridad a cambio de recompensas económicas (*bug bounties*).
  - **Hacktivistas:** Atacantes con motivaciones políticas o sociales que buscan causar impacto mediático o protestar.
  - **Ciberdelincuentes:** Atacantes motivados por lucro económico que operan en economías subterráneas.
  - **Patrocinados por el Estado:** Hackers respaldados por gobiernos dedicados al ciberespionaje e inteligencia militar/comercial.
  - **Personas adentro (Insiders):** Empleados o exempleados con credenciales o acceso autorizado.
  - **Espías corporativos e industriales:** Centrados en la extracción de secretos comerciales y propiedad intelectual para ventaja competitiva.
  - **Grupos terroristas:** Buscan causar interrupciones graves en servicios críticos para promover agendas extremistas.
  - **Hackers éticos:** Profesionales de seguridad autorizados que evalúan, encuentran y corrigen vulnerabilidades.

---

## 3. Malware (Software Malicioso)
- **Definición:** Software diseñado para alterar operaciones, causar daños u obtener acceso no autorizado operando de forma sigilosa.
- **Categorías Principales:**
  - **Virus:** Requieren interacción humana para propagarse e infectar otros archivos. Se adhieren a código o documentos legítimos. Variantes: sector de arranque, firmware, macros, programas y scripts.
  - **Troyanos:** Se disfrazan de aplicaciones útiles para ejecutar código dañino. Variantes: RATs (acceso remoto), envío de datos, destructivos, proxy, FTP, desactivadores de antivirus, Troyanos DoS y keyloggers.
  - **Adware:** Muestra publicidad no deseada en el sistema.
  - **Ransomware:** Cifra archivos del sistema y exige el pago de un rescate.
  - **Rootkits:** Consiguen acceso a nivel de administrador/sistema mientras ocultan su presencia.
  - **Spyware:** Recopila información privada del usuario sin su consentimiento.

---

## 4. Ataques Comunes de Red
- **Reconocimiento:** Recopilación previa de información sobre sistemas, servicios o vulnerabilidades (búsquedas WHOIS, barridos de ping, escaneo de puertos y escaneo de vulnerabilidades).
- **Acceso:** Explotación de autenticaciones o servicios para tomar control o escalar privilegios (ataques de contraseña/cracking, suplantación o *spoofing*, ataques Man-in-the-Middle, desbordamiento de búfer/ *buffer overflow*).
- **Ingeniería Social:** Manipulación psicológica para engañar a los usuarios (Pretexting, Phishing, Spear Phishing, Vishing, Smishing, Baiting, Impersonation, Tailgating, Dumpster Diving).
- **Denegación de Servicio (DoS / DDoS):** Inundación de tráfico o envío de paquetes malformados para ralentizar o colapsar servicios. Los ataques DDoS coordinan múltiples fuentes infectadas (*zombies*) organizadas en redes *botnets*.

---

## 5. Concientización y Respuesta ante Incidentes
- **Señales de Alerta (Red Flags) en Help Desk:** Mensajes no solicitados, lenguaje de urgencia o amenaza, solicitudes de credenciales/datos financieros, archivos adjuntos sospechosos o inconsistencias en los dominios de correo.
- **Pasos para la Respuesta a Incidentes (NIST SP 800-61):**
  1. **Identificación de síntomas:** Observación de comportamientos inusuales.
  2. **Recolección inicial de evidencias:** Capturas de pantalla y registro de actividad del usuario.
  3. **Análisis de logs:** Revisión de registros de sistema y red.
  4. **Diagnóstico preliminar:** Evaluación con base en la evidencia recopilada.
  5. **Documentación y reporte:** Compilación del informe final para escalamiento.
- **Protección del Host:** Antivirus con motores de firma, heurística y comportamiento (Microsoft Defender, XProtect/MRT, Malwarebytes, Kaspersky). Uso de herramientas de rescate en Modo Seguro para infecciones persistentes.

---

## 6. Protección de Datos y Control de Acceso
- **Gestión de Contraseñas:** Longitud recomendada de 12 a 16 caracteres combinando mayúsculas, minúsculas, números y símbolos para prevenir ataques de fuerza bruta, *password spraying* o *credential stuffing*. Uso recomendado de gestores de contraseñas.
- **Autenticación Multi-Factor (MFA):** Requiere al menos dos factores distintos de autenticación:
  - Algo que sabes (contraseña/PIN).
  - Algo que tienes (dispositivo móvil, token físico, hardware key).
  - Algo que eres (datos biométricos).
- **Categorías de Datos Sensibles:** Datos confidenciales de la empresa, datos propietarios/propiedad intelectual, Información de Identificación Personal (PII), datos financieros/tarjetas, registros médicos/salud y documentación legal.
- **Políticas Organizacionales:** Implementación de Política de Uso Aceptable (AUP), políticas de contraseñas, confidencialidad, retención de datos, respuesta a incidentes y seguridad en trabajo remoto.
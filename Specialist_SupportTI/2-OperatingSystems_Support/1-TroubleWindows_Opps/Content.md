## 1. Arranque y Modo Seguro
* **BIOS vs UEFI:** UEFI reemplaza a la antigua BIOS de 16 bits; ofrece mayor seguridad, interfaz gráfica y soporte para discos grandes.
* **Secuencia de arranque:** Define qué dispositivo inicia el sistema (por defecto el disco principal). Se modifica en la UEFI para arrancar desde USB o red.
* **Modo Seguro (Safe Mode):** Ayuda a diagnosticar fallas cargando solo lo esencial.
  * *Acceso:* Configuración (`Settings > System > Recovery > Advanced Startup`), tecla `Shift + Reiniciar`, o tras 3 fallos seguidos (WinRE).
  * *Variaciones:* Básico/F4 (controladores esenciales), Red/F5 (con internet), Símbolo del Sistema/F6 (comandos).

## 2. Pantalla y Energía
* **Pantalla:** Problemas comunes como texto borroso o parpadeo. Claves:
  * *Resolución y Densidad:* Más píxeles = mayor claridad; una mala resolución borra la imagen.
  * *Dot Pitch:* Menor distancia entre puntos = texto más nítido.
  * *Tasa de Refresco (Hz) y FPS:* Los Hz son del monitor, los FPS del rendimiento. Desajustes causan *screen tearing* o *ghosting*.
* **Energía:** Modos para ahorrar batería y optimizar rendimiento.
  * *Sleep (Suspensión):* Guarda datos en la RAM con consumo mínimo de energía (despierta rápido).
  * *Hibernate (Hibernación):* Guarda el estado en el disco duro y apaga el equipo por completo (tarda más en volver).
  * *Apagado y Apagar pantalla:* Opciones para conservar energía.

## 3. Accesibilidad y Navegación
* **Visión y Audición:** Herramientas de inclusión como *Text Size & Scaling* (tamaño de texto), *Magnifier* (lupa), filtros de color, *Narrator* (lector de pantalla), *Mono Audio* y subtítulos en vivo (*Live Capions*).
* **Entrada alternativa:** *Teclado en pantalla (On-Screen Keyboard)* y gestos táctiles para trackpad/pantalla cuando fallan los periféricos físicos.

## 4. Seguridad y Mantenimiento del Sistema
* **BitLocker:** Cifrado de unidades completo que protege los datos ante robos o pérdidas mediante PIN, contraseña, USB o chip TPM.
* **Windows Update:** Tipos de actualizaciones:
  * *Quality:* Mensuales de seguridad y confiabilidad (*Patch Tuesday*).
  * *Feature:* Nuevas funciones (ej. pasar de Win 10 a 11).
  * *Driver y Firmware:* Mejoran compatibilidad y hardware.
* **Administrador de Tareas (Task Manager):** Herramientas clave por pestañas:
  * *Processes:* Aplicaciones y procesos activos.
  * *Performance:* Gráficos de uso de CPU, memoria y red.
  * *Startup Apps:* Programas que arrancan con el sistema.
  * *Details & Services:* Gestión avanzada y control de servicios.

## 5. Respaldo en la Nube
* **Propósito:** Reemplazan a los discos externos para evitar pérdida de datos por fallas o ataques.
* **Principales Servicios:**
  * *OneDrive:* Integrado en Windows, incluye recuperación de archivos (*File Recovery*) por 30 días en la Papelera.
  * *Google Drive:* 15 GB gratis, permite sincronizar carpetas locales (*Mirror*) o trabajar solo en la nube (*Stream*).
  * *Dropbox:* Plan gratuito de 2 GB con sincronización en tiempo real y selección de carpetas locales (*Selective Sync*).
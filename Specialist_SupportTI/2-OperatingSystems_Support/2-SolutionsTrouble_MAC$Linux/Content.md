## 1. Introducción a Linux y macOS

* **Panorama de Sistemas Operativos:** Windows domina el mercado empresarial (73%), macOS a los profesionales creativos (15%) y Linux domina servidores y desarrollo (4%).
* **Filosofía de Unix:** Creado en los Bell Labs (1969) bajo el principio de programas "pequeños y especializados" que trabajan en conjunto.
* **Linux:** Desarrollado por Linus Torvalds en 1991 como un proyecto colaborativo de código abierto con múltiples distribuciones (*distros*) como Ubuntu y Debian.
* **macOS:** Construido por Apple en 2001 sobre bases de Unix con un enfoque propietario y cerrado altamente integrado al hardware.

## 2. Interfaz y Línea de Comandos (CLI)
* **Linux (GUI):** Altamente personalizable; distribuciones como Ubuntu usan el entorno de escritorio GNOME (incluye Lanzador, Barra de Menús superior, Menús de Sistema y Carpeta Home).
* **macOS (GUI):** Utiliza la interfaz Aqua modernizada con elementos similares a iOS (Barra de Menús con menús de aplicación, Spotlight, Centro de Control, Centro de Notificaciones, Dock, Mission Control y Stage Manager).
* **La Terminal (CLI):** Permite comunicarse con el kernel mediante un *shell*. Los comandos se componen de: comando + opciones (con guiones) + argumentos.
* **Emuladores de Terminal:** En Linux existen Terminator, Eterm, Xterm, Konsole y GNOME Terminal; macOS incluye una aplicación de Terminal nativa.

## 3. Comandos Básicos Esenciales y Directorios
* **Estructura:** El directorio raíz se representa con `/` y el directorio personal con la tilde (`~`).
* **Navegación y Archivos:**
  * `pwd`: Muestra la ruta del directorio actual.
  * `ls`: Lista el contenido de un directorio (con la opción `-l` muestra detalles completos como permisos, enlaces, dueño, grupo, tamaño en bytes, fecha y hora).
  * `cd`: Cambia de directorio.
  * `mkdir` / `rmdir`: Crea o elimina directorios.
  * `touch`: Crea archivos vacíos.
  * `cp`: Copia archivos.
  * `rm`: Elimina archivos o directorios.
  * `cat` / `echo`: Muestra contenido de archivos o imprime texto en pantalla.
  * `man`: Accede a las páginas de manual de los comandos.
  * `grep`: Busca patrones o texto dentro de archivos.

## 4. Permisos de Archivos en Unix (Linux/macOS)
* **Categorías:** Se definen para tres niveles: Dueño (*owner*), Grupo (*group*) y Otros (*others*).
* **Tipos de Permisos:** Lectura (`r` = 4), Escritura (`w` = 2) y Ejecución (`x` = 1).
* **Valores Octales Comunes:**
  * `777`: Acceso total para todos.
  * `755`: Dueño con acceso total; grupo y otros con lectura/ejecución.
  * `700`: Acceso exclusivo para el dueño.
  * `666`: Todos pueden leer y escribir.
  * `644`: Dueño lee/escribe; otros solo leen.
  * `600`: Dueño lee/escribe; otros sin acceso.
* **Comandos de Administración de Permisos y Usuarios:**
  * `chmod`: Cambia los permisos de un archivo.
  * `chown`: Cambia el dueño y grupo de un archivo.
  * `sudo`: Ejecuta comandos de forma temporal con privilegios de superusuario (*root*).
  * `passwd`: Cambia la contraseña del usuario.

## 5. Mantenimiento y Tareas Automatizadas
* **Automatización con Cron:** Servicio en segundo plano para tareas programadas mediante una tabla (*cron table* editada con `crontab`).
  * Consta de 6 columnas: Minuto (0-59), Hora (0-23), Día del mes (1-31), Mes (1-12), Día de la semana (0-6) y Comando a ejecutar.

## 6. Seguridad y Resguardos
* **Protección contra Malware y Vulnerabilidades:** Uso de actualizaciones del sistema operativo (*patches*), firmware, antivirus y antimalware basados en bases de datos de firmas (*signature files*).
* **Gestión de Credenciales:** 
  * Ubuntu Linux utiliza `Gnome-keyring` (aplicación "Contraseñas y Claves").
  * macOS utiliza `Keychain Access` (certificados Wi-Fi, notas seguras) y la aplicación `Passwords`.
* **Respaldos (Backups):**
  * Linux utiliza herramientas como Amanda, Bacula, Fwbackups y Déjà Dup (soporta copias locales, cifrado y compresión).
  * macOS cuenta con **Time Machine** integrado para respaldos incrementales automáticos en discos externos o almacenamiento de red, y **iCloud** para sincronización en la nube.

## 7. Diagnóstico de Discos y Virtualización
* **Herramientas de Disco:** Ubuntu utiliza *Disks* (gestión de particiones, SMART, formateo), mientras que macOS usa *Disk Utility* y funciones de reparación como *First Aid*.
* **Virtualización:** Permite ejecutar múltiples sistemas operativos en una sola máquina física mediante un **Hypervisor**.
  * *Tipo 1 (Bare-metal):* Instalado directamente sobre el hardware (servidores empresariales).
  * *Tipo 2 (Hosted):* Software como VirtualBox que corre sobre un sistema operativo existente (macOS, Windows, Linux).
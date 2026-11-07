# Resumen de Soporte TI: Servicios de Directorio, Conectividad y Periféricos

---

## 1. Servicios de Directorio y Unidades Compartidas

### Servicios de Directorio Principales
Gestionan usuarios, equipos y permisos centralizados:
* **Local Users and Groups**: Gestión básica para equipos independientes.
* **Active Directory (AD)**: Sistema de gestión centralizada empresarial de Microsoft.
* **Entra ID**: Servicio de identidad en la nube de Microsoft.
* **AWS IAM**: Gestión de acceso a recursos en la nube de Amazon.

### Autenticación y MFA
La autenticación moderna utiliza **MFA** (Autenticación de Múltiples Factores) mediante apps como *Microsoft Authenticator*, *Google Authenticator* o *Duo Mobile*.
* **Problemas comunes a resolver**: Desincronización de hora, pérdida del dispositivo, fallos al escanear QR y eliminación accidental de la app.

### Unidades Compartidas y Mapeo
* **Servicios Cloud**: OneDrive, Google Drive, Dropbox y Amazon S3 Buckets.
* **Mapeo en cliente**:
  * **Google Drive**: Mediante *Google Drive for Desktop* (sincronización en el Explorador).
  * **Red Local**: Protocolo **SMB** asignando una letra de unidad a la ruta de red.

### Directivas de Grupo (GPO)
Permiten la configuración automática de equipos.
* **Windows**: Reclamar/actualizar directivas con `gpupdate`.
* **Linux / macOS** (unidos a AD vía agent): Actualizar con `sudo adgpupdate`.

---

## 2. Conectividad y Gestión de Usuarios

### Cuentas Locales vs. Dominio
* **Cuentas Locales**: Se administran con `lusrmgr.msc`. *(Nota: Restablecer la contraseña local puede causar la pérdida de acceso a archivos cifrados)*.
* **Cuentas de Dominio**: Se administran en Active Directory con `dsa.msc` (ADUC). Se recomienda forzar el cambio de contraseña en el siguiente inicio de sesión.

### Bloqueo de Cuentas (Account Lockout)
Ocurre tras múltiples intentos fallidos de contraseña para mitigar ataques de fuerza bruta.
* **Solución**: En ADUC (`dsa.msc`), ir a las propiedades del usuario -> pestaña **Accounts** -> marcar **Unlock Account**. *No requiere cambiar la contraseña del usuario*.

---

## 3. Soporte a Periféricos y Hardware

### Impresoras, Escáneres y Fax
* **Impresoras**: Revisar conexiones/controladores, atascos de papel, reiniciar el servicio *Print Spooler* (cola de impresión) y reemplazar tóner.
* **Escáneres**: Limpieza de cristal, ajuste de alineación y reconfigurar rutas de archivo de destino.
* **Fax**: Requerido en sectores legal/salud. Validar cableado, tono de marcado y alineación de rodillos de papel.

### Periféricos de Audio e Entrada
* **Auriculares / Micrófonos**: Seleccionar el dispositivo de salida/entrada correcto en el sistema, revisar silenciadores (mute), permisos de app y reparar conexiones Bluetooth o de cable.
* **Teclados y Mouses**: Verificar baterías, cambiar superficies/pads, validar la distribución de idioma del teclado y ajustar la velocidad del puntero.
* **Pantallas Táctiles**: Habilitar controladores, ejecutar utilidades de calibración y eliminar interferencias.

### Equipos de Teleconferencia y Almacenamiento Externo
* **Sistemas Unificados (ej. Cisco Desk)**: Verificar alimentación, conexiones de red y reiniciar ante congelamientos.
* **Cámaras Web**: Otorgar permisos en el SO, retirar cubiertas físicas de lente y mejorar iluminación.
* **Unidades Externas**: Verificar formato del sistema de archivos, cables/puertos y detener el uso inmediatamente si hay fallos mecánicos para intentar recuperación profesional.
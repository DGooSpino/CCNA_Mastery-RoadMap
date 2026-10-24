## 1. Metodologías de diagnóstico y solución de problemas
* La solución de problemas es un proceso sistemático que puede seguir un enfoque de siete pasos (definir el problema, recopilar información relevante, analizar la información, eliminar posibles causas, proponer hipótesis sobre la causa más probable, probar la hipótesis y resolver el problema) o seguir las capas del modelo OSI.
* La solución estructurada puede aplicar métodos como: de abajo hacia arriba, de arriba hacia abajo, divide y vencerás, seguir el camino, comparación y conjetura educada.
* La elección del método depende del problema y de la experiencia del técnico. Siempre se debe documentar el procedimiento según las normas de la empresa.

## 2. Documentación de Red
* Es esencial para mantener, proteger y solucionar problemas mediante diagramas físicos y lógicos, documentos escritos y líneas base de rendimiento.
* **Topologías documentables:** PAN, LAN, VLANs, WLAN, WMN, CAN, MAN, WAN y VPN.
* **Diagramas:** La topología física detalla ubicaciones y conexiones físicas; la topología lógica incluye direcciones IP, dispositivos, servicios en nube, rutas y políticas de seguridad.
* **Servicios en la nube:** Incluyen SaaS, PaaS, IaaS y modelos XaaS (como DaaS, DRaaS, CaaS, MaaS).
* **Estándares inalámbricos:** IEEE 802.11 (como 802.11b, n, g, ac) operando en espectro sin licencia, diferenciándose de las frecuencias con licencia controladas por la FCC.
* **Líneas base:** Mediciones de rendimiento histórico para detectar desviaciones significativas y problemas de seguridad.
* **CDP (Cisco Discovery Protocol):** Protocolo de capa de enlace para descubrir vecinos directamente conectados mediante comandos como `show cdp neighbors`.

## 3. Mesas de Ayuda (Help Desk) y Políticas de Seguridad
* Las políticas de seguridad definen normas de autenticación, longitud de contraseñas, control de acceso remoto y procedimientos operativos estándar (SOP).
* La mesa de ayuda es el punto central de contacto para usuarios y clientes, gestionando tiquetes de problemas.
* **Habilidades blandas del técnico:** Empatía, escucha activa, trato por el nombre, evitar juicios y escalar problemas cuando sea necesario.
* **Recopilación de datos en hosts:** Uso de comandos y herramientas de conectividad como `ping` y `traceroute` (`tracert`), visores de eventos y administrador de tareas.
* **Dispositivos Cisco:** Se prefiere **SSH** sobre Telnet (por seguridad en texto plano) y comandos IOS como `show ip interface brief`, `show ip route` y `show protocols`.

## 4. Solución de problemas en dispositivos finales
* **Windows:** Uso del Centro de redes y recursos compartidos, y comandos como `ipconfig /all`.
* **Linux:** Herramientas de GUI, comando `ifconfig`, `speedtest` y `ncat` (`nc`).
* **macOS:** Preferencias de red, `ifconfig`, y comandos de red específicos del sistema operativo.
* **Dispositivos móviles:** Verificación en configuraciones de Wi-Fi (iOS) o *Acerca del teléfono > Estado de configuración* (Android).

## 5. Solución de problemas avanzados y comandos de red
* **Modos de Cisco IOS:** EXEC de usuario (nivel básico) y EXEC privilegiado (acceso total ingresando con `enable`). La ayuda contextual se obtiene con el signo `?`.
* **Análisis de protocolos:** Herramientas de captura de paquetes como **Wireshark** (código abierto) para decodificar capas de protocolo.
* **Ancho de banda vs. Rendimiento:** El ancho de banda es la capacidad teórica máxima (bits por segundo); el rendimiento es la velocidad real medida afectada por latencia y demoras. Se puede medir con herramientas como **iPerf**.

## 6. Solución de problemas de conectividad remota
* **Herramientas de escritorio remoto:** Microsoft Remote Desktop, Apple Remote Desktop y TeamViewer (pueden representar riesgos si no se configuran correctamente).
* **Protocolos de acceso:** 
  * *Telnet:* Puerto TCP 23, obsoleto y sin cifrado.
  * *SSH:* Con cifrado, recomendado sobre Telnet (clientes como PuTTY y Tera Term).
  * *RDP:* Protocolo gráfico de Microsoft (puerto 3389), con clientes para múltiples sistemas operativos y alternativas como VNC.
* **VPN (Redes Privadas Virtuales):** Conexiones cifradas sobre redes no seguras. Se dividen en *Sitio a Sitio* (sucursales completas) y *Acceso Remoto* (usuarios individuales mediante clientes como Cisco AnyConnect).
* **Gestión y Automatización:** Uso de plataformas basadas en la nube o locales, SNMP, RMON, y scripts en **Python** para automatizar tareas repetitivas de infraestructura.
## 1. Conmutadores Cisco

* **Función principal:** Un conmutador (switch) se utiliza para conectar dispositivos dentro de la misma red. Por el contrario, un enrutador (router) se usa para conectar varias redes entre sí.
* **Tipos de puertos y conectividad:**
  * **Conmutadores de menor costo:** Solo admiten puertos de interfaz de par trenzado de cobre.
  * **Conmutadores de mayor precio:** Incluyen conexiones de fibra óptica, utilizadas para conectar el conmutador a otros switches situados a grandes distancias.
* **Ancho de banda y compatibilidad:**
  * Las NIC de Ethernet y los puertos del conmutador funcionan con anchos de banda específicos (ej. 10/100 o 10/100/1000 Mbps).
  * El ancho de banda real del dispositivo será el ancho de banda común más alto soportado por ambos extremos.
* **Administración y hardware:**
  * Incluyen configuraciones físicas modulares y fijas.
  * Un conmutador administrado con sistema operativo Cisco permite control sobre puertos individuales o sobre el conmutador en su totalidad.
  * *Ejemplo:* La serie Cisco Catalyst 2960 es adecuada para redes pequeñas y medianas.

---

## 2. Velocidades del Conmutador y Métodos de Reenvío

### Métodos de Reenvío
Los conmutadores utilizan principalmente dos métodos para conmutar datos entre puertos:
1. Almacenamiento y reenvío (*Store-and-Forward*).
2. Conmutación a través de corte (*Cut-Through*), la cual tiene dos variantes:
   * Avance rápido (*Fast-Forward*).
   * Sin fragmentos (*Fragment-Free*).

### Memoria y Configuración Dúplex
* **Métodos de búfer de memoria:** Memoria basada en puertos y memoria compartida.
* **Modos Dúplex:** Dúplex completo (*Full-Duplex*) y medio dúplex (*Half-Duplex*).

### Funciones Automáticas
* **Auto negociación:** Permite que dos dispositivos negocien automáticamente la mayor velocidad y el modo dúplex soportado (si ambos lo admiten, seleccionan *Full-Duplex* y el ancho de banda común más alto).
* **Auto-MDIX (Interfaz cruzada automática):** Detecta automáticamente el tipo de cable conectado (directo o cruzado) y reconfigura las interfaces internamente según sea necesario.

---

## 3. Proceso de Arranque del Conmutador

### Pasos iniciales
1. Los switches Cisco vienen preconfigurados de fábrica para funcionar al encenderse, aunque se deben aplicar ajustes básicos de seguridad.
2. **Pasos de encendido:** 
   1. Verificar componentes.
   2. Conectar cables.
   3. Encender el conmutador.
3. Al encenderse, ejecuta automáticamente la prueba POST (*Power-On Self-Test*).

### Métodos de Administración
* **Fuera de banda (*Out-of-band*):** Requiere una conexión física directa al puerto de consola del dispositivo para la configuración inicial.
* **Dentro de banda (*In-band*):** Se utiliza para monitorear y configurar el dispositivo de forma remota a través de una conexión de red.

### Archivos de Inicio
Al iniciar, el dispositivo carga dos archivos clave en la memoria RAM:
* **Imagen del sistema operativo (IOS):** Se almacena en la memoria Flash.
* **Archivo de configuración inicial (*startup-config*):** Se almacena en la NVRAM.

---

## 4. Enrutadores Cisco

### Componentes Internos
Los enrutadores requieren componentes de hardware esenciales para su funcionamiento:
* Sistema Operativo (IOS)
* CPU, RAM, ROM y NVRAM

### Interfaces y Expansión
* Puertos de consola e interfaces LAN.
* **Ranuras de expansión de interfaz:** Para módulos EHWIC, seriales, DSL, puertos de conmutador o inalámbricos.
* **Ranuras de almacenamiento expandido:** Para tarjetas de memoria flash compacta y puertos USB.

---

## 5. Proceso de Arranque del Enrutador

### Pasos para encender un enrutador Cisco:
1. **Paso 1:** Monte el dispositivo de forma segura en el rack.
2. **Paso 2:** Conecte a tierra el dispositivo.
3. **Paso 3:** Conecte el cable de alimentación.
4. **Paso 4:** Conecte un cable de consola.
5. **Paso 5:** Encienda el enrutador.
6. **Paso 6:** Observe los mensajes de inicio en la PC dentro de la ventana del terminal.

### Métodos de Acceso CLI
* **Acceso a la línea de comandos:** Principalmente mediante puertos de Consola, SSH y Auxiliar (Aux).
* Además, los enrutadores cuentan con interfaces de red para recibir y reenviar paquetes IP.
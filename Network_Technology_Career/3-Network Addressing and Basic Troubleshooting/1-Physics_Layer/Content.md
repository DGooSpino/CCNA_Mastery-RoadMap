## 1. Propósito de la Capa Física

Antes de que pueda ocurrir cualquier comunicación de red, se debe establecer una conexión física a una red local. Una conexión física puede ser una conexión por cable o una conexión inalámbrica mediante ondas de radio.

* **Tarjetas de Interfaz de Red (NIC):** Conectan un dispositivo a la red.
  * **NIC Ethernet:** Se utilizan para conexiones por cable.
  * **NIC WLAN (Red de área local inalámbrica):** Se utilizan para conexiones inalámbricas.

La capa física de OSI proporciona los medios de transporte de los bits que conforman una trama de la capa de enlace de datos a través de los medios de red. Esta capa acepta una trama completa desde la capa de enlace de datos y la codifica como una secuencia de señales que se transmiten en los medios locales. Un dispositivo final o un dispositivo intermediario recibe los bits codificados que componen una trama.

---

## 2. Características de la Capa Física

La capa física consta de circuitos electrónicos, medios y conectores desarrollados por ingenieros. Los estándares de la capa física abordan tres áreas funcionales: **componentes físicos, codificación y señalización**.

### Conceptos Clave de Rendimiento:
* **Ancho de banda:** Capacidad a la que un medio puede transportar datos. El ancho de banda digital mide la cantidad de datos que pueden fluir desde un lugar hacia otro en un período de tiempo determinado.
* **Rendimiento (*Throughput*):** Medida de la transferencia de bits a través de los medios durante un período de tiempo determinado; generalmente es menor que el ancho de banda.
* **Latencia:** Cantidad de tiempo, incluidas las demoras, que les toma a los datos transferirse desde un punto determinado hasta otro.
* **Capacidad de transferencia útil (*Goodput*):** Medida de datos utilizables transferidos durante un período determinado.

### Representación de Bits según el Medio:
* **Cable de cobre:** Las señales son patrones de pulsos eléctricos.
* **Cable de fibra óptica:** Las señales son patrones de luz.
* **Conexión inalámbrica:** Las señales son patrones de transmisiones de microondas.

---

## 3. Cableado de Cobre

Las redes utilizan medios de cobre porque son económicos, fáciles de instalar y tienen baja resistencia a la corriente eléctrica. Sin embargo, están limitados por la distancia y la interferencia de señal.

Los valores de tiempo y voltaje de los pulsos eléctricos son susceptibles a interferencias de dos fuentes: **EMI** (Interferencia Electromagnética) y **Crosstalk** (Diafonía).

### Tipos de Cableado de Cobre:
1. **UTP (*Unshielded Twisted Pair*):**
   * Posee una cubierta exterior para proteger los cables de daños físicos.
   * Contiene pares trenzados para proteger la señal de interferencias.
   * Aislamiento plástico codificado por colores que aísla eléctricamente los cables e identifica cada par.
2. **STP (*Shielded Twisted Pair*):**
   * Utiliza cuatro pares de cables, cada uno envuelto en un blindaje de aluminio.
   * Se envuelve luego en una trenza o lámina metálica general.
3. **Cable Coaxial:**
   * Recibe su nombre porque dos conductores comparten el mismo eje.
   * Se utiliza para conectar antenas a dispositivos inalámbricos y dentro de las instalaciones de clientes por proveedores de Internet por cable.

---

## 4. Cableado UTP

Consta de cuatro pares de hilos codificados por colores que están trenzados entre sí y recubiertos con un revestimiento de plástico flexible. Los cables UTP no utilizan blindaje para contrarrestar los efectos de la EMI y RFI; en su lugar, limitan el crosstalk mediante la **cancelación** y la **variación del número de giros por par de cables**.

* **Estándares:** Cumple con los estándares establecidos por **ANSI/TIA**. La **IEEE** define las características eléctricas del cableado.
* **Conectores:** Se terminan generalmente con un conector **RJ-45**.
* **Tipos de Cables según Convención:**
  * Ethernet Directo (*Straight-Through*)
  * Ethernet Cruzado (*Crossover*)
  * **Rollover (Propietario de Cisco):** Conecta una estación de trabajo al puerto de consola de un enrutador.

---
A:verde, naranja, marrón
B:naranja, verde, marrón

## 5. Cableado de Fibra Óptica

Transmite datos a distancias más largas y con anchos de banda más altos que cualquier otro medio de red, con menos atenuación y siendo **completamente inmune a EMI y RFI**. Es un hilo flexible y extremadamente delgado de vidrio muy puro donde los bits se codifican como impulsos de luz.

### Sectores de Aplicación:
* Redes empresariales.
* FTTH (*Fiber to the Home*).
* Redes de largo recorrido.
* Redes de cable submarino.

### Conectores y Cables de Conexión:
* **Tipos de conectores:** ST, SC, LC y LC multimodo dúplex.
* **Cables de parcheo (*patch cords*):** SC-SC multimodo, LC-LC monomodo, ST-LC multimodo y SC-ST monomodo.
* **Uso en Empresas:** Principalmente como cableado de red troncal (*backbone*) para conexiones punto a punto de alto tráfico y para la interconexión entre edificios de un campus.
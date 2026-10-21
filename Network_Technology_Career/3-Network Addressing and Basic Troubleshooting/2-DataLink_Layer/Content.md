## Topologías
Los dos tipos de topologías utilizadas en redes LAN y WAN son **físicas** y **lógicas**. 

- **Topología Lógica:** La capa de enlace de datos controla el acceso de los datos a los medios. Esta topología influye en el tipo de trama de red y en el método de control de acceso a los medios empleado.
- **Topologías WAN Físicas comunes:**
  - Punto a Punto (conecta directamente dos nodos finales; agregar dispositivos intermedios no altera necesariamente la topología lógica).
  - Concentrador y espécimen (*Hub-and-spoke*).
  - Malla (*Mesh*).
- **Topologías LAN Físicas:**
  - Estrella y Estrella extendida (los nodos se conectan a un dispositivo intermedio central).
  - Bus.
  - Anillo.
---

## Modos de Transmisión y Redes de Acceso Múltiple

- **Semidúplex (*Half-Duplex*):** Los datos se intercambian en una sola dirección a la vez.
- **Dúplex Completo (*Full-Duplex*):** Permite enviar y recibir datos de manera simultánea.
- **Coincidencia de Dúplex:** Ambas interfaces interconectadas deben usar el mismo modo. Una descalibración (*duplex mismatch*) genera ineficiencia y latencia en el enlace.
- **Redes de Acceso Múltiple:** Son redes donde varios nodos pueden acceder al medio simultáneamente (ejemplos: LAN Ethernet y WLAN).
---

## Control de Acceso al Medio (MAC)
Existen dos métodos fundamentales para gestionar el acceso en medios compartidos:

1. **Acceso Basado en Contención:** 
   - Todos los nodos operan en modo semidúplex.
   - Requiere un proceso para gestionar situaciones donde más de un dispositivo transmite al mismo tiempo.
   - *Ejemplos:*
     - **CSMA/CD:** Utilizado en redes LAN Ethernet con topología en bus.
     - **CSMA/CA:** Utilizado en redes inalámbricas (WLAN).
2. **Acceso Controlado:** Cada nodo tiene su turno asignado para acceder al medio.
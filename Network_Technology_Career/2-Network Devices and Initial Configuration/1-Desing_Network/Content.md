# Redes Confiables
A medida que las redes evolucionan, se ha aprendido que hay cuatro características básicas que los arquitectos de redes deben abordar para cumplir con las expectativas de los usuarios: tolerancia a fallas, escalabilidad, QoS y seguridad.

* **Tolerancia a fallas:** Limita la cantidad de dispositivos afectados durante una falla y permite una recuperación rápida. Estas redes dependen de varias rutas entre el origen y el destino; si falla una ruta, los mensajes se pueden enviar inmediatamente por otro enlace.
* **Escalabilidad:** Se expande rápidamente para admitir nuevos usuarios y aplicaciones sin degradar el rendimiento de los servicios para los usuarios existentes. Las redes son escalables porque los diseñadores siguen los estándares y protocolos aceptados.
* **QoS (Calidad de Servicio):** Es un requisito cada vez mayor debido a la convergencia de datos, voz y vídeo en la misma red. Funciona como un mecanismo principal para administrar la congestión y garantizar el envío confiable. El ancho de banda se mide en bps. El enfoque de QoS es **priorizar el tráfico urgente** (importa el tipo de tráfico, no el contenido).
* **Seguridad:** Los administradores deben abordar la **seguridad de la infraestructura de red** y la **seguridad de la información** (protegiendo los paquetes en tránsito y los datos almacenados). Se sustenta en tres requisitos principales: **Confidencialidad, Integridad y Disponibilidad**.

---

# Diseño de Redes Jerárquico

Las direcciones IP contienen dos partes: la porción de red (idéntica para todos los hosts conectados a la misma red local) y la porción de host (identifica de forma individual a cada equipo). Para comunicarse en una red jerárquica se requieren tanto la dirección MAC física como la dirección IP lógica.

## El papel de las direcciones MAC e IP
* La dirección MAC indica la identidad individual de un host específico, pero no su ubicación en la red.
* Si millones de dispositivos en Internet se identificaran únicamente por su dirección MAC, localizarlos sería extremadamente difícil. Por ello, se dividen las redes grandes en partes más pequeñas y fáciles de administrar mediante un **modelo de diseño jerárquico**.

## Capas del Diseño Jerárquico
Las redes jerárquicas escalan de manera eficiente gracias a su estructura de tres capas:

1. **Capa de Acceso:**
   * Proporciona un punto de conexión a la red para los dispositivos de usuarios finales.
   * Permite que varios hosts se conecten a otros dispositivos a través de un conmutador o un punto de acceso inalámbrico.
   * La porción de red de la dirección IP suele ser la misma para los dispositivos dentro de una misma capa de acceso.

2. **Capa de Distribución:**
   * Proporciona un punto de conexión para redes independientes y controla el flujo de información entre ellas.
   * Los dispositivos de esta capa controlan el tipo y la cantidad de tráfico que circula desde la capa de acceso hasta la capa principal.

3. **Capa de Núcleo (Core):**
   * Es una capa troncal de alta velocidad equipada con conexiones redundantes.
   * Su función principal es transportar grandes cantidades de datos entre múltiples redes finales con rapidez.
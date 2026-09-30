## 1. Límites de la Red

* Cada host de una red debe utilizar el router como gateway hacia otras redes.
* Cada host necesita conocer la dirección IPv4 de la interfaz del enrutador conectada a su red local, conocida como **dirección de puerta de enlace predeterminada**.
* La puerta de enlace predeterminada se puede configurar de forma estática en el host o recibirse de manera dinámica mediante DHCP.
* El enrutador inalámbrico funciona como **servidor DHCP** para todos los hosts internos conectados por cable Ethernet o de forma inalámbrica.
* Al conectarse al Proveedor de Servicios de Internet (ISP), el enrutador inalámbrico actúa como **cliente DHCP** para obtener la dirección IPv4 externa correcta en su interfaz de Internet.
* Los ISP proporcionan una dirección enrutable en Internet que otorga acceso a la red externa a los hosts conectados al enrutador.
* El enrutador inalámbrico delimita exactamente la separación entre la red local interna y la red externa de Internet.
---
## 2. Funcionamiento de NAT

* El enrutador inalámbrico obtiene una dirección pública del ISP para enviar y recibir paquetes en Internet, entregando a la vez direcciones privadas a los clientes locales.
* El mecanismo empleado para transformar direcciones privadas en direcciones enrutables hacia Internet se denomina **NAT**.
* Mediante NAT, una dirección IPv4 privada de origen local se convierte en una dirección pública global, invirtiéndose el proceso para los paquetes que ingresan.
* Gracias a NAT, el enrutador inalámbrico mapea y traduce múltiples direcciones IPv4 internas hacia una única dirección pública.
* Únicamente se requiere traducir aquellos paquetes cuyo destino sean redes externas.
* Dichos paquetes atraviesan la puerta de enlace, donde el enrutador inalámbrico sustituye la dirección IPv4 privada del host de origen por su propia dirección IPv4 pública.
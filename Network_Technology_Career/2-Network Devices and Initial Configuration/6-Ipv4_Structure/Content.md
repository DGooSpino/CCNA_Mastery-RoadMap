## 📡 Estructura de la Dirección IPv4
Una dirección **IPv4** es una dirección jerárquica de **32 bits** que se compone de dos partes principales:
- **Porción de red**
- **Porción de host**
Para determinar qué parte corresponde a la red y cuál al host, debemos observar la **secuencia de 32 bits** que forma la dirección IPv4.

### 🔹 Porción de red
Los bits que pertenecen a la **porción de red** deben ser idénticos para todos los dispositivos que se encuentran dentro de la misma red.

### 🔹 Porción de host
Los bits que pertenecen a la **porción de host** deben ser únicos para identificar un dispositivo específico dentro de una red. Por lo tanto:
> Si dos hosts tienen el mismo patrón de bits en la porción de red de una dirección IPv4, significa que ambos hosts pertenecen a la **misma red**.
---

## 🧩 Máscara de subred IPv4
La **máscara de subred IPv4** se utiliza para diferenciar la **porción de red** de la **porción de host** de una dirección IPv4. Cuando se asigna una dirección IPv4 a un dispositivo, la máscara de subred permite determinar cuál es la **dirección de red** del dispositivo.
La dirección de red representa a **todos los dispositivos que pertenecen a la misma red**.
### Ejemplo
```text
Dirección IPv4:
192.168.10.10

Máscara de subred:
255.255.255.0
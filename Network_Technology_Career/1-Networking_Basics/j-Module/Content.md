# 🌐 Resumen del Módulo: IPv6 y Transición de Redes

## 1. Problemas con IPv4 y Motivación para la Migración

El agotamiento inminente del espacio de direcciones de IPv4 fue el catalizador principal que impulsó la creación e implementación de IPv6.

*   **Capacidad de Direccionamiento:** IPv6 opera con un formato de **128 bits**, logrando un espacio masivo de aproximadamente **$340$ sextillones** de direcciones únicas.
*   **Evolución Estructural (IETF):** Al diseñar este sucesor, la *Internet Engineering Task Force* (IETF) integró mejoras cruciales a nivel de arquitectura y protocolos.
*   **El rol de ICMPv6:** A diferencia de IPv4, donde ICMP era principalmente opcional, **ICMPv6** es obligatorio y asume tareas vitales como el Descubrimiento de Vecinos (*Neighbor Discovery*) y la autoconfiguración de direcciones.
---
### 🚀 Técnicas de Transición (Coexistencia IPv4 e IPv6)

Dado que la migración global hacia IPv6 toma tiempo, se han estandarizado tres metodologías clave para garantizar la compatibilidad entre ambos mundos:

1.  **Doble Pila (*Dual-stack*):** 
    *   *¿Qué es?:* Los nodos ejecutan pilas de protocolos IPv4 e IPv6 de manera simultánea.
    *   *Propósito:* Es la técnica principal de **conectividad nativa**.
2.  **Tunelización (*Tunnelling*):** 
    *   *¿Qué es?:* Método para transportar tráfico IPv6 encapsulándolo dentro de paquetes IPv4.
    *   *Propósito:* Permite atravesar infraestructura heredada que aún no comprende IPv6 de forma nativa.
3.  **Traducción (*Translation* - ej. NAT64):** 
    *   *¿Qué es?:* Conversión directa de paquetes entre extremos IPv6 e IPv4.
    *   *Propósito:* Facilita que dispositivos modernos basados únicamente en IPv6 interactúen con servicios legados de IPv4.
---
## 2. Asignación y Formato de Direcciones IPv6

Las direcciones IPv6 se estructuran bajo estrictos parámetros lógicos para mantener la consistencia en el direccionamiento de Capa 3:

*   **Longitud Estándar:** 128 bits en total, expresados en notación hexadecimal.
*   **División por Hextetos:** Se componen de **$32$ dígitos hexadecimales** agrupados en **$8$ bloques de $16$ bits** conocidos como *hextetos*, separados por dos puntos (`:`).
*   **Sensibilidad de Caja:** Son completamente agnósticas a mayúsculas y minúsculas.
*   **Ejemplo de Formato Preferido:**

    $$\text{fe80:0000:0000:0000:0123:4567:89ab:cdef}$$
--
### ⚙️ Reglas de Abreviación y Compresión

Para optimizar la legibilidad y reducir la cantidad de caracteres, se aplican dos reglas fundamentales:

#### **Regla 1: Omitir Ceros Iniciales**
Se pueden descartar los ceros ubicados a la izquierda dentro de cualquier hexteto individual:
*   $01\text{ab} \longrightarrow 1\text{ab}$
*   $09\text{f}0 \longrightarrow 9\text{f}0$
*   $0\text{a}00 \longrightarrow \text{a}00$
*   $00\text{ab} \longrightarrow \text{ab}$

#### **Regla 2: Uso de Dobles Puntos (`::`)**
Los dobles puntos comprimen una cadena continua de uno o más hextetos compuestos exclusivamente por ceros ($0$).
*   **Restricción Estricta:** Solo se permite emplear la secuencia `::` **una sola vez** por dirección para evitar ambigüedades de descompresión.
*   **Criterio de Desempate:** Si existen múltiples cadenas de ceros de igual longitud en una dirección, se comprime obligatoriamente la primera de izquierda a derecha.
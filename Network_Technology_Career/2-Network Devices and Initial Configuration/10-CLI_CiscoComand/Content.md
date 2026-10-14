# Navegación en Cisco IOS
La Interfaz de Línea de Comandos (CLI) de Cisco IOS es un entorno de texto utilizado para configurar, monitorear y mantener routers y switches de la red. Puede emplearse tanto para administración local (fuera de banda) como remota (en banda).

## Modos de Operación Principal
1. **Modo EXEC Usuario (`Router>`)**:
   - Acceso inicial con permisos restringidos.
   - Permite monitoreo y diagnóstico básico sin alterar la configuración del equipo.

2. **Modo EXEC Privilegiado (`Router#`)**:
   - Requiere privilegios administrativos y se ingresa con el comando `enable`.
   - Ofrece acceso total a comandos de diagnóstico avanzado y permite ingresar a los modos de configuración (`configure terminal`).
   - El indicador de configuración global se muestra como `Router(config)#`.

## Comandos Clave de Navegación
- `enable`: Pasa de modo Usuario a modo Privilegiado.
- `disable`: Regresa de modo Privilegiado a modo Usuario.
- `configure terminal`: Entra al modo de configuración global.
- `interface vlan 1`: Entra a la configuración de interfaz.
- `line console 0` / `line vty 0 15`: Entran a la configuración de líneas (consola o acceso remoto).
- `exit`: Retrocede un nivel en la jerarquía de modos.
- `end` o `Ctrl+Z`: Regresa directamente al modo EXEC Privilegiado.
---

# Estructura de la Sintaxis de Comandos
Cada comando consta de la instrucción principal acompañada de **palabras clave** (parámetros fijos del sistema) y **argumentos** (valores definidos por el usuario, como direcciones IP o nombres).

## Convenciones del Manual de Sintaxis
- **Negrita**: Comandos y palabras clave que deben escribirse exactamente como se muestran.
- *Cursiva*: Argumentos donde el usuario asigna el valor específico.
- `[opcional]`: Elementos opcionales entre corchetes.
- `{obligatorio}`: Elementos requeridos entre llaves.
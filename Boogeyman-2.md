# Análisis del Incidente Boogeyman 2

## Resumen Ejecutivo
El presente informe detalla la investigación forense realizada sobre el incidente **Boogeyman 2** de TryHackMe. El compromiso inicial se produjo a través de un correo de *spear-phishing* que contenía un documento de Word malicioso (`Resume_WesleyTaylor.doc`). 

El atacante utilizó macros VBA (Visual Basic for Applications) para descargar y ejecutar un payload de JavaScript de primera etapa, el cual posteriormente descargó un binario malicioso de segunda etapa (`updater.exe`) para establecer una conexión con un servidor C2 y configurar persistencia. La investigación se centró en la extracción de macros y la informática forense de la memoria RAM (Memory Forensics) de la máquina afectada.

## Herramientas Utilizadas

| Categoría | Herramienta | Propósito de Uso |
| :--- | :--- | :--- |
| **Análisis de Macros** | Olevba (Oletools) | Análisis y extracción de macros VBA ocultas dentro de documentos ofimáticos. |
| **Forense de Memoria** | Volatility 3 | Framework avanzado para la disección y análisis de volcados de la memoria RAM (archivos .raw). |
| **Línea de Comandos** | BASH (strings, grep) | Extracción de cadenas de texto y búsqueda de patrones forzados desde volcados de memoria crudos. |

## Comandos de Consola Utilizados

A continuación, se detalla la sintaxis exacta de las herramientas utilizadas para extraer la evidencia:

### Análisis del Documento Malicioso
Extracción del código de la macro VBA para revelar el comportamiento `AutoOpen` y las URL de descarga iniciales:
bash
olevba Resume_WesleyTaylor.doc

Análisis Forense con Volatility 3
Reconstrucción del árbol de procesos para identificar la jerarquía de ejecución del malware:

vol -f WKSTN-2961.raw windows.pstree

Extracción Forzada de Artefactos de Memoria
Ante la volatilidad y sobrescritura de estructuras en la RAM, se utilizó fuerza bruta para encontrar la URL del payload de la segunda etapa:

strings WKSTN-2961.raw | grep -i "boogeymanisback.lol"

Búsqueda de la sintaxis exacta utilizada por el atacante para asegurar persistencia en el sistema infectado:

strings WKSTN-2961.raw | grep -i "schtasks" | grep -i "create"

### Metodología y Hallazgos
La investigación se dividió en fases tácticas de análisis estático y de memoria:

1. Análisis de Documento Ofimático (Stage 1)
Mediante el uso de olevba, se identificó la función maliciosa AutoOpen() en el documento de Word. El script estaba programado para descargar un archivo disfrazado como imagen (update.png) desde el servidor del atacante files.boogeymanisback.lol, guardarlo localmente bajo la ruta C:\ProgramData\update.js y ejecutarlo de forma silenciosa utilizando wscript.exe.

2. Análisis del Árbol de Procesos en RAM
La utilización del plugin windows.pstree de Volatility 3 confirmó la ejecución exitosa de la cadena de ataque. Se observó claramente la jerarquía: el proceso WINWORD.EXE (PID 1124) originó a wscript.exe (PID 4260), el cual a su vez lanzó el binario de segunda etapa, renombrado localmente como updater.exe (PID 6216).

3. Recuperación de Artefactos y Persistencia
Al fallar los escaneos convencionales de Volatility (filescan, cmdline) debido a la naturaleza volátil de la memoria, se utilizó la herramienta strings sobre la imagen cruda:

Conexión C2: Se logró extraer el código fuente del JavaScript alojado en RAM, revelando la URL exacta de la descarga de la segunda etapa (update.exe).

Mecanismo de Persistencia: Se identificó la creación de una tarea programada mediante schtasks para asegurar que el malware se ejecutara automáticamente tras reiniciar el equipo, garantizando el acceso continuo al C2.

Conclusión
La investigación forense de la memoria permitió reconstruir con exactitud la cadena de infección: desde la apertura inicial del documento de Word, pasando por la descarga de scripts evasivos, hasta el establecimiento de persistencia y comunicación de Comando y Control (C2). Las técnicas de extracción forzada demostraron ser vitales cuando los rastros estructurados de la memoria fueron sobrescritos por el sistema operativo.

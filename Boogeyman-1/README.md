# Análisis del Incidente Boogeyman 1

## Resumen Ejecutivo
El presente informe detalla la investigación técnica realizada sobre el incidente de seguridad **Boogeyman 1** de TryHackMe. El vector de ataque inicial consistió en una campaña de *spear-phishing* dirigida a un empleado de la organización. Mediante la ejecución no autorizada de un archivo de acceso directo malicioso (.lnk), el atacante logró establecer persistencia y ejecutar scripts maliciosos en la estación de trabajo comprometida.

Como resultado de la intrusión, el adversario realizó labores de enumeración interna del sistema, accedió a bases de datos locales confidenciales y exfiltró exitosamente un almacén de contraseñas sensible junto con notas corporativas privadas.

## Herramientas Utilizadas
Para el análisis forense digital y la reconstrucción de la cadena de ataque se emplearon las siguientes herramientas:

| Categoría | Herramienta | Propósito de Uso |
| :--- | :--- | :--- |
| **Análisis de Correo** | Thunderbird | Inspección y parseo del archivo de correo malicioso original (.eml). |
| **Análisis de Red** | Wireshark | Inspección de capturas de tráfico de red para identificar comunicaciones salientes. |
| **Decodificación** | CyberChef | Desofuscación y decodificación de payloads codificados en Base64. |
| **Análisis de Logs** | jq | Procesamiento y filtrado estructurado del archivo JSON de registros de PowerShell. |
| **Línea de Comandos** | BASH (strings, grep) | Extracción de cadenas de texto legibles y búsqueda de patrones dentro de artefactos binarios. |

## Comandos de Consola Utilizados

A continuación, se detalla la sintaxis exacta de las utilidades de línea de comandos de Linux (`bash`) y el procesador de JSON (`jq`) empleados durante la investigación para el aislamiento de artefactos:

### Extracción del Archivo ZIP Malicioso
Descompresión del archivo adjunto protegido con la contraseña descubierta mediante ingeniería social en el cuerpo del correo:

bash

unzip nombre_del_archivo.zip

Análisis del Archivo de Acceso Directo (.lnk)
Extracción de cadenas de texto legibles (incluyendo el escaneo de codificación de 16 bits Little-Endian) para revelar el payload de PowerShell ofuscado y saltar la "basura" binaria:

strings -el Invoice_20230103.lnk | grep -i "powershell"

lnkparse Invoice_20230103.lnk

Análisis de Registros de PowerShell (powershell.json)
Filtrado de la estructura JSON para localizar eventos de ejecución relacionados con la herramienta de bases de datos (sq3.exe), permitiendo descubrir el acceso no autorizado al archivo plum.sqlite:

cat powershell.json | jq '.ScriptBlockText | select(type == "string") | select(test("sq3.exe"; "i"))'

Filtrado de eventos para identificar la interacción, preparación y exfiltración de la bóveda de contraseñas de KeePass (.kdbx):

cat powershell.json | jq '.ScriptBlockText | select(type == "string") | select(test("\\.kdbx"; "i"))'


## Metodología y Hallazgos
La investigación se dividió en tres fases consecutivas siguiendo la cadena de destrucción del ataque (*Cyber Kill Chain*):

### 1. Vector de Entrada y Análisis de Correo
Se procedió a la inspección del archivo de correo electrónico `.eml` almacenado mediante la plataforma Thunderbird. Se confirmó la recepción de un mensaje de phishing diseñado para engañar al usuario final, el cual contenía como adjunto un archivo comprimido que alojaba un acceso directo `.lnk` malicioso.

### 2. Extracción y Decodificación del Payload
Mediante el uso de utilidades de la interfaz de comandos de Linux, se analizó la estructura del archivo `.lnk`:
* Se aplicó la herramienta `strings` sobre el archivo de acceso directo para identificar comandos incrustados.
* Se extrajo un bloque de código ofuscado codificado en **Base64**.
* El código fue procesado a través de **CyberChef**, aplicando operaciones de decodificación que revelaron comandos de PowerShell diseñados para contactar la infraestructura de Comando y Control (C2) del atacante y descargar la siguiente fase de ejecución.

### 3. Análisis Forense de Ejecución y Exfiltración
El análisis detallado de los eventos de PowerShell registrados en `powershell.json` mediante consultas personalizadas con `jq` permitió reconstruir las acciones posteriores al compromiso:
* **Enumeración del Sistema:** Se identificó la ejecución del script de auditoría de seguridad `Seatbelt`, utilizado por el atacante para obtener información contextual del host y de la red local.
* **Acceso a Datos Confidenciales:** Se observó la invocación del ejecutable `sq3.exe` para interactuar directamente con la base de datos local `plum.sqlite`, permitiendo la lectura no autorizada de su contenido.
* **Exfiltración de Credenciales:** Se confirmó la localización y posterior exfiltración del archivo de bóveda de contraseñas de la víctima, identificado como `julianne_westcott.kdbx`.

## Conclusión
El incidente compromete la confidencialidad de la estación de trabajo analizada. El vector de entrada por correo electrónico permitió al atacante evasión inicial mediante ingeniería social, logrando la ejecución local de scripts maliciosos. A través de este acceso, el adversario realizó con éxito el reconocimiento del entorno, la extracción de bases de datos internas y el robo de la bóveda principal de credenciales y notas confidenciales del usuario afectado.

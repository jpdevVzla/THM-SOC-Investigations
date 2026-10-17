# Fase 3: Análisis Avanzado de Amenazas, SIEM y Respuesta a Incidentes (Capstone)

En la fase final de la especialización, el objetivo fue consolidar todas las habilidades técnicas previamente adquiridas para operar a nivel empresarial. Aprendí a utilizar plataformas de gestión centralizada (SIEM), a enriquecer mis investigaciones con inteligencia de amenazas y, finalmente, a resolver incidentes críticos complejos de principio a fin simulando un entorno de producción real.

A continuación, se detallan las competencias adquiridas en estos módulos finales:

## 1. Malware Concepts for SOC
En este módulo, aprendí a identificar tipos comunes de malware, comprender su propósito y analizar archivos[cite: 67].
* **Competencias clave:**
  * Triaje inicial y clasificación de familias de malware (Ransomware, Troyanos, Info Stealers, etc.).
  * Comprensión profunda de la tendencia actual de ciberataques: por qué los ataques *Living off the Land* (LOTL) se están volviendo cada vez más comunes[cite: 67], utilizando binarios legítimos del sistema (como PowerShell o WMI) para evadir las detecciones de los antivirus tradicionales.

## 2. Threat Analysis Tools
Adquirí habilidades prácticas en el uso de inteligencia de amenazas, herramientas de enriquecimiento y flujos de trabajo de análisis para fortalecer mis capacidades dentro del SOC[cite: 67].
* **Competencias clave:**
  * Uso de plataformas de *Threat Intelligence* (Inteligencia de Amenazas) para investigar la reputación de Indicadores de Compromiso (IoCs) como direcciones IP, dominios y hashes de archivos maliciosos.
  * Integración de contexto adicional a las alertas de seguridad para acelerar el proceso de toma de decisiones durante un incidente.

## 3. SIEM Triage for SOC
Exploré cómo las soluciones SIEM (Gestión de Eventos e Información de Seguridad) ayudan a detectar signos tempranos de ataques, investigar alertas del SOC y correlacionar registros (logs) para construir una línea de tiempo del incidente[cite: 67].
* **Competencias clave:**
  * Uso operativo de plataformas SIEM líderes en la industria (Elastic/Kibana y Splunk) para buscar, filtrar y analizar grandes volúmenes de datos.
  * Reconstrucción paso a paso de las acciones del atacante cruzando telemetría de red, eventos de Windows (Sysmon) y registros de aplicaciones.

## 4. SOC Level 1 Capstone Challenges
Este fue el examen final y la demostración definitiva de mis habilidades. Tuve que investigar incidentes críticos y aplicar todas las destrezas necesarias para ser un analista SOC efectivo mientras manejaba diversos artefactos digitales[cite: 67].
* **Investigaciones destacadas resueltas:**
  * **Tempest:** Investigación forense de una estación de trabajo afectada por una cadena de ataque completa, rastreando desde el acceso inicial hasta la ejecución de payloads.
  * **Boogeyman 1 & 2:** Resolví intrusiones complejas iniciadas por *spear-phishing*. El análisis requirió la extracción manual de payloads ofuscados en Base64, el filtrado avanzado de logs de PowerShell usando `jq`, la desofuscación de macros VBA con `olevba` y el uso intensivo de **Volatility 3** para el análisis forense de la memoria RAM, descubriendo mecanismos de persistencia (tareas programadas) y tráfico de Comando y Control (C2).

---
**Conclusión General de la Especialización:**
Completar la ruta "SOC Level 1" me ha dotado de un marco de trabajo analítico robusto. No solo entiendo la teoría detrás de los ciberataques, sino que poseo la experiencia práctica (hands-on) para interceptar telemetría de red, diseccionar malware a nivel de endpoint, orquestar investigaciones en plataformas SIEM y extraer evidencia irrefutable de la memoria RAM. Estoy completamente capacitado para aportar valor inmediato en operaciones de defensa cibernética y respuesta a incidentes.

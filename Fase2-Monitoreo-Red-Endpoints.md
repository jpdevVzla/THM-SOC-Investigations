# Fase 2: Monitoreo de Redes, Endpoints y Seguridad Web

En esta segunda etapa de la especialización, el enfoque se centró en la visibilidad profunda de la infraestructura tecnológica. Desarrollé habilidades analíticas para inspeccionar el tráfico de red paquete por paquete, auditar aplicaciones web y monitorear a bajo nivel los sistemas operativos Windows y Linux para cazar amenazas que lograron evadir las defensas perimetrales.

A continuación, se detallan las competencias técnicas adquiridas por cada módulo completado:

## 1. Network Traffic Analysis
Este módulo me proporcionó los fundamentos técnicos del análisis de tráfico de red, permitiéndome obtener experiencia práctica en la detección de diversos tipos de ataques a través de herramientas de captura de paquetes[cite: 66].
* **Competencias clave:** 
  * Dominio avanzado de **Wireshark** y **Tshark**.
  * Construcción de filtros BPF (Berkeley Packet Filter) complejos para aislar anomalías en protocolos específicos (TCP/IP, HTTP, DNS).
  * Seguimiento de flujos de comunicación (TCP Streams) y extracción de payloads o archivos maliciosos interceptados en la red.

## 2. Network Security Monitoring
Profundicé en los fundamentos clave de la seguridad de red y la importancia crítica de monitorear los perímetros corporativos[cite: 66]. 
* **Competencias clave:**
  * Análisis de logs y tráfico de red para rastrear huellas de ataques basados en red, tales como interceptación de comunicaciones (MITM - Man-In-The-Middle), tácticas de descubrimiento de red y exfiltración de datos confidenciales[cite: 66].
  * Familiaridad con Sistemas de Detección de Intrusos (NIDS) y la correlación de telemetría de red para identificar patrones de Comandos y Control (C2).

## 3. Web Security Monitoring
La infraestructura web es el servicio más expuesto de cualquier organización. En este módulo, aprendí a proteger y monitorear el ecosistema web a través de laboratorios orientados al SOC y escenarios del mundo real[cite: 66].
* **Competencias clave:**
  * Análisis de logs de acceso y errores de servidores web (Apache/Nginx).
  * Identificación y triaje de ataques a nivel aplicativo (Capa 7), incluyendo Inyecciones SQL (SQLi), Cross-Site Scripting (XSS), Local File Inclusion (LFI), Directory Traversal y ataques de fuerza bruta contra paneles de autenticación.

## 4. Windows Security Monitoring
Adquirí un entendimiento profundo sobre cómo funciona el registro de eventos en Windows y cómo utilizarlo estratégicamente para detectar ciberataques comunes mediante ejemplos reales y laboratorios prácticos de detección de amenazas[cite: 66].
* **Competencias clave:**
  * Dominio del Visor de Eventos de Windows y uso avanzado de **Sysmon** para telemetría granular.
  * Identificación de *Event IDs* críticos para la investigación de incidentes (ej. 4688 Creación de procesos, 4624/4625 Inicios de sesión, 4720 Creación de cuentas de usuario).
  * Detección de técnicas de *Living off the Land* (LOLBINs), ejecución de malware, escalada de privilegios y creación de puertas traseras a nivel de sistema operativo.

## 5. Linux Security Monitoring
Estudié el ecosistema de registros en Linux y aprendí a utilizar los logs del sistema para detectar vectores de ataque comunes en entornos basados en Unix, apoyado en laboratorios prácticos de detección de amenazas[cite: 66].
* **Competencias clave:**
  * Auditoría y correlación de archivos de registro críticos (`/var/log/syslog`, `auth.log`, `bash_history`).
  * Uso de herramientas nativas de Linux y comandos forenses (`grep`, `awk`, `sed`) para rastrear accesos no autorizados por SSH.
  * Detección de persistencia mediante trabajos Cron (`cron jobs`) maliciosos, escalada de privilegios vía `sudo`, y monitoreo con el demonio `auditd`.

---
**Conclusión de la Fase 2:**
Con la finalización de esta etapa, mi capacidad de análisis dejó de ser puramente conceptual para volverse altamente operativa. Ahora poseo la competencia técnica para rastrear a un adversario en múltiples capas de la infraestructura: desde el cable de red (captura de paquetes) y el servidor web perimetral, hasta los registros más profundos del sistema operativo (Windows/Linux).

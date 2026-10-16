# THM-SOC-Investigations
Reportes de análisis de incidentes, triage de malware y ciberseguridad en TryHackMe.

# Portafolio de Ciberseguridad: Especialización SOC Nivel 1
**Autor:** Ing. Juan Vicente Muñoz Rodriguez

## Resumen Ejecutivo
He completado exitosamente la ruta de especialización defensiva "SOC Level 1" (Analista de Centro de Operaciones de Seguridad), cubriendo más de 14 módulos técnicos intensivos. Esta formación 100% práctica valida mis capacidades como Ingeniero de Sistemas para monitorear, detectar, analizar y responder a incidentes de seguridad cibernética en entornos corporativos modernos.

Este conjunto de habilidades me permite ofrecer servicios integrales de consultoría en TI y ciberseguridad, garantizando la protección de activos digitales, la investigación forense de vulneraciones y la respuesta rápida ante amenazas avanzadas.

## Competencias Técnicas Adquiridas
A lo largo de las investigaciones y laboratorios, desarrollé experiencia práctica en las siguientes áreas operativas:

### 1. Monitoreo y Análisis de Redes (Network Security Monitoring)
* Análisis profundo de tráfico de red y captura de paquetes (PCAP) utilizando **Wireshark** y **Tshark**.
* Detección proactiva de exfiltración de datos, ataques Man-In-The-Middle (MITM) y comunicaciones de Comando y Control (C2).

### 2. Gestión de Eventos e Información de Seguridad (SIEM)
* Correlación de logs y triaje de alertas utilizando soluciones empresariales líderes como **Elastic (ELK Stack)** y **Splunk**.
* Creación de consultas estructuradas para aislar eventos de seguridad críticos y reducir la fatiga por falsos positivos.

### 3. Seguridad de Endpoints (Windows & Linux)
* Monitoreo avanzado de eventos del sistema operativo utilizando **Sysmon** y auditoría nativa de Windows/Linux.
* Detección de escalada de privilegios, mecanismos de persistencia, ejecución de binarios maliciosos (LOLBINs) y técnicas de evasión.

### 4. Análisis de Malware e Informática Forense
* Análisis estático y extracción de macros maliciosas (VBA) de documentos ofimáticos mediante **Olevba/Oletools**.
* Informática forense de memoria RAM (Memory Forensics) utilizando **Volatility 3** para rastrear jerarquías de procesos, recuperar artefactos volátiles y descifrar payloads.
* Desofuscación de payloads y scripts codificados (Base64, Hex) mediante **CyberChef** y herramientas de consola (`strings`, `grep`, `jq`).

### 5. Defensa contra Phishing y Threat Intelligence
* Inspección minuciosa de cabeceras de correo electrónico, identificación de suplantación de identidad (Spoofing) y análisis de archivos adjuntos armados.

## Investigaciones de Incidentes Destacadas (Capstone Challenges)
Como prueba final de mis capacidades, he resuelto de manera autónoma escenarios de ataques reales que abarcaron la cadena de destrucción completa (*Cyber Kill Chain*):

* **Incidente Tempest:** Investigación de una intrusión completa a través del rastreo de tráfico malicioso, exfiltración de datos confidenciales y análisis profundo de logs del sistema.
* **Incidente Boogeyman 1:** Triaje de malware, análisis de campaña de spear-phishing y uso avanzado del procesador JSON (`jq`) para rastrear la ejecución de herramientas de enumeración y el robo de una bóveda de contraseñas.
* **Incidente Boogeyman 2:** Análisis forense avanzado de memoria RAM para reconstruir la ejecución de un payload ofuscado en JavaScript, localizando mecanismos de persistencia mediante tareas programadas y recuperando binarios inyectados.

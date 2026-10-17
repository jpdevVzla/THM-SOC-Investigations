# Fase 1: Fundamentos de Operaciones de Seguridad (SOC) y Análisis de Amenazas

En esta primera etapa de la especialización **SOC Level 1**, desarrollé y consolidé las bases operativas, metodológicas y tecnológicas necesarias para operar dentro de un Centro de Operaciones de Seguridad (SOC) moderno. El enfoque principal fue dominar la arquitectura defensiva, el triaje de alertas y el análisis técnico de vectores de ataque iniciales, como el phishing.

A continuación, se detallan las competencias técnicas y analíticas adquiridas por cada módulo completado:

## 1. Blue Team Introduction
Este módulo sentó las bases de la seguridad defensiva. Comprendí la estructura organizativa de un SOC, sus funciones críticas y cómo se integra el "Blue Team" para proteger los activos de la información.
* **Competencias clave:** Identificación de roles dentro de un SOC (Tier 1 Triage, Tier 2 Incident Response, Tier 3 Threat Hunting), comprensión del ciclo de vida de la respuesta a incidentes y métricas clave operativas (MTTD, MTTR).

## 2. SOC Team Internals
Me enfoqué en el trabajo diario de un analista de seguridad, dominando los flujos de trabajo para la gestión de incidentes.
* **Competencias clave:** 
  * **Triaje de alertas:** Evaluación inicial de eventos de seguridad para distinguir entre falsos positivos y amenazas reales.
  * **Clasificación y Escalamiento:** Asignación de niveles de severidad a los incidentes y aplicación de protocolos de escalamiento hacia ingenieros de nivel superior (Tier 2/3) proporcionando contexto técnico accionable.

## 3. Core SOC Solutions
Obtuve experiencia práctica y teórica sobre la "tríada" de herramientas fundamentales que potencian la visibilidad y respuesta en una red corporativa.
* **Competencias clave:**
  * **SIEM (Security Information and Event Management):** Comprensión de la ingesta de logs, normalización de datos y correlación de eventos para la detección de anomalías.
  * **EDR (Endpoint Detection and Response):** Análisis de telemetría a nivel de host (procesos, memoria, registro) para contener amenazas directamente en los dispositivos.
  * **SOAR (Security Orchestration, Automation, and Response):** Integración de playbooks automatizados para acelerar la respuesta a incidentes repetitivos y reducir la fatiga de alertas.

## 4. Cyber Defence Frameworks
El análisis de ciberseguridad requiere un lenguaje estandarizado. En este módulo, aprendí a perfilar adversarios y a mapear sus comportamientos utilizando los marcos de inteligencia de amenazas más respetados de la industria.
* **Competencias clave:**
  * **MITRE ATT&CK:** Mapeo de Tácticas, Técnicas y Procedimientos (TTPs) utilizados por actores de amenazas avanzados (APTs) para mejorar las reglas de detección.
  * **Cyber Kill Chain (Lockheed Martin):** Análisis de las fases de un ciberataque (desde el reconocimiento hasta la exfiltración) para identificar oportunidades de interrupción (choke points).
  * **The Pyramid of Pain:** Comprensión de la dificultad que representa para un atacante cambiar ciertos Indicadores de Compromiso (IoCs). Evolución del análisis desde simples hashes y direcciones IP, hasta el bloqueo de herramientas y TTPs.

## 5. Phishing Analysis
El phishing sigue siendo el vector de acceso inicial número uno. Este módulo fue netamente práctico, enfocado en diseccionar campañas de correo electrónico malicioso y neutralizar la amenaza antes de la ejecución del payload.
* **Competencias clave:**
  * **Análisis de Cabeceras (Email Headers):** Inspección del código fuente del correo para rastrear la IP de origen, servidores de retransmisión (relays) y Return-Paths.
  * **Autenticación de Correo:** Verificación de registros **SPF** (Sender Policy Framework), **DKIM** (DomainKeys Identified Mail) y **DMARC** para detectar suplantación de identidad (Spoofing).
  * **Extracción de Artefactos:** Descarga segura de archivos adjuntos (.eml, .msg) y extracción de URLs maliciosas.
  * **Defanging y OSINT:** Técnicas de "desarmado" de enlaces (ej. `hxxp[://]malicioso[.]com`) para documentación segura, y uso de inteligencia de fuentes abiertas (VirusTotal, URL2PNG, Cisco Talos) para verificar la reputación de dominios y hashes sin interactuar con la infraestructura del atacante.

---
**Conclusión de la Fase 1:**
Esta etapa inicial me proporcionó un marco de trabajo estructurado. Ahora poseo la capacidad de interceptar alertas, mapear el comportamiento del atacante contra frameworks estándar de la industria y realizar autopsias técnicas de vectores de ataque de ingeniería social para proteger el perímetro corporativo.

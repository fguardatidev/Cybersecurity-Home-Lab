# Cybersecurity Home Lab

Laboratorio personal de ciberseguridad orientado al aprendizaje práctico de detección, monitoreo y análisis de eventos de seguridad.

El objetivo de este proyecto es desarrollar y documentar habilidades técnicas aplicables a distintas áreas de ciberseguridad, especialmente operaciones de seguridad, análisis de incidentes y seguridad de infraestructura.

## Entorno de laboratorio

- **Sistema operativo:** Kali Linux
- **Virtualización:** VirtualBox
- **Recursos:** 2 vCPU, 4 GB RAM
- **Herramientas:** Suricata IDS, OpenSSH, tcpdump, jq y Linux CLI

Todos los ejercicios se realizan en un entorno controlado y autorizado.

## Ejercicios

### 01 — HTTP Traffic Detection

Configuración de una regla personalizada de Suricata para identificar una solicitud HTTP específica.

**Actividades:**
- Generación y captura de tráfico HTTP.
- Configuración de reglas de detección.
- Análisis de alertas de Suricata.
- Correlación de eventos mediante logs JSON.
- Documentación y clasificación de la actividad.

[Ver ejercicio 01](01-HTTP-Detection/README.md)

### 02 — SSH Authentication Analysis

Análisis de múltiples intentos fallidos de autenticación contra un servidor SSH de laboratorio.

**Actividades:**
- Configuración de un servidor OpenSSH local.
- Generación controlada de autenticaciones fallidas.
- Recolección y análisis de logs.
- Evaluación de frecuencia y origen de los intentos.
- Clasificación de eventos y elaboración de conclusiones.

[Ver ejercicio 02](02-SSH-Authentication/README.md)

## Metodología

Los ejercicios siguen un proceso de investigación:

1. Preparación del entorno.
2. Generación de eventos de prueba.
3. Recolección de evidencias.
4. Análisis técnico.
5. Evaluación de posibles amenazas.
6. Documentación de resultados.

## Objetivo profesional

Este repositorio forma parte de mi formación práctica en ciberseguridad y busca demostrar conocimientos técnicos, capacidad de análisis y documentación de eventos de seguridad.

Los escenarios son simulaciones controladas y no representan incidentes reales en entornos productivos.

# Caso 001 — HTTP Traffic Detection

## Objetivo

Implementar una regla personalizada de Suricata IDS para detectar solicitudes HTTP específicas y analizar los eventos generados.

## Herramientas utilizadas

- Kali Linux
- Suricata IDS
- tcpdump
- curl
- jq
- Python HTTP Server

## Procedimiento

1. Se configuró un servidor HTTP local en el puerto 8000.
2. Se creó una regla de detección personalizada en Suricata.
3. Se generó una solicitud HTTP hacia `/soc-test-alert`.
4. Se capturó el tráfico utilizando tcpdump.
5. Se procesó la captura con Suricata.
6. Se analizaron los registros `fast.log` y `eve.json`.

## Evidencia obtenida

Suricata generó una alerta con los siguientes datos:

| Campo                 | Valor           |
|-----------------------|-----------------|
| Signature ID          | 1000001         |
| IP origen             | 127.0.0.1        |
| IP destino            | 127.0.0.1       |
| Puerto destino        | 8000            |
| Método HTTP           | GET             |
| URI                   | /soc-test-alert |
| Respuesta HTTP        | 404             |
| Severidad de la regla | 3               |

Se correlacionaron los eventos de tipo `alert` y `http` mediante el identificador `flow_id`.

## Análisis

La alerta fue generada porque la solicitud HTTP coincidió con la regla personalizada.

El código HTTP 404 indica que el recurso solicitado no fue encontrado, no que Suricata haya bloqueado la comunicación.

## Conclusión

Se confirmó que la actividad correspondía a una prueba autorizada.

**Clasificación:** actividad benigna de laboratorio.

**Escalamiento:** no requerido.

## Aprendizajes

- Configuración de reglas IDS.
- Captura y análisis de tráfico HTTP.
- Interpretación de alertas.
- Correlación de eventos.
- Diferenciación entre una detección y un incidente confirmado.

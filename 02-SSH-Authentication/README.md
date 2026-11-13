# Caso 002 — SSH Authentication Analysis

## Objetivo

Analizar múltiples intentos fallidos de autenticación SSH, identificar patrones temporales y evaluar si la actividad representa una posible amenaza.

## Herramientas utilizadas

- Kali Linux
- OpenSSH Server
- SSH Client
- Linux CLI
- grep
- moreutils (ts)

## Procedimiento

1. Se configuró un servidor SSH de laboratorio en `127.0.0.1:2222`.
2. Se habilitó el registro detallado de eventos.
3. Se generaron cinco intentos fallidos de autenticación.
4. Se recolectaron los eventos en un archivo de logs.
5. Se incorporaron timestamps para realizar un análisis temporal.

## Evidencia obtenida

| Campo | Resultado |
|---|---|
| Intentos fallidos | 5 |
| IP de origen | `127.0.0.1` |
| Usuario objetivo | `kali` |
| Puerto de destino | `2222` |
| Primer intento | `19:02:08` |
| Último intento | `19:03:53` |
| Intervalo total | 105 segundos |

Todos los intentos provinieron de la misma dirección IP y utilizaron diferentes puertos de origen.

## Análisis

Se detectaron cinco intentos fallidos contra una misma cuenta en un intervalo de 105 segundos.

Aunque este comportamiento puede ser relevante para detectar intentos de fuerza bruta, la cantidad de eventos por sí sola no permite confirmar una actividad maliciosa.

En una investigación real sería necesario correlacionar esta información con autenticaciones exitosas, comportamiento histórico, origen de las conexiones y contexto del usuario.

## Conclusión

Se verificó que las autenticaciones fallidas fueron generadas manualmente en un entorno de laboratorio autorizado.

**Clasificación:** actividad benigna de laboratorio.

**Escalamiento:** no requerido.

## Aprendizajes

- Configuración básica de OpenSSH.
- Análisis de registros de autenticación.
- Identificación de IP y puertos de origen.
- Análisis temporal de eventos.
- Evaluación de indicadores de posibles ataques de fuerza bruta.
- Documentación de hallazgos de seguridad.

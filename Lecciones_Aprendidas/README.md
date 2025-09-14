# Caso: Error de conexión intermitente con la base de datos

**Fecha:** 2025-09-11  
**Proyecto:** Plataforma de Pagos

## Problema
La aplicación perdía conexión con la BD bajo alta carga.

## Causa
Pool de conexiones configurado con `max=10`, insuficiente en picos.

## Solución aplicada
- Incrementar pool a `max=50`.
- Añadir métricas de latencia en Grafana.
- Alertas en Slack para saturación del pool.

## Lección aprendida
Siempre realizar pruebas de carga que simulen el tráfico pico y validar configuración de pool y timeouts.


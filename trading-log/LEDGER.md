# Reto 100 € — Paper trading (Alpaca)

- **Periodo:** 2026-11-18 → 2026-12-02 (cierre de mercado)
- **Capital inicial:** 100 € ≈ **115,00 $** (tipo aproximado 1 € = 1,15 $)
- **Cuenta:** Alpaca *paper* (dinero simulado). La cuenta tiene 100.000 $, pero solo se usan los 115 $ del reto.
- **Etiqueta de órdenes:** `client_order_id` empieza por `eur100-`

## Reglas
1. Riesgo máximo por operación: **2 % del capital del reto** (~2,30 $). Toda entrada lleva stop-loss.
2. Exposición total ≤ capital del reto (sin margen, sin cortos, sin opciones).
3. Preferir órdenes bracket (entrada + stop + objetivo) con acciones enteras; ratio objetivo/riesgo ≥ 2:1.
4. Valores líquidos (grandes capitalizaciones / ETFs), nada de *penny stocks* ni warrants.
5. Si el capital cae a 100 $ o menos, se reduce el riesgo a 1 % por operación.
6. Revisión dos veces por día de mercado (12:41 y 15:41 hora de Nueva York).
7. El 2026-12-02 a las 15:41 ET se cierran todas las posiciones del reto y se hace el informe final.

## Operaciones

| # | Fecha (ET) | Símbolo | Lado | Cant. | Entrada | Stop | Objetivo | Salida | P/L $ | Estado | Motivo |
|---|-----------|---------|------|------:|--------:|-----:|---------:|-------:|------:|--------|--------|
| 1 | 2026-11-18 11:46 | T | Long | 4 | 22,08 | 21,50 | 23,10 | — | — | Abierta | Fuerza relativa: mínimos crecientes desde 20,85 mientras SPY cae ~6,5 %; soporte 21,50-21,65. Riesgo 2,32 $ / objetivo +4,08 $ |

## Estado del capital

| Fecha | Efectivo reto $ | Valor posiciones $ | Total $ | Total € (aprox.) | Notas |
|-------|---------------:|-------------------:|--------:|-----------------:|-------|
| 2026-11-18 | 26,68 | 88,32 | 115,00 | 100,00 | Apertura T |

## Diario
- **2026-11-18:** Mercado en corrección (SPY 779 → 728 en 3 semanas). Se evita perseguir rebotes en valores bajistas (INTC, SOFI, F, BAC). Entrada defensiva en T por fuerza relativa.

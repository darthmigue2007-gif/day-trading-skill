# Reto 100 € — Paper trading (Alpaca)

- **Cuenta:** Alpaca *paper* (dinero simulado). La cuenta tiene 100.000 $, pero cada fase usa solo su capital de reto.
- **Capital por fase:** 100 € ≈ **115,00 $** (tipo aproximado 1 € = 1,15 $). Cada fase **arranca de cero con 115 $** para que los resultados sean comparables.
- **Etiqueta de órdenes:** `client_order_id` = `eur100-F<fase>-SIMBOLO-AAAAMMDD-n` (la operación #1 usa el formato antiguo `eur100-T-20261118-1` y pertenece a la Fase 1).
- **Revisiones:** dos por día de mercado (12:41 y 15:41 hora de Nueva York).

## Fases (una estrategia cada 2 semanas)

| Fase | Periodo | Estrategia | Riesgo |
|------|---------|-----------|--------|
| 1 | 2026-11-18 → 2026-12-02 | **Medir ventaja** | 2 % del capital por operación, stop obligatorio, ratio ≥ 2:1, acciones/ETFs líquidos sin apalancamiento |
| 2 | 2026-12-03 → 2026-12-16 | **Agresivo controlado** | 5 % por operación, stop obligatorio, ratio ≥ 2:1; se permiten ETFs apalancados (TQQQ, SOXL, etc.) y acciones de alto momentum |
| 3 | 2026-12-17 → 2026-12-31 | **Todo a por los 1000 €** | Sin límite de riesgo por operación: posiciones concentradas, opciones (incluidas de vencimiento corto) y ETFs 3x. Solo en paper. El resultado **no** sirve como prueba para dinero real |

**Cierre de fase:** en la revisión de las 15:41 ET del último día de cada fase se cierran todas las posiciones de la fase y se escribe su resumen. La fase siguiente empieza en la revisión de las 12:41 ET de su primer día.

### Reglas comunes
1. Exposición total ≤ capital de la fase (sin margen, sin cortos).
2. Valores líquidos; nada de *penny stocks*, warrants ni derechos.
3. Fases 1 y 2: nunca se baja un stop; cuando la posición gana ≥ 1R, el stop sube a break-even.
4. Cada operación se anota con su motivo.

## Criterio de evaluación (por fase)
- Resultado neto en $ y €, drawdown máximo, nº de operaciones, % de aciertos, R medio.
- Cumplimiento de las reglas de la fase.
- Al final (2026-12-31) se comparan las tres fases. Seis semanas siguen siendo una muestra pequeña: un buen resultado justificaría seguir en paper más tiempo antes de pasar a dinero real.

---

## Fase 1 — Medir ventaja (2026-11-18 → 2026-12-02)

### Operaciones

| # | Fecha (ET) | Símbolo | Lado | Cant. | Entrada | Stop | Objetivo | Salida | P/L $ | Estado | Motivo |
|---|-----------|---------|------|------:|--------:|-----:|---------:|-------:|------:|--------|--------|
| 1 | 2026-11-18 11:46 | T | Long | 4 | 22,08 | 21,50 | 23,10 | — | — | Abierta | Fuerza relativa: mínimos crecientes desde 20,85 mientras SPY cae ~6,5 %; soporte 21,50-21,65. Riesgo 2,32 $ / objetivo +4,08 $ |

### Estado del capital

| Fecha | Efectivo $ | Valor posiciones $ | Total $ | Total € (aprox.) | Notas |
|-------|-----------:|-------------------:|--------:|-----------------:|-------|
| 2026-11-18 | 26,68 | 88,32 | 115,00 | 100,00 | Apertura T |
| 2026-11-18 12:41 | 26,68 | 88,36 | 115,04 | 100,03 | Revisión: T 22,09, sin cambios |
| 2026-11-18 15:41 | 26,68 | 87,88 | 114,56 | 99,62 | Revisión: T 21,97, sin cambios |

### Diario
- **2026-11-18:** Mercado en corrección (SPY 779 → 728 en 3 semanas). Se evita perseguir rebotes en valores bajistas (INTC, SOFI, F, BAC). Entrada defensiva en T por fuerza relativa.
- **2026-11-18 12:41 ET:** T 22,09 (+0,04 $); stop 21,50 y objetivo 23,10 activos, lejos de +1R (22,66) para mover a break-even. SPY rebota ligeramente (731). Efectivo libre 26,68 $: insuficiente para otra entrada con stop técnico y tamaño útil; no se opera.
- **2026-11-18 15:41 ET:** T cede a 21,97 (-0,44 $, -0,2R) junto al mercado (SPY 730,6); sigue por encima del soporte 21,90 del día y del stop 21,50. Se mantiene el plan sin tocar órdenes. Sin nuevas entradas.

---

## Fase 2 — Agresivo controlado (2026-12-03 → 2026-12-16)
_Pendiente._

---

## Fase 3 — Todo a por los 1000 € (2026-12-17 → 2026-12-31)
_Pendiente._

---

## Comparativa final
_Pendiente (2026-12-31)._

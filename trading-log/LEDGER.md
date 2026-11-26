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
| 1 | 2026-11-18 11:46 | T | Long | 4 | 22,08 | 21,50 → **22,08** (BE, 20-nov) | 23,10 | 22,19 (23-nov 09:35, stop) | **+0,44** (+0,19R) | Cerrada | Fuerza relativa: mínimos crecientes desde 20,85 mientras SPY cae ~6,5 %; soporte 21,50-21,65. Riesgo 2,32 $ / objetivo +4,08 $ |
| 2 | 2026-11-24 09:34 | F | Long | 8 | 11,5875 | 11,38 → **11,59** (BE, 24-nov) | 12,20 | 12,20 (25-nov 14:10, objetivo) | **+4,90** (+2,95R) | Cerrada | Giro del mercado: SPY defiende 713,6 y cierra +4,9 % cerca de máximos; F rebota desde 11,135 con mínimo más alto y cierra en máximos del día. Stop bajo el mínimo del día (11,39). Riesgo 2,24 $ (1,9 %) / objetivo +4,32 $ (1,9R; resistencia previa 12,2-12,3) |

### Estado del capital

| Fecha | Efectivo $ | Valor posiciones $ | Total $ | Total € (aprox.) | Notas |
|-------|-----------:|-------------------:|--------:|-----------------:|-------|
| 2026-11-18 | 26,68 | 88,32 | 115,00 | 100,00 | Apertura T |
| 2026-11-18 12:41 | 26,68 | 88,36 | 115,04 | 100,03 | Revisión: T 22,09, sin cambios |
| 2026-11-18 15:41 | 26,68 | 87,88 | 114,56 | 99,62 | Revisión: T 21,97, sin cambios |
| 2026-11-19 12:41 | 26,68 | 86,86 | 113,54 | 98,73 | Revisión: T 21,71, sin cambios |
| 2026-11-19 15:41 | 26,68 | 86,86 | 113,54 | 98,73 | Revisión: T 21,72, sin cambios |
| 2026-11-20 12:41 | 26,68 | 90,56 | 117,24 | 101,95 | T 22,64; stop a break-even |
| 2026-11-20 15:41 | 26,68 | 89,40 | 116,08 | 100,94 | T 22,35, sin cambios |
| 2026-11-23 12:41 | 115,44 | 0,00 | 115,44 | 100,38 | T cerrada por stop BE (+0,44 $); 100 % en efectivo |
| 2026-11-23 15:41 | 115,44 | 0,00 | 115,44 | 100,38 | Orden bracket F enviada (pendiente) |
| 2026-11-24 12:41 | 22,74 | 95,76 | 118,50 | 103,04 | F 11,97 (+3,06 $); stop a break-even |
| 2026-11-24 15:41 | 22,74 | 95,16 | 117,90 | 102,52 | F 11,90 (+2,46 $), sin cambios |
| 2026-11-26 | 120,28 | 0,00 | 120,28 | 104,59 | F cerrada en objetivo (+4,90 $). Neto tras comisiones regulatorias (~0,06 $), según saldo de Alpaca: +5,28 $ |

### Diario
- **2026-11-18:** Mercado en corrección (SPY 779 → 728 en 3 semanas). Se evita perseguir rebotes en valores bajistas (INTC, SOFI, F, BAC). Entrada defensiva en T por fuerza relativa.
- **2026-11-18 12:41 ET:** T 22,09 (+0,04 $); stop 21,50 y objetivo 23,10 activos, lejos de +1R (22,66) para mover a break-even. SPY rebota ligeramente (731). Efectivo libre 26,68 $: insuficiente para otra entrada con stop técnico y tamaño útil; no se opera.
- **2026-11-18 15:41 ET:** T cede a 21,97 (-0,44 $, -0,2R) junto al mercado (SPY 730,6); sigue por encima del soporte 21,90 del día y del stop 21,50. Se mantiene el plan sin tocar órdenes. Sin nuevas entradas.
- **2026-11-19 12:41 ET:** Sesión bajista con mucha amplitud: SPY abrió 737,5, cayó a 717,5 y cotiza 723 (-1 %). T 21,71 (-1,46 $, -0,63R); mínimo del día 21,53, a 3 céntimos del stop 21,50. No se toca el stop (la regla prohíbe bajarlo y el soporte sigue siendo 21,50-21,65). Con el mercado en caída no hay setups largos de calidad; no se opera con el efectivo libre.
- **2026-11-19 15:41 ET:** SPY sigue cayendo hasta 717 (-1,8 % en el día, mínimo 715,7; ~-8 % desde máximos de octubre). T aguanta en 21,72, con fuerza relativa clara frente al índice; el soporte 21,53 resistió. Posición y órdenes sin cambios. Sin nuevas entradas: no se compran caídas de un mercado en tendencia bajista.
- **2026-11-20 12:41 ET:** T sube +3,6 % en el día hasta 22,64 (máx. 22,68), alcanzando +1R (22,66) mientras SPY se desploma a 700 (-2,2 %, ~-10 % desde máximos): fuerza relativa confirmada. Stop subido de 21,50 a 22,08 (break-even; nueva orden 7801a97b). La operación ya no puede perder. Objetivo 23,10 intacto. Sin nuevas entradas con el índice en caída libre.
- **2026-11-20 15:41 ET:** SPY cierra la semana en mínimos (690,8, -3,5 % en el día; ~-11 % desde máximos). T recorta a 22,35 pero mantiene +2,3 % en el día. Stop en break-even (22,08) y objetivo 23,10 activos durante el fin de semana. Riesgo de gap bajista el lunes: si abre por debajo de 22,08, el stop ejecutará a mercado con una pequeña pérdida posible. Sin nuevas entradas.
- **2026-11-23 12:41 ET:** El stop break-even de T se ejecutó a las 09:35 ET a 22,19 (por encima del stop 22,08). **Operación #1 cerrada: +0,44 $ (+0,19R).** SPY abrió con gap alcista de +4,9 % (690,7 → 724,3) y rebota a 721,9 tras tocar 713,6; T queda rezagado (22,12) al rotar el dinero de defensivos a riesgo. Capital de la fase: 115,44 $ en efectivo. No se entra: comprar tras un gap de +5 % en un mercado aún bajista no ofrece stop técnico cercano ni ratio 2:1 limpio. Se esperará a ver si el rebote forma un mínimo más alto (pullback que respete 713) para buscar entrada.
- **2026-11-23 15:41 ET:** SPY consolida el giro: cierra 724,7 tras defender 713,6 (rango alto del día). Se prepara la operación #2 en F (bracket 8 acc., límite 11,66, stop 11,38, objetivo 12,20). **Incidencia:** el proceso se reinició durante la revisión y la orden llegó a Alpaca a las 17:06 ET, con el mercado ya cerrado; queda en espera para la apertura del 24-nov. Si F abre con hueco bajista por debajo de 11,38, la entrada y el stop se ejecutarían casi a la vez con una pérdida pequeña; si abre por encima de 11,66, no entra. Se revisará a las 12:41 ET.
- **2026-11-24 12:41 ET:** F entró en la apertura a 11,5875 (mejor que el límite 11,66). R = 0,2075 $/acc. Sube a 11,97 (+3,06 $, +1,8R) con el mercado plano (SPY 719,8, -0,4 %): fuerza relativa. Stop subido de 11,38 a 11,59 (break-even; nueva orden 4d544576). Objetivo 12,20 intacto. Efectivo libre 22,74 $: insuficiente para otra entrada útil.
- **2026-11-24 15:41 ET:** F cierra cerca de máximos (11,90; máx. 11,995) mientras SPY cede a 716,5 (-0,8 %). Stop BE 11,59 y objetivo 12,20 activos. Sin cambios ni nuevas entradas.
- **2026-11-25 12:41 ET:** ⚠️ Revisión no realizada: el conector de Alpaca rechazó la sesión (requiere volver a iniciar sesión). No se pudo consultar ni operar. La posición F sigue protegida en el servidor de Alpaca con stop 11,59 (break-even) y objetivo 12,20, que se ejecutan aunque no haya revisión.
- **2026-11-25 15:41 ET:** ⚠️ Segunda revisión sin acceso: Alpaca sigue requiriendo nuevo inicio de sesión. Sin operar; órdenes de F (stop 11,59 / objetivo 12,20) activas en el servidor.
- **2026-11-26 (Acción de Gracias, mercado cerrado):** conexión con Alpaca restablecida. Se comprueba que el **objetivo de F se ejecutó el 25-nov a las 14:10 ET a 12,20: operación #2 cerrada con +4,90 $ (+2,95R)**; el stop quedó cancelado automáticamente. Balance de la fase: 2 operaciones, 2 ganadoras (+0,19R y +2,95R), capital 120,28 $ (≈104,59 €, +4,6 %), drawdown máximo 1,3 % (19-nov). Todo en efectivo. Próxima sesión: viernes 27-nov, media jornada (cierra 13:00 ET).

---

## Fase 2 — Agresivo controlado (2026-12-03 → 2026-12-16)
_Pendiente._

---

## Fase 3 — Todo a por los 1000 € (2026-12-17 → 2026-12-31)
_Pendiente._

---

## Comparativa final
_Pendiente (2026-12-31)._

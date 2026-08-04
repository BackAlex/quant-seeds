# quant-seeds

Niveles dealer diarios de **ES** y **NQ** para [TradingView Pine Seeds](https://github.com/tradingview-pine-seeds/docs).

Los publica automáticamente el grabador de la plataforma Quant, una vez por
jornada después del cierre de opciones de EE.UU. (16:30 ET).

## Qué hay acá

`data/<SIMBOLO>.csv` — una fila por día: `YYYYMMDDT,open,high,low,close,volume`

| símbolo | qué es |
|---|---|
| `ES_ZERO_GAMMA` / `NQ_ZERO_GAMMA` | precio donde el GEX neto cruza cero |
| `ES_CALL_WALL` / `NQ_CALL_WALL` | strike de mayor gamma call |
| `ES_PUT_WALL` / `NQ_PUT_WALL` | strike de mayor gamma put |
| `ES_MAX_PAIN` / `NQ_MAX_PAIN` | strike que minimiza el pago total al vencimiento |
| `ES_SPOT` / `NQ_SPOT` | referencia |

Los niveles salen de las opciones de SPY y QQQ (feed demorado de CBOE) y se
traducen a precio de futuro con un ratio **medido**, no con el multiplicador
nominal — el ×41 nominal ponía los niveles ~140 puntos de NQ fuera de lugar.

## Qué NO hay

Nada de operaciones, posiciones, tamaños ni resultados. Solo niveles de
estructura de opciones, que son derivables de datos públicos.

Estos datos solo se DIBUJAN. Nada acá ejecuta órdenes.

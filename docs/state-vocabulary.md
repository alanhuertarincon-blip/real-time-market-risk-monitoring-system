# ZEC COPILOT — State Vocabulary & Detectors [VERIFIED, S4]

## Micro-detectors (pure functions, zec_micro.py)
- `contar_toques` — distinct level entries with hysteresis (touch counting).
- `rechazo_en_nivel` — bounce confirmation for defended levels.
- `absorcion` — aggressive one-sided volume WITHOUT price advance (proxy inference;
  no L2 order-book depth available).

## Named states (deterministic rule firing; priority: flow alerts beat structure)
- SOPORTE DEBILITADO / RESISTENCIA DEBILITADA (repeated touches, weakening)
- SOPORTE DEFENDIDO / RESISTENCIA DEFENDIDA (touch + confirmed rejection)
- COMPRAS SIN AVANCE / VENTAS SIN AVANCE (absorption; e.g. "Venta sin avance =
  trampa potencial")
- PROBANDO SOPORTE / PROBANDO RESISTENCIA (proximity-based, post-bugfix)
- Confirmed breakout states via established extremes (`extremes_between(300, 20)`,
  older tape segment) with close-beyond-threshold rule.
- Priority behavior observed live in test: 5 touches counted (SOPORTE_DEBILITADO
  queued) but absorption won the header as the stronger flow alert.

## Exact thresholds per state
MISSING here (inside the code; set by eye, unvalidated — do not treat as tuned).

# ZEC COPILOT — Error & Fix History

## E-Z01 — `lectura_ruptura_objetivo` never fired in production — RESOLVED [S4]
- Symptom: breakout/target block permanently showed "DENTRO DE RANGO".
- Root cause: nucleo levels always bracket price via the dead zone → `price >
  resistance` and `price < support` were mathematically impossible.
- Fix: proximity-based detection for PROBANDO states + established-extremes logic
  (older tape segment, `extremes_between(300, 20)`) for confirmed breakouts;
  monitor updated to compute/pass `est_high`/`est_low`; `detectar_micro` output
  wired to both classifier and context builder.
- Post-fix evidence: live tick shows "PROBANDO SOPORTE ... soporte a 0.3 ATR"
  firing (sample output preserved). Consolidated file rebuilt to 5 sections and
  re-verified; all tests pass.

## Known open gaps (not bugs; declared limitations) — UNRESOLVED
- Approximate liquidation (fixed MMR) [S4] — highest-danger gap.
- Gross PnL without fees/funding [S4].
- Session-only levels; no HTF/prior-day context [S4].
- Thresholds unvalidated on ZEC data [S3/S4].

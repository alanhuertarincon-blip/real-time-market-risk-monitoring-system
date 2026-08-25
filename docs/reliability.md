# ZEC COPILOT — Honest Reliability Assessment (delivered on direct request) [VERIFIED, S4]

Layer by layer:
- **Raw trade data (aggTrade websocket): genuinely accurate.**
- **Arithmetic (ATR, ratios, R-multiples): correct** — but ATR uses 15-second
  synthetic candles from session start, NOT standard chart ATR.
- **"Niveles reales": the most overstated element** — they reflect only the
  intra-session tape, not the structure other participants actually trade.
- **Liquidation price: explicitly approximate** (fixed MMR, no tier adjustment) —
  the MOST DANGEROUS gap for real money at high leverage.
- **PnL: gross** — no fees/funding (taker round-trip ≈ 4% of margin at 45x).
- **Named states: deterministic rules with hand-chosen thresholds, none backtested
  on ZEC.** Absorption without L2 depth is a proxy inference.
- Frame: a discipline & risk-visibility mechanism, NOT a predictive edge.

Accuracy roadmap in priority order (recorded): read-only API key for exact
liquidation → fees+funding in PnL → HTF/prior-day levels → raw tape recording →
state-outcome validation on ZEC data.

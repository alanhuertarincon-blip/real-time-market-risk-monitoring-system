# Real Time Market Risk & Monitoring System

A documented real-time ZECUSDT perpetual-futures market monitoring system built around live Binance trade data, ATR-normalized risk measures, R-multiples, market-state rules, and position-risk visibility.

**Status:** operational build completed; predictive validation pending.

## Current public-release status

The original implementation was recorded as a consolidated Python program of approximately **2,064 lines across five sections/modules** (`NUCLEO -> LECTURAS -> ESTADOS -> MICRO -> MONITOR`). The original source files are **not currently recoverable in this environment**, so this repository intentionally publishes the surviving technical evidence and validation record rather than a reconstructed substitute.

That boundary is important: the documentation supports what the system measured and how a key logic defect was fixed, but it would be misleading to invent source code and present it as the original implementation.

## What the surviving record supports

- Live Binance `aggTrade` data ingestion.
- ATR and R-multiple risk arithmetic.
- Intra-session volume/tape-derived support, resistance, and POC-style levels.
- Deterministic rule-based market states.
- A resolved breakout-detection bug: the original level construction always bracketed price, making `price > resistance` and `price < support` mathematically unreachable.
- Post-fix live test evidence showing `PROBANDO SOPORTE` at **0.3 ATR**.

## Important reliability boundary

The system was useful as a **risk-visibility and discipline tool**, not as a validated predictive edge. The surviving audit explicitly records several unresolved limitations: approximate liquidation calculations, gross PnL without fees/funding, session-only levels, and hand-selected state thresholds that were not backtested on ZEC.

See [`docs/reliability.md`](docs/reliability.md), [`docs/bug-fix.md`](docs/bug-fix.md), and [`docs/state-vocabulary.md`](docs/state-vocabulary.md).

## Source recovery

A complete public code release should only be added if the original `zec_copiloto.py` or its five module files are recovered from the original machine/chat outputs. Until then, this repository is an evidence-backed technical record, not a source-code reconstruction.

## Disclaimer

Research and portfolio documentation only. Not investment advice. No predictive performance claim is made.

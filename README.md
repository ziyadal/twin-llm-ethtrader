# Twin-LLM ETH Trader

An early notebook experiment exploring a two-stage LLM decision workflow for ETH market analysis.

The concept separates proposal from review:

1. An **Analyst** receives a constrained market snapshot built from price, EMA, RSI, ATR, and recent high/low data.
2. An **Auditor** reviews the proposed BUY / SELL / HOLD decision and either approves or revises it.
3. The workflow emits a structured JSON signal rather than relying on free-text parsing.

## What this experiment demonstrates

- Pulling daily OHLCV data with yfinance
- Computing EMA, RSI, ATR, and rolling price levels with pandas
- Passing only supplied market metrics to the model
- Separating signal generation from independent LLM review
- Producing machine-readable decisions and risk levels

## Status and limitations

**Learning prototype; not production-ready.** The committed notebook is a historical snapshot and is not reproducibly runnable from a clean checkout: it contains stale error output and references definitions that are not present in the current cells. It also has no walk-forward test, transaction-cost model, or execution layer.

The more rigorous successor is [multi-agent-trading-system](https://github.com/ziyadal/multi-agent-trading-system), which adds typed Pydantic contracts, LangGraph checkpointing, a human approval gate, lookahead-safe historical evaluation, and per-agent cost telemetry.

Educational research only. No live orders are submitted, and nothing here is financial advice.


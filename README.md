# Situational Awareness V2

Enhanced Market Intelligence System — a comprehensive multi-signal framework that fuses macro, geopolitical, sentiment, trade, institutional, and alternative data into actionable confidence scores for quantitative trading.

## Key Features

- **18 signal layers** across 6 dimensions (up from 8 microstructure-only layers in V1)
- **Hierarchical Bayesian fusion** — regime-conditional signal weighting
- **Signal → Meaning → Confidence pipeline** — not just "what is VIX?" but "what does VIX inversion mean in this regime?"
- **Dempster-Shafer theory** for uncertain geopolitical signals
- **Conflict escalation protocol** — LLM deep analysis when dimensions disagree
- **All free data sources** — FRED, GDELT, SEC EDGAR, Reddit, ACLED, World Bank, UN Comtrade

## Architecture

```
Regime Detection (L0: HMM on 4 macro factors)
    ↓ gates all weights
6 Dimensions × 18 Layers:
  A) Macro: Monetary (L1) + Credit (L2) + Economic (L3)
  B) Geopolitical: Risk (L7) + Trade Flow (L8)
  C) Sentiment: Market (L9) + Social (L10) + Whale (L11)
  D) Alternative: Satellite (L12) + Shipping (L13)
  E) Microstructure: V1 upgraded (L4-L6, L14-L18)
    ↓
Hierarchical Bayesian Fusion
    ↓
Risk Confidence (0-100) + Opportunity Confidence (0-100) + Action Recommendation
```

## Documentation

| Document | Description |
|----------|-------------|
| [DESIGN.md](DESIGN.md) | Full design specification (English) |
| [DESIGN_CN.md](DESIGN_CN.md) | 设计规范摘要（中文） |

## Methodology

This design was validated using the **Three Validation Framework**:

1. **First Principles** — Markets are complex adaptive systems; regime must precede signal interpretation; same signal means different things in different regimes
2. **Induction** — 80% of major moves come from macro/geo/sentiment; all expert frameworks rank liquidity #1; signal divergence is more informative than agreement
3. **Deduction** — AMH → regime determines strategy fitness → regime detection runs first → micro signals weighted by regime → disagreement signals regime transition

## Research Foundations

### Academic

- Endsley (1995): 3-Level SA Model
- Shiller: CAPE, Narrative Economics
- Taleb: Fat Tails, Black Swans, Convexity
- Andrew Lo: Adaptive Markets Hypothesis
- Sornette: LPPL Bubble Detection, Dragon-Kings
- Lopez de Prado: Triple Barrier, HRP, Meta-Labeling
- Hamilton (1989): Regime-Switching Models
- Baker-Wurgler (2006): Composite Sentiment Index

### Expert

- Dalio: Dual Debt Cycle, 5 Forces
- Howard Marks: Credit/Risk/Psychological Cycles
- Druckenmiller: Top-down macro → bottom-up
- El-Erian: Secular vs Cyclical, T-junctions
- Lyn Alden: Fiscal Dominance Thesis

### Institutional

- Bloomberg: 5-category signal framework
- Goldman Sachs: FCI + RAI + Recession Model
- JPMorgan: Bayesian regime indicator
- Bridgewater: Daily Observations process

### Open Source

- OpenBB (67k stars): Provider Registry pattern
- FinGPT (20k stars): FinBERT sentiment
- FinRobot (7k stars): Agent-of-Agents fusion
- QuantConnect Lean: Alpha Model pipeline

## Implementation Roadmap

| Phase | Weeks | Scope |
|-------|-------|-------|
| 1 | 1-2 | Regime detection (HMM) + Macro data pipeline (L0-L3) |
| 2 | 3-4 | Sentiment + Whale tracking + Social signals (L9-L11) |
| 3 | 5-6 | Geopolitical risk + Trade flow intelligence (L7-L8) |
| 4 | 7-8 | Alternative data: Satellite + Shipping (L12-L13) |
| 5 | 9-10 | Full Bayesian fusion + Strategy Brain integration |
| 6 | 11-12 | Optimization, backtesting, dashboard, documentation |

## Data Sources (All Free)

| Category | Source | API |
|----------|--------|-----|
| Macro | FRED | fredapi |
| Global Macro | World Bank / OECD | wbgapi / pandasdmx |
| Trade | UN Comtrade + Census | comtradeapicall / census |
| Geopolitical | GDELT + ACLED | gdelt / HTTP |
| Insider | SEC EDGAR | edgartools |
| Sentiment | Reddit + Finnhub | praw / finnhub-python |
| Shipping | MarineCadastre + FRED | CSV / fredapi |
| Satellite | NASA EarthData + Sentinel | HTTP / sentinelhub-py |

## License

MIT

## Status

🟡 Design Complete — Implementation Phase 1 starting

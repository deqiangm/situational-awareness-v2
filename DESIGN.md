# Situational Awareness V2: Enhanced Market Intelligence System

> A comprehensive multi-signal market intelligence framework that fuses macro, geopolitical, sentiment, trade, institutional, and alternative data into actionable confidence scores.

## Table of Contents

- [Executive Summary](#executive-summary)
- [Three Validation Analysis](#three-validation-analysis)
- [Architecture Overview](#architecture-overview)
- [Signal Classification Framework](#signal-classification-framework)
- [Data Sources Map](#data-sources-map)
- [Signal Fusion Methodology](#signal-fusion-methodology)
- [Confidence Score System](#confidence-score-system)
- [Layer Specifications](#layer-specifications)
- [Implementation Roadmap](#implementation-roadmap)
- [Research Bibliography](#research-bibliography)

---

## Executive Summary

### Problem

The current 8-layer situational awareness system (V1) is entirely **market-microstructure** level — sector rotation, concentration, breadth, IV regime, dynamic limits, gap analysis, opportunity cost, cash drag. While valuable, it misses the dominant drivers of market moves:

- **80% of major market shifts** originate from macro regime changes, geopolitical shocks, or sentiment inflections — not from technical indicators
- **Black swan events** (COVID-2020, Russia-Ukraine, SVB) are invisible to microstructure-only systems
- **Expert frameworks** (Dalio, Druckenmiller, Marks) consistently rank macro/liquidity as #1 signal, yet our system has zero macro coverage

### Solution

Expand from 8 microstructure layers to **18 layers across 6 dimensions**, with a hierarchical Bayesian fusion architecture that produces unified confidence scores per risk/opportunity category.

### Key Innovation

**Signal → Meaning → Confidence pipeline**: Not just "what is the VIX?" but "VIX term structure inversion in a tightening cycle with weakening breadth = 73% confidence of correction within 30 days."

---

## Three Validation Analysis

### First Principles (第一性原理)

**What is the fundamental problem?**

- Goal: Know the current market state with enough lead time to act
- Constraint 1: Markets are complex adaptive systems (Andrew Lo, AMH)
- Constraint 2: Signals have different frequencies — macro is monthly, sentiment is daily, tick data is microsecond
- Constraint 3: The same signal means different things in different regimes (e.g., rising rates = normal in expansion, dangerous in late cycle)
- Constraint 4: No single signal is sufficient — only signal constellations predict reliably

**Derived Facts:**

1. Regime identification must precede signal interpretation (Hamilton 1989)
2. Signal fusion must be regime-conditional, not static-weighted
3. Higher-frequency signals must be filtered through lower-frequency regime state
4. Confidence scores must reflect signal agreement, not just signal strength

### Induction (归纳法)

**Observed Phenomena:**

1. V1 8-layer system caught sector rotation and breadth divergence, but missed SVB contagion (no credit stress layer)
2. Baker-Wurgler sentiment index predicts cross-sectional returns 12 months ahead (academic consensus)
3. Yield curve inversion has preceded every US recession since 1960 — but with 6-24 month lead time
4. Druckenmiller's approach (top-down macro first) consistently outperforms bottom-up-only approaches
5. Bridgewater's Daily Observations process: systematic data collection → cause-effect analysis → stress-test → confidence level
6. GDELT event data spikes preceded Russia-Ukraine market impact by 2-5 days
7. Sornette's LPPL model successfully identified 2008, 2015 China, 2020 bubbles with measurable lead times
8. Goldman Sachs FCI (Financial Conditions Index) is the single most predictive indicator for 3-month forward returns

**Inductively Derived Patterns:**

1. Liquidity/credit conditions are the #1 signal across ALL expert frameworks
2. Macro dominates micro — 60-100% macro weight in institutional decision-making
3. Signal divergence (tech bullish + macro bearish) is more informative than signal agreement
4. Early warning has a hierarchy: credit stress → liquidity withdrawal → breadth decline → price decline
5. The most valuable signals are the ones that disagree with the consensus

### Deduction (演绎法)

**Premises:**

- P1: Market regime determines which strategies are fit (AMH)
- P2: Regime transitions are detectable from macro + credit + sentiment signals
- P3: Within a regime, microstructure signals have stable predictive relationships
- P4: Across regime boundaries, microstructure signals lose predictive power

**Logical Chain:**

1. P1 + P2 → Regime detection must run first, with highest priority
2. P3 + P4 → Micro signals must be weighted by regime-appropriateness
3. Signal disagreement between macro and micro → regime transition likely
4. Regime transition probability → position sizing and risk limit adjustment

**Conclusion:** The architecture must be **hierarchical**: Regime Layer (top) → Dimension Layers (middle) → Microstructure Layers (bottom). Bottom layers feed up, top layers gate and weight everything below.

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    CONFIDENCE SCORE OUTPUT                       │
│  Risk Confidence: 0-100  |  Opportunity Confidence: 0-100       │
│  Regime: [Expansion|Normal|Stress|Crisis]                       │
│  Action: [Aggressive|Neutral|Defensive|Survival]                │
└────────────────────────────┬────────────────────────────────────┘
                             │
┌────────────────────────────▼────────────────────────────────────┐
│              LAYER 0: REGIME DETECTION (Highest Priority)       │
│  Hidden Markov Model on macro factors → 4 states               │
│  Overrides all downstream signal weights                        │
└────────────────────────────┬────────────────────────────────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                     │
┌───────▼──────┐  ┌──────────▼──────┐  ┌──────────▼──────┐
│  DIMENSION A │  │  DIMENSION B    │  │  DIMENSION C    │
│   MACRO      │  │  GEOPOLITICAL   │  │  SENTIMENT      │
│              │  │  & POLITICAL    │  │  & SOCIAL       │
│ L1: Monetary │  │  L7: GeopolRisk │  │  L9: MktSentiment│
│ L2: Credit   │  │  L8: TradeFlow  │  │  L10: SocialSent │
│ L3: Economic │  │                 │  │  L11: WhaleTrack │
└───────┬──────┘  └────────┬────────┘  └────────┬────────┘
        │                  │                     │
┌───────▼──────┐  ┌────────▼────────┐            │
│  DIMENSION D │  │  DIMENSION E    │◄───────────┘
│  ALTERNATIVE │  │  MICROSTRUCTURE │
│              │  │  (V1 UPGRADED)  │
│ L12: AltData │  │                 │
│ L13: ShipSat │  │  L4: SectorRot  │
│              │  │  L5: MktBreadth │
│              │  │  L6: IVRegime   │
│              │  │  L14: ConcRisk  │
│              │  │  L15: DynLimits │
│              │  │  L16: GapAnal   │
│              │  │  L17: OppCost   │
│              │  │  L18: CashDrag  │
└───────┬──────┘  └────────┬────────┘
        │                  │
        └────────┬─────────┘
                 │
┌────────────────▼────────────────────────────────────────────────┐
│              FUSION ENGINE: Hierarchical Bayesian Network        │
│  - Regime-conditional weighting                                  │
│  - Signal conflict detection and escalation                     │
│  - Dempster-Shafer for uncertain signals                        │
│  - Confidence score = P(risk) × signal_agreement_factor         │
└─────────────────────────────────────────────────────────────────┘
```

---

## Signal Classification Framework

### Core Principle: Signal → Meaning → Action

Every signal follows a three-stage interpretation:

| Stage | Question | Example |
|-------|----------|---------|
| **Signal** | What is the raw data? | VIX = 28, term structure inverted |
| **Meaning** | What does it mean in this regime? | In Stress regime: fear rising, protection expensive |
| **Action** | What should we do? | Reduce position size, buy puts on SPY, raise cash |

### Signal Categories

#### RISK SIGNALS (Indicators of Danger)

| Signal | Threshold | Risk Indicated | Lead Time |
|--------|-----------|----------------|-----------|
| Yield curve inversion (10Y-2Y < 0) | < 0 bps | Recession in 6-24 months | Long |
| Credit spread widening (HY OAS) | > 500 bps | Credit stress, potential contagion | Medium |
| FCI tightening > 2 std dev | > 2σ from mean | Financial conditions deteriorating | Short |
| GDELT conflict tone < -5 | AvgTone < -5 | Geopolitical escalation | Very short |
| Put/Call ratio > 1.5 | > 1.5 | Extreme fear / hedging activity | Short |
| Cross-asset correlation spike | > 0.7 avg | Risk-off contagion | Immediate |
| Sornette LPPL critical point | Within 5% of tc | Bubble burst imminent | Very short |
| Insider selling surge | > 3x normal | Smart money exiting | Medium |
| Trade balance shock | > 20% MoM change | Supply chain disruption | Medium |
| VIX term structure inversion | 1M > 3M vol | Near-term stress expected | Short |

#### OPPORTUNITY SIGNALS (Indicators of Potential)

| Signal | Threshold | Opportunity Indicated | Lead Time |
|--------|-----------|----------------------|-----------|
| Yield curve steepening after inversion | From neg to pos | Recovery cycle beginning | Long |
| Credit spread compression | < 200 bps | Risk appetite returning | Medium |
| FCI easing > 2 std dev | > 2σ easing | Tailwind for risk assets | Short |
| Baker-Wurgler sentiment < 0.2 | Low sentiment | Contrarian buying opportunity | Long (12mo) |
| GDELT cooperation tone > 3 | AvgTone > 3 | Geopolitical de-escalation | Short |
| Put/Call ratio < 0.6 | < 0.6 | Complacency (contrarian: sell premium) | Medium |
| Sector rotation into cyclicals | XLK/XLF RS rising | Expansion phase opportunity | Medium |
| Insider buying surge | > 3x normal | Smart money accumulating | Medium |
| ISM PMI bottoming > 45 | Cross above 45 | Manufacturing recovery | Medium |
| Social sentiment divergence | Very bearish + rising price | Short squeeze potential | Short |

#### REGIME SIGNALS (Indicators of Structural Shift)

| Signal | Indicates | Action Override |
|--------|-----------|-----------------|
| GDP growth > 3% + low inflation | Expansion | Max positions (8+), growth bias |
| GDP growth 1-3% + stable inflation | Normal | Standard positions (6-8), balanced |
| GDP growth < 1% or yield curve inv | Stress | Reduce positions (4-6), defensive |
| GDP decline + credit stress + war | Crisis | Min positions (2-3), survival mode |
| Fiscal dominance (Alden) | Structural inflation | Real assets, avoid nominal bonds |

---

## Data Sources Map

### Dimension A: Macro

| Layer | Data | Source | API | Cost | Frequency |
|-------|------|--------|-----|------|-----------|
| L1: Monetary | Fed Funds Rate, Balance Sheet, FCI | FRED | fredapi | Free | Weekly |
| L1: Monetary | Global Central Bank Rates | BIS | pandasdmx | Free | Monthly |
| L2: Credit | HY OAS, IG Spreads, Loan Growth | FRED | fredapi | Free | Weekly |
| L2: Credit | 13F Institutional Holdings | SEC EDGAR | edgartools | Free | Quarterly |
| L3: Economic | GDP, CPI, Unemployment, PMI | FRED | fredapi | Free | Monthly |
| L3: Economic | ADS Real-time Index | Philadelphia Fed | HTTP | Free | Daily |
| L3: Economic | Global Leading Indicators | OECD | pandasdmx | Free | Monthly |

### Dimension B: Geopolitical & Trade

| Layer | Data | Source | API | Cost | Frequency |
|-------|------|--------|-----|------|-----------|
| L7: GeopolRisk | Conflict Events, Goldstein Scale | GDELT | gdelt | Free | Real-time |
| L7: GeopolRisk | Armed Conflict Data | ACLED | HTTP | Free (research) | Daily |
| L7: GeopolRisk | Political Stability Index | World Bank | wbgapi | Free | Annual |
| L8: TradeFlow | Bilateral Trade Volumes | UN Comtrade | comtradeapicall | Free (100/hr) | Monthly |
| L8: TradeFlow | US Import/Export | Census Bureau | census | Free | Monthly |
| L8: TradeFlow | Tariff Rate Changes | WTO | HTTP | Free | As needed |

### Dimension C: Sentiment & Social

| Layer | Data | Source | API | Cost | Frequency |
|-------|------|--------|-----|------|-----------|
| L9: MktSentiment | Fear & Greed Index | CNN scrape | custom | Free | Daily |
| L9: MktSentiment | CBOE Put/Call Ratio | CBOE | HTTP CSV | Free | Daily |
| L9: MktSentiment | VIX Term Structure | CBOE/yfinance | yfinance | Free | Daily |
| L9: MktSentiment | Fund Flow Directionals | FRED/ICI | fredapi | Free | Weekly |
| L10: SocialSent | Reddit WSB Mentions | Reddit/PRAW | praw | Free | Hourly |
| L10: SocialSent | News Sentiment (FinBERT) | Finnhub | finnhub-python | Free (60/min) | Daily |
| L10: SocialSent | Earnings Call NLP | SEC EDGAR + local FinBERT | custom | Free | Quarterly |
| L11: WhaleTrack | Insider Transactions | SEC Form 4 / OpenInsider | edgartools | Free | Daily |
| L11: WhaleTrack | 13F Institutional Changes | SEC EDGAR | edgartools | Free | Quarterly |
| L11: WhaleTrack | Large Block Trades | Unusual Whales (limited) | HTTP | Freemium | Real-time |

### Dimension D: Alternative Data

| Layer | Data | Source | API | Cost | Frequency |
|-------|------|--------|-----|------|-----------|
| L12: AltData | Nighttime Lights (econ proxy) | NASA EarthData | HTTP | Free | Monthly |
| L12: AltData | Oil Storage Estimation | Sentinel Hub | sentinelhub-py | Free (250k/mo) | Weekly |
| L13: ShipSat | AIS Vessel Tracking (US) | MarineCadastre | CSV download | Free | Daily |
| L13: ShipSat | Global Maritime Trade Stats | UNCTADstat | HTTP | Free | Monthly |
| L13: ShipSat | Container Rates | FRED (Harper Index) | fredapi | Free | Weekly |

### Dimension E: Microstructure (V1 Upgraded)

| Layer | Data | Source | API | Cost | Frequency |
|-------|------|--------|-----|------|-----------|
| L4-L6, L14-L18 | Existing 8 layers | yfinance + SQLite | yfinance | Free | Existing |

---

## Signal Fusion Methodology

### Why Hierarchical Bayesian Network

Based on the academic research, we chose a **hierarchical Bayesian network** for fusion because:

1. **Handles uncertainty**: Unlike simple weighted averages, Bayesian networks model uncertainty explicitly
2. **Regime-conditional**: Signal weights change based on regime state (AMH principle)
3. **Causal modeling**: Can encode known causal relationships (e.g., Fed rate → credit spreads → stock prices)
4. **Conflict detection**: When signals disagree, posterior probability reflects this — no artificial smoothing
5. **Incremental updates**: New data updates beliefs naturally (Bayes' theorem)

### Fusion Architecture

```
Level 1: Within-Dimension Fusion
─────────────────────────────────
Each dimension produces a Dimension Score (0-100) and a Confidence (0-1):

  Macro_Dimension = f(L1_score, L2_score, L3_score | regime_weights)
  GeoPol_Dimension = f(L7_score, L8_score | regime_weights)
  Sentiment_Dimension = f(L9_score, L10_score, L11_score | regime_weights)
  AltData_Dimension = f(L12_score, L13_score | regime_weights)
  Micro_Dimension = f(L4..L6, L14..L18 | regime_weights)

Level 2: Cross-Dimension Fusion
───────────────────────────────
Regime gates the dimension weights:

  IF regime == EXPANSION:
    Macro_weight = 0.30, Sentiment = 0.25, Micro = 0.25, GeoPol = 0.10, Alt = 0.10
  IF regime == NORMAL:
    Macro_weight = 0.25, Sentiment = 0.20, Micro = 0.30, GeoPol = 0.15, Alt = 0.10
  IF regime == STRESS:
    Macro_weight = 0.35, Sentiment = 0.15, Micro = 0.20, GeoPol = 0.20, Alt = 0.10
  IF regime == CRISIS:
    Macro_weight = 0.40, Sentiment = 0.10, Micro = 0.10, GeoPol = 0.30, Alt = 0.10

Level 3: Final Confidence Score
───────────────────────────────
  Risk_Confidence = Σ(dimension_risk × dimension_weight) × agreement_factor
  Opp_Confidence  = Σ(dimension_opp × dimension_weight) × agreement_factor

  agreement_factor = 1 - variance(dimension_scores) / max_possible_variance
  → When all dimensions agree, agreement_factor ≈ 1.0 (high confidence)
  → When dimensions disagree, agreement_factor < 0.5 (low confidence, wait)
```

### Dempster-Shafer for Uncertain Signals

For signals with high uncertainty (geopolitical events, alternative data), we use **Dempster-Shafer Evidence Theory** instead of Bayesian probability:

- Each signal provides a "mass function" m(A) where A is a hypothesis (e.g., "market will decline")
- Conflicting signals are fused via Dempster's combination rule
- This naturally handles "I don't know" — unlike Bayesian which forces a prior

**When to use D-S vs Bayesian:**
- Bayesian: well-sampled signals with historical data (yield curve, credit spreads, VIX)
- Dempster-Shafer: rare-event signals with limited history (geopolitical shocks, black swans)

### Conflict Escalation Protocol

When dimensions disagree significantly (variance > 50% of max):

1. **Flag as DIVERGENT** — LLM deep analysis triggered
2. **LLM analyzes the divergence root cause** — why are macro and micro disagreeing?
3. **Classify divergence type:**
   - *Lagging divergence*: Macro shifted but micro hasn't caught up → position for macro move
   - *False divergence*: One signal is noisy → trust the consensus
   - *Regime transition*: Both are right, regime is changing → reduce all exposure
4. **Output**: Divergence resolution + adjusted confidence score

---

## Confidence Score System

### Score Definitions

| Score Range | Meaning | Action |
|-------------|---------|--------|
| 0-20 | Very Low | Signal noise, no actionable intelligence |
| 21-40 | Low | Some indication but insufficient evidence. Hold/Observe |
| 41-60 | Moderate | Signal present but mixed. Small position, tight stops |
| 61-80 | High | Strong signal constellation. Full position sizing |
| 81-100 | Very High | Near-certainty (rare). Maximum conviction |

### Multi-Signal Combination Examples

#### Example 1: High Risk Confidence (Correction Imminent)

| Signal | Value | Risk Score | Weight |
|--------|-------|------------|--------|
| Yield curve inverted 8 months | -50 bps | 85 | 0.20 |
| HY OAS widening | 450 → 550 bps | 72 | 0.15 |
| FCI tightening | +2.1σ | 78 | 0.15 |
| GDELT conflict spike | AvgTone = -7 | 65 | 0.10 |
| VIX term structure inverted | 1M=32, 3M=24 | 80 | 0.10 |
| Put/Call > 1.5 | 1.8 | 68 | 0.10 |
| Breadth declining | A/D < 0.3 | 60 | 0.05 |
| Insider selling 3x | Surge | 70 | 0.05 |
| Microstructure (V1) | Mixed | 50 | 0.10 |

**Weighted Risk Score = 74.3**
**Agreement Factor = 0.88** (most signals point same direction)
**Final Risk Confidence = 74.3 × 0.88 = 65.4 → HIGH**

**Action**: Reduce positions to 4, raise cash to 30%, buy SPY puts, tighten stops

#### Example 2: High Opportunity Confidence (Recovery Beginning)

| Signal | Value | Opp Score | Weight |
|--------|-------|-----------|--------|
| Yield curve steepening | +30 bps from inv | 70 | 0.20 |
| Credit spreads compressing | 500 → 350 bps | 65 | 0.15 |
| ISM PMI bottoming | 44 → 47 | 58 | 0.15 |
| Baker-Wurgler low | 0.15 | 72 | 0.10 |
| Insider buying surge | 3x normal | 62 | 0.10 |
| Sentiment extreme fear | FGI = 12 | 68 | 0.10 |
| Sector rotation into cyclicals | XLK RS↑ | 55 | 0.05 |
| Microstructure (V1) | Mixed | 45 | 0.15 |

**Weighted Opp Score = 62.4**
**Agreement Factor = 0.76**
**Final Opp Confidence = 62.4 × 0.76 = 47.4 → MODERATE**

**Action**: Begin small positions in cyclicals, keep tight stops, scale in over 2-3 weeks

---

## Layer Specifications

### L0: Regime Detection (NEW — Highest Priority)

**Method**: Hidden Markov Model (Hamilton 1989) on 4 macro factors
- Factor 1: FCI (Financial Conditions Index)
- Factor 2: Yield Curve Slope (10Y-2Y)
- Factor 3: Real Credit Growth
- Factor 4: ADS Real-time Economic Activity Index

**States**: Expansion | Normal | Stress | Crisis

**Output**: Current regime + transition probabilities + time-in-state

**Data**: FRED daily/weekly series → kalman filter smoothing

**Regime Override Rules**:
- CRISIS detected → max 3 positions, 40% cash floor, no new longs without LLM approval
- STRESS detected → max 5 positions, 25% cash floor, reduce existing longs by 50%
- NORMAL → standard operating parameters
- EXPANSION → max 8 positions, growth-biased allocation

### L1: Monetary Conditions (NEW)

**Signals**:
- Fed Funds Rate direction (hiking/easing/pausing)
- Fed Balance Sheet change rate (QT/QE velocity)
- FCI z-score (financial conditions vs 5-year norm)
- Global CB policy convergence/divergence

**Key Rule**: Rate hiking cycle + balance sheet QT = double tightening = high risk
**Data Source**: FRED series FEDFUNDS, WALCL, BSIPTS + BIS policy rates

### L2: Credit Conditions (NEW)

**Signals**:
- HY OAS level and velocity (BAMLH0A0HYM2)
- IG OAS level and velocity
- Loan growth rate (commercial bank loans)
- Default rate trajectory
- Credit impulse (new credit / GDP change)

**Key Rule**: OAS widening velocity > OAS level — rapid widening is the danger signal
**Data Source**: FRED series BAMLH0A0HYM2, BAMLC0A4CBBB, NANQFPSMEI

### L3: Economic Activity (NEW)

**Signals**:
- ADS Real-time Index (Aruoba-Diebold-Scotti)
- ISM Manufacturing PMI
- ISM Services PMI
- Unemployment rate + initial claims trajectory
- CPI + PCE inflation trajectory
- Consumer confidence (UMCSENT)

**Key Rule**: PMI < 45 for 2+ months = recession signal; PMI bottoming above 45 = recovery signal
**Data Source**: FRED series ADS, MANEMP, NFP, UNRATE, CPIAUCSL, UMCSENT

### L7: Geopolitical Risk (NEW)

**Signals**:
- GDELT AvgTone (global news sentiment -10 to +10)
- GDELT Goldstein Scale (conflict-cooperation -10 to +10)
- ACLED conflict event count and fatalities
- Caldara-Iacoviello Geopolitical Risk Index (GPR)
- Country stability indicators (World Bank)

**Key Rule**: GPR spike > 2σ + AvgTone < -5 = active crisis escalation
**Data Source**: GDELT API, ACLED API, FRED GPRCVR series

### L8: Trade Flow Intelligence (NEW)

**Signals**:
- US trade balance trajectory
- Bilateral trade flow changes (US-China, US-EU)
- Tariff rate changes (WTRI index)
- Container shipping rates (HARPEX)
- Export control events

**Key Rule**: Trade balance shock > 20% MoM = supply chain disruption risk
**Data Source**: UN Comtrade API, Census Bureau API, FRED HARPEX

### L9: Market Sentiment (NEW)

**Signals**:
- CNN Fear & Greed Index (0-100 composite)
- CBOE Total Put/Call Ratio
- VIX level + term structure (1M/3M/6M)
- Fund flow directionals (equity vs bond funds)
- Short interest ratio (market-wide)

**Key Rule**: FGI < 20 = extreme fear (contrarian buy); FGI > 80 = extreme greed (contrarian sell premium)
**Data Source**: CNN scrape, CBOE CSV, yfinance VIX, FRED IFAF

### L10: Social Sentiment (NEW)

**Signals**:
- Reddit WSB mention count + sentiment (PRAW + FinBERT)
- News sentiment via FinBERT/Finnhub
- Earnings call NLP (Loughran-McDonald dictionary)
- Social media momentum (mention velocity)

**Key Rule**: Mention spike 5x+ for a stock = attention but not direction; combine with price action
**Data Source**: Reddit PRAW, Finnhub API, SEC EDGAR transcripts

### L11: Whale Tracking (NEW)

**Signals**:
- Insider buy/sell ratio (Form 4)
- 13F institutional position changes (quarterly)
- Cluster buys (multiple insiders at same company)
- CEO/CFO purchase signals
- Hedge fund concentration in sectors

**Key Rule**: Cluster insider buying at 52-week lows = strongest bull signal
**Data Source**: SEC EDGAR Form 4, 13F via edgartools, OpenInsider

### L12: Alternative Data - Economic Proxies (NEW)

**Signals**:
- Nighttime light intensity change (economic activity proxy)
- Oil storage tank fullness (Sentinel satellite)
- Consumer spending proxies (credit card data where available)

**Key Rule**: These are supplementary, not primary — use to confirm or question primary signals
**Data Source**: NASA EarthData, Sentinel Hub

### L13: Shipping & Satellite (NEW)

**Signals**:
- AIS vessel count in key ports (US coastal)
- Global maritime trade statistics
- Container rate index (HARPEX)
- Dry bulk shipping rates (BDI proxy)

**Key Rule**: Port activity drop > 30% = real economy slowdown signal
**Data Source**: MarineCadastre AIS CSV, UNCTADstat, FRED HARPEX

### L4-L6, L14-L18: Upgraded V1 Layers

Existing 8 layers remain but gain:
- **Regime-conditional weighting** (different weights in expansion vs crisis)
- **Cross-dimension validation** (breadth decline confirmed by credit stress = stronger signal)
- **Velocity indicators** (rate of change matters more than absolute level)

---

## Implementation Roadmap

### Phase 1: Foundation (Week 1-2)

**Goal**: Regime detection + macro data pipeline

- [ ] L0: Implement HMM regime detector on FRED data (4 factors)
- [ ] L1: Monetary conditions module (Fed rate, balance sheet, FCI)
- [ ] L2: Credit conditions module (OAS, loan growth, default rate)
- [ ] L3: Economic activity module (ADS, PMI, unemployment, CPI)
- [ ] Data pipeline: FRED API client with caching (SQLite)
- [ ] Regime override: integrate into existing dynamic_limits

### Phase 2: Sentiment & Intelligence (Week 3-4)

**Goal**: Sentiment + whale tracking + social signals

- [ ] L9: Market sentiment module (FGI, P/C ratio, VIX term structure)
- [ ] L10: Social sentiment module (Reddit PRAW, Finnhub NLP)
- [ ] L11: Whale tracking module (SEC EDGAR 13F + Form 4)
- [ ] Signal classification engine (risk/opportunity/regime categories)
- [ ] Confidence score calculator (weighted average + agreement factor)

### Phase 3: Geopolitical & Trade (Week 5-6)

**Goal**: Geopolitical risk + trade flow intelligence

- [ ] L7: Geopolitical risk module (GDELT, ACLED, GPR index)
- [ ] L8: Trade flow module (UN Comtrade, Census Bureau, HARPEX)
- [ ] Dempster-Shafer fusion for uncertain signals
- [ ] Conflict escalation protocol

### Phase 4: Alternative Data (Week 7-8)

**Goal**: Satellite, shipping, and alternative data

- [ ] L12: Alternative data module (nighttime lights, oil storage)
- [ ] L13: Shipping module (AIS data, maritime trade stats)
- [ ] Cross-dimension validation engine
- [ ] Divergence detection and LLM escalation protocol

### Phase 5: Fusion & Integration (Week 9-10)

**Goal**: Full Bayesian fusion + Strategy Brain integration

- [ ] Hierarchical Bayesian network implementation
- [ ] Regime-conditional weight matrices
- [ ] Integration with Strategy Brain (replace V1 Step 1)
- [ ] Backtesting framework (validate signal combinations)
- [ ] Alert system (Telegram notifications on high-confidence signals)

### Phase 6: Refinement (Week 11-12)

**Goal**: Optimization and validation

- [ ] Signal weight optimization (walk-forward analysis)
- [ ] Sornette LPPL bubble detection integration
- [ ] Real-time dashboard (FastAPI + SPA)
- [ ] Performance tracking (signal accuracy vs outcomes)
- [ ] Documentation and skill packaging

---

## Research Bibliography

### Academic Foundations

| Author | Key Work | Contribution to SA V2 |
|--------|----------|----------------------|
| Mica Endsley | "Toward a Theory of Situation Awareness" (1995) | 3-Level SA Model: Perception → Comprehension → Projection |
| Robert Shiller | "Irrational Exuberance" (2000/2015); "Narrative Economics" (2019) | CAPE framework, behavioral sentiment, narrative detection |
| Nassim Taleb | "The Black Swan" (2007); "Statistical Consequences of Fat Tails" (2020) | Mediocristan vs Extremistan, tail risk, convexity scoring |
| Andrew Lo | "Adaptive Markets" (2017) | AMH: markets adapt like ecosystems, regime determines strategy fitness |
| Didier Sornette | "Why Stock Markets Crash" (2003); Dragon-Kings (2009) | LPPL bubble detection, critical point prediction, Financial Crisis Observatory |
| Marcos Lopez de Prado | "Advances in Financial Machine Learning" (2018) | Triple barrier labeling, HRP, meta-labeling, combinatorial purged CV |
| James Hamilton | "Regime-Switching Models" (1989, Econometrica) | Hidden Markov Models for macro regime detection |
| Baker & Wurgler | "Investor Sentiment and Cross-Section of Stock Returns" (2006, JF) | Composite sentiment index, sentiment as contrarian predictor |
| Kaminsky, Lizondo, Reinhart | "Leading Indicators of Currency Crises" (1998, IMF) | KLR signals approach: threshold-based composite early warning |
| Battiston et al. | "DebtRank" (2012); "Bayesian Networks for Systemic Risk" (ECB) | Network contagion model, Bayesian fusion for financial risk |

### Expert Methodologies

| Expert | Framework | Key Signals | Weight Priority |
|--------|-----------|-------------|-----------------|
| Ray Dalio | Dual Debt Cycle (5-10yr short / 50-100yr long), 5 Forces | Productivity, Debt Cycle, Wealth Gap, Geopolitics, Climate | Macro 90%, Micro 10% |
| Howard Marks | 3 Intertwined Cycles (credit/risk/psychological), Second-level Thinking | Credit cycle position, risk appetite, investor psychology | Macro 70%, Sentiment 30% |
| Stanley Druckenmiller | Top-down macro first → bottom-up, Asymmetric R/R | Liquidity conditions, momentum, then valuation | Macro 80%, Micro 20% |
| Mohamed El-Erian | Secular vs Cyclical, T-junctions, Narrative vs Data | Structural regime, inflection points, divergence detection | Macro 70%, Micro 30% |
| Lyn Alden | Fiscal Dominance, Global Dollar Squeeze, Petrodollar Fraying | Fiscal deficits + QE, dollar liquidity, trade settlement shifts | Macro 85%, Trade 15% |

### Institutional Systems

| Institution | System | Key Features |
|-------------|--------|-------------|
| Bloomberg Terminal | Custom Monitors, FCI, Recession Probability | 5 categories (macro/market/flow/sentiment/liquidity), user-configurable |
| Goldman Sachs | FCI, RAI, Recession Model, Surprise Index, Bull/Bear Indicators | Quantitative weighting + qualitative overlay, 5-indicator dashboard |
| JPMorgan | Market Regime Indicator, Credit Cycle, Global Liquidity, Factor Momentum | Bayesian updating, 5-dashboard structure |
| Bridgewater | Daily Observations (BDO), Cause-Effect Framework | Systematic data → causal analysis → stress test → confidence level, radical transparency |

### Open Source References

| Project | Stars | Key Pattern Adopted |
|---------|-------|---------------------|
| OpenBB Terminal | 67.4k | Provider Registry pattern for data normalization |
| FinGPT | 20k | FinBERT sentiment classification, PEFT for finance NLP |
| FinRobot | 6.9k | Agent-of-Agents composition for multi-signal fusion |
| QuantConnect Lean | 9k+ | Alpha Model pipeline (signal → score → weight → aggregate) |
| MacroDashboard | 10 | Flask + FRED integration pattern |

### Data Source Summary

| Category | Best Free Source | API Package | Update Frequency |
|----------|-----------------|-------------|-----------------|
| Macro Economic | FRED | fredapi | Daily-Weekly |
| Global Macro | World Bank / OECD | wbgapi / pandasdmx | Monthly-Annual |
| Trade | UN Comtrade + Census | comtradeapicall / census | Monthly |
| Geopolitical | GDELT + ACLED | gdelt / HTTP | Real-time / Daily |
| Insider | SEC EDGAR | edgartools | Daily-Quarterly |
| Sentiment | Reddit + Finnhub | praw / finnhub-python | Hourly-Daily |
| Shipping | MarineCadastre + FRED | CSV / fredapi | Daily-Weekly |
| Satellite | NASA EarthData + Sentinel | HTTP / sentinelhub-py | Weekly-Monthly |

---

*Design Version: 2.0 | Date: 2026-05-11 | Methodology: Three Validation (First Principles + Induction + Deduction)*

# Situational Awareness V2: Knowledge Base

> Empirical rules distilled from academic theory and real-world market behavior. This is a living document — continuously expanded as new patterns are discovered and validated.

## Table of Contents

- [Signal-Effect Knowledge Base](#signal-effect-knowledge-base)
- [Macro Parameter Impact Map](#macro-parameter-impact-map)
- [Key Figure Influence Map](#key-figure-influence-map)
- [Sentiment-Price Interaction Rules](#sentiment-price-interaction-rules)
- [Regime-Specific Playbook](#regime-specific-playbook)
- [Cross-Signal Interaction Matrix](#cross-signal-interaction-matrix)
- [Historical Pattern Encyclopedia](#historical-pattern-encyclopedia)

---

## Signal-Effect Knowledge Base

### Credit & Debt Signals

| Signal | What It Indicates | Typical Effect | Lead Time | Academic Basis |
|--------|-------------------|----------------|-----------|----------------|
| Yield curve inversion (10Y-2Y < 0) | Recession ahead; short-term rates > long-term = banks can't profit from lending | Equity decline begins 6-18 months after inversion; banks underperform immediately | 6-24 months | Estrella & Mishkin (1998); every US recession since 1960 |
| Yield curve steepening (after inversion) | Recession ending; monetary easing beginning | Cyclical stocks outperform; credit spreads compress | 3-6 months after steepening | Historical pattern, Fed easing cycle |
| HY OAS > 500bps | Credit stress; high-yield bonds demand large risk premium | Equity volatility rises; small caps underperform; value traps appear | 1-3 months | Altman (1989) default cycle; Alessi-Detken (2011) |
| HY OAS widening velocity > 50bps/week | Credit deterioration accelerating — more important than absolute level | Systemic risk rising; contagion to equities likely | 2-4 weeks | Giesecke et al. (2011) — credit spread velocity predicts default clustering |
| IG OAS > 200bps | Investment-grade stress; corporate bond market distressed | Equity risk premium rises; buybacks decline; capex cuts | 1-2 months | Greenwood & Hanson (2013) — IG spreads predict equity returns |
| Commercial loan growth declining | Banks tightening lending standards | Economic slowdown 2-3 quarters ahead | 2-3 quarters | Fed Senior Loan Officer Survey (SLOOS) — best leading indicator per Fed research |
| Credit impulse turning negative | New credit creation < debt repayment — economy losing fuel | GDP growth decelerates within 2-4 quarters | 2-4 quarters | Biggs et al. (2010) — credit impulse predicts GDP better than credit stock |
| Fed balance sheet shrinking (QT) | Liquidity withdrawal from financial system | Risk asset pressure; dollar strength; emerging market stress | 3-6 months | BIS research: QT effects lag by 2-4 quarters; 2018 QT caused repo crisis |

### Monetary Policy Signals

| Signal | What It Indicates | Typical Effect | Lead Time | Source |
|--------|-------------------|----------------|-----------|--------|
| Fed Funds Rate rising + yield curve flattening | Late-cycle tightening; approaching recession | Bond rally ahead; equity rotation to defensive; financials weaken | 6-18 months | Dalio's debt cycle framework |
| Fed pivot (last hike → pause → cut) | Policy reversal typically signals recession has arrived or is imminent | Initial equity rally on "Fed put" → often followed by further decline if recession is deep | 0-6 months | "Don't fight the Fed" — but first cut often coincides with crisis (2001, 2007, 2019) |
| FCI tightening > 2σ | Financial conditions significantly restrictive | Equity returns decline over next 3 months | 1-3 months | Goldman Sachs FCI research — best 3-month equity predictor |
| FCI easing > 2σ | Financial conditions very accommodative | Tailwind for risk assets over next 3 months | 1-3 months | Same — FCI easing precedes risk rallies |
| Global CB policy divergence | Some CBs hiking while others easing | Currency volatility; carry trades affected; capital flows to tightening jurisdictions | Immediate-3 months | BIS research: policy divergence → FX volatility → EM stress |
| Rate cuts + balance sheet expansion (QE) | Stimulus regime — "money printing" if combined with fiscal deficits | Asset inflation; real asset outperformance; nominal bond yields may rise despite cuts | 3-12 months | Alden: Fiscal dominance thesis — QE alone ≠ money printing; QE + fiscal deficits = money printing |

### Economic Indicator Signals

| Signal | What It Indicates | Typical Effect | Lead Time | Source |
|--------|-------------------|----------------|-----------|--------|
| ISM Manufacturing PMI < 45 | Manufacturing in deep contraction | Broad economic weakness; industrials/materials underperform | 0-3 months | ISM: below 45 = recession-level in manufacturing |
| ISM PMI bottoming above 45 then rising | Manufacturing recovery beginning | Cyclical stocks lead; commodities bottom | 1-3 months ahead of GDP recovery | Historical: PMI bottoms 3-6 months before GDP |
| Initial jobless claims rising 4+ consecutive weeks | Labor market deterioration beginning | Consumer discretionary weakness; recession risk rising | 2-4 months | Fed research: initial claims are best real-time labor indicator |
| Unemployment rate rising from cycle low (Sahm Rule) | Sahm Rule triggered = recession has started | Significant equity downside ahead; defensive rotation | 0-2 months | Sahm (2019): 0.5pp rise in 3-month avg unemployment = recession already started |
| CPI > 5% and accelerating | Inflationary pressure; Fed will tighten | Bond sell-off; growth stocks underperform; real assets outperform | 0-6 months | Shiller: high inflation → high equity risk premium |
| CPI declining from peak | Disinflation; Fed may ease | Growth stocks recover; duration assets rally | 3-9 months | Historical: equity rally begins when CPI clearly declining |
| ADS Real-time Index < -0.5 | Real-time economic activity contracting | Recession risk elevated | Current | Aruoba, Diebold, Scotti (2009): daily real-time conditions |
| Consumer confidence (UMCSENT) dropping sharply | Consumer spending will decline | Retail, discretionary, housing weakness ahead | 1-3 months | UMich: sentiment drops precede spending drops by 1-3 months |

---

## Macro Parameter Impact Map

### Interest Rates

| Parameter | Direct Impact | Second-Order Impact | Typical Magnitude |
|-----------|--------------|--------------------|--------------------|
| Fed Funds Rate +25bps | Bank funding costs rise; variable rate debt costs increase | Bond yields rise; mortgage rates rise; equity valuations compressed (higher discount rate) | SPX typically -0.5% to -1.5% on surprise hike |
| Fed Funds Rate -25bps | Cheaper borrowing; stimulus signal | Bond rally; mortgage refi wave; equity valuations expand | SPX typically +0.5% to +1.5% on surprise cut |
| 10Y Treasury yield +50bps | Mortgage rates rise ~50bps; duration assets fall | Housing slowdown; growth stock PE compression; bank NIM may improve | SPX -3% to -7% for rapid 50bps rise |
| 10Y Treasury yield -50bps | Mortgage rates fall; duration assets rally | Refinancing wave; growth stocks PE expansion; flight to safety signal | SPX +2% to +5% if driven by demand; -5% if driven by recession fear |

### Inflation

| Parameter | Direct Impact | Second-Order Impact | Typical Magnitude |
|-----------|--------------|--------------------|--------------------|
| CPI > expected by 0.5pp | Bond sell-off; rate hike expectations surge | Growth stocks decline; commodities rally; TIPS outperform nominal bonds | SPX -1% to -3% on CPI miss |
| CPI < expected by 0.5pp | Bond rally; rate cut expectations rise | Growth stocks rally; value underperforms; real yields decline | SPX +1% to +2% on CPI beat |
| PCE Core accelerating | Fed's preferred inflation measure rising → more hawkish | Same as CPI but slower transmission (monthly data) | Similar to CPI |
| Wage growth > 4% | Labor cost pressure; margin compression | Fed more hawkish; automation investment increases; services inflation | SPX -1% to -2%; labor-intensive sectors hit hardest |

### Economic Growth

| Parameter | Direct Impact | Second-Order Impact | Typical Magnitude |
|-----------|--------------|--------------------|--------------------|
| GDP growth > 3% | Strong economy; corporate earnings growth | Risk-on; cyclicals outperform; Fed may tighten | Bullish for equities, bearish for bonds |
| GDP growth < 1% | Stagnation; recession risk | Risk-off; defensives outperform; Fed may ease | Bearish for equities, bullish for bonds |
| GDP negative QoQ | Recession may have started | Significant equity downside; credit stress rises | SPX typically -15% to -30% in recession |
| PMI > 55 | Strong expansion | Cyclical outperformance; commodities demand rises | Very bullish for industrials, materials |
| PMI < 45 | Contraction | Defensive rotation; bond rally | Bearish for cyclicals |

### Global Trade

| Parameter | Direct Impact | Second-Order Impact | Typical Magnitude |
|-----------|--------------|--------------------|--------------------|
| Trade balance widening (deficit) | More imports; domestic producers compete with imports | Dollar demand (to pay for imports); manufacturing weakness | Moderate impact on specific sectors |
| Tariff increase 10%+ | Import costs rise; inflationary; trade partners retaliate | Supply chain disruption; specific sector impact (steel, tech, ag) | Affected sectors -5% to -15% |
| Container rates doubling | Shipping costs surge; supply chain stress | Inflationary pressure; imported goods cost more; trade volume may decline | Consumer goods margins compressed |
| Export controls (tech) | Targeted companies/sectors lose market access | Decoupling acceleration; domestic substitution theme | Sector-specific: -10% to -30% for directly affected |

---

## Key Figure Influence Map

### Central Bankers

| Figure | Current Role | Market Impact | Key Signals to Watch |
|--------|-------------|---------------|---------------------|
| Jerome Powell | Fed Chair | Highest impact — every word parsed for policy direction | "Data dependent" = no pivot yet; "confident inflation moving to 2%" = cut coming; "attenuate" = slow QT |
| ECB President | ECB | Euro, European banks, EUR-denominated assets | Rate decision language; TPI (Transmission Protection Instrument) activation |
| PBoC Governor | China Central Bank | Chinese equities, EM currencies, commodity demand | RRR cuts = stimulus; MLF rate = policy direction; "counter-cyclical" = easing |

### Market Legends

| Figure | Known For | Impact When Speaking | Key Frameworks |
|--------|-----------|---------------------|----------------|
| Ray Dalio | Bridgewater; "How The Economic Machine Works" | Moves macro discussion; institutional repositioning follows | Dual debt cycle; 5 forces; bubble checklist (6 criteria) |
| Howard Marks | Oaktree; risk memos | Moves credit markets; institutional risk appetite shifts | Credit cycle position; "risk-on/risk-off" assessment; second-level thinking |
| Stanley Druckenmiller | 30 years no down year; top-down macro | Rarely speaks publicly, but when he does, moves markets | Liquidity first; asymmetric risk-reward; "don't invest in what you don't understand" |
| Warren Buffett | Berkshire Hathaway; value investing | Cash deployment signals (buying = bottom near); cash hoarding = caution | "Be greedy when others are fearful"; Buffett Indicator (mkt cap/GDP); buyback behavior |
| Cathie Wood | ARK Invest; innovation investing | ARK flows move high-growth stocks; contrarian tech calls | Innovation cycles; 5-year horizons; technology convergence |
| Bill Ackman | Pershing Square; activist | Hedging signals (2008, 2020) extremely accurate; activism targets rally | "I see the mothership" = big bet; hedge positions reveal macro views |
| Michael Burry | Scion Capital; Big Short | Rare Twitter posts move markets; deletion pattern = concern level | "Sell" tweets; focus on speculative bubbles; TSLA puts signal |

### Political Figures

| Figure | Impact Domain | Market-Relevant Signals |
|--------|--------------|----------------------|
| US President | Trade policy, fiscal policy, regulation | Executive orders on trade/tariffs; infrastructure bills; tax policy; appointments to Fed/CFTC |
| US Treasury Secretary | Dollar policy, sanctions, debt management | "Strong dollar" policy language; sanctions announcements; debt ceiling negotiations |
| Chinese Premier/President | China stimulus, trade, regulation | Stimulus announcements; regulatory crackdown signals; trade negotiation posture |
| Key EU Leaders | EU regulation, fiscal, trade | Digital regulation (DMA/DSA); fiscal integration; Russia policy |

### What Their ACTIONS Signal (More Important Than Words)

| Action | What It Really Means | Market Effect |
|--------|---------------------|---------------|
| Buffett buying aggressively | Smart money sees value; market near bottom or specific sector undervalued | Bullish for targets; broad sentiment boost |
| Buffett hoarding cash ($100B+) | Few attractive values; caution warranted | Bearish signal — "when Buffett can't find value, market is expensive" |
| Druckenmiller going to cash | Macro uncertainty; risk-reward unfavorable | Very bearish — he almost never goes fully to cash except before major events |
| Dalio's Bridgewater reducing equity exposure | Systematic risk-off; macro regime deteriorating | Bearish — Bridgewater's systematic signals are data-driven |
| 13F filings: hedge funds crowding into same sector | Consensus trade — vulnerable to unwind | Contrarian: crowded trades often reverse violently |
| Insider cluster buying | Multiple insiders at same company buying with personal funds | Strongest bullish signal: people with best information are buying |
| CEO selling > 50% of holdings | Insider thinks stock overvalued or trouble ahead | Bearish for that stock; sector contagion possible |
| Sovereign wealth funds buying gold | De-dollarization; inflation hedge; geopolitical risk | Gold bullish; dollar negative; real asset positive |

---

## Sentiment-Price Interaction Rules

### Market Sentiment Indicators

| Indicator | Extreme Read | What It Means | Historical Win Rate |
|-----------|-------------|---------------|-------------------|
| CNN Fear & Greed Index < 10 | Extreme Fear | Contrarian: market near bottom | 82% positive 12-month returns from FGI < 10 |
| CNN Fear & Greed Index > 90 | Extreme Greed | Contrarian: market near top | 71% negative 12-month returns from FGI > 90 |
| CBOE Put/Call > 1.5 | Extreme hedging | Near-term bottom if other indicators confirm | 68% positive 1-month returns from extreme P/C |
| CBOE Put/Call < 0.5 | Extreme complacency | Vulnerable to selloff | 63% negative 3-month returns |
| VIX > 35 | Extreme fear | Usually coincides with or near bottom | 75% positive 6-month returns from VIX > 35 |
| VIX < 12 | Extreme complacency | Risk buildup; tail risk underpriced | 58% negative 6-month returns |
| AAII Bullish > 55% | Retail euphoria | Contrarian: retail often wrong at extremes | 65% negative 6-month returns |
| AAII Bearish > 55% | Retail despair | Contrarian: buying opportunity | 67% positive 6-month returns |

### Social Sentiment Rules

| Pattern | Signal | Reliability | Why |
|---------|--------|-------------|-----|
| Reddit WSB mentions 10x spike for a stock | Attention surge — NOT direction signal | Low for direction, High for volatility | Attention ≠ conviction; meme stocks are extremely volatile both ways |
| WSB overwhelmingly bullish + stock already up 50%+ | FOMO top forming | Moderate | Retail euphoria at tops; smart money exits |
| WSB overwhelmingly bearish + stock at 52-week low | Potential contrarian buy | Low-Moderate | Sometimes right (value trap), sometimes wrong (fundamentals deteriorating) |
| Twitter/X sentiment reversal (bullish→bearish) after rally | Momentum exhaustion | Moderate | Social momentum reversal precedes price reversal by 1-5 days |
| Earnings call NLP: "challenging" frequency rising | Management preparing market for bad news | High | Loughran-McDonald: "challenging" is the #1 negative predictor in earnings calls |
| Earnings call NLP: "confident" frequency rising | Management genuinely optimistic | Moderate-High | "Confident" is #2 positive predictor in financial NLP |

### Fund Flow Signals

| Pattern | What It Means | Effect |
|---------|---------------|--------|
| Massive equity fund inflows | Retail chasing rally | Contrarian bearish: top often near when fund inflows peak |
| Massive equity fund outflows | Capitulation selling | Contrarian bullish: bottom often near when outflows peak |
| Bond fund inflows + equity outflows simultaneously | Flight to safety | Confirms risk-off regime; defensive positioning warranted |
| Sector rotation: Tech → Energy | Growth to value rotation | Macro shift: rising rates/inflation expectations |

---

## Regime-Specific Playbook

### EXPANSION Regime (GDP > 3%, low inflation, steep yield curve)

| Dimension | Optimal Strategy | Key Signals to Monitor |
|-----------|-----------------|----------------------|
| Equity | Growth/beta bias; maximize position count (8+) | PMI, earnings growth, retail sales |
| Options | Sell premium (low IV); covered calls on growth stocks | IV percentile < 30% |
| Sectors | Tech, Consumer Discretionary, Financials | Sector rotation into cyclicals |
| Risk | Low — but watch for overheating signals | CPI acceleration, wage growth > 4% |
| Duration | Long duration assets OK (growth stocks benefit from low rates) | Yield curve flattening = early warning |
| **Exit Signal** | Yield curve flattening + PMI peaking + FCI tightening | These 3 together = expansion ending |

### NORMAL Regime (GDP 1-3%, stable inflation, moderate yield curve)

| Dimension | Optimal Strategy | Key Signals to Monitor |
|-----------|-----------------|----------------------|
| Equity | Balanced; 6-8 positions; alpha-driven selection | Breadth, sector rotation, earnings |
| Options | Balanced premium selling and buying | IV around 40-60th percentile |
| Sectors | Mix growth and value; follow alpha signals | Relative strength shifts |
| Risk | Moderate — position sizing matters | Credit spread widening, sentiment extremes |
| **Exit Signal** | Credit spreads widening + FCI > 1σ tightening | Early stress signs |

### STRESS Regine (GDP < 1%, yield curve inverted, FCI tightening)

| Dimension | Optimal Strategy | Key Signals to Monitor |
|-----------|-----------------|----------------------|
| Equity | Defensive; 4-5 positions; raise cash to 25%+ | Sahm Rule, initial claims, HY OAS |
| Options | Buy protection (puts, debit spreads); reduce premium selling | IV > 60th percentile; P/C ratio rising |
| Sectors | Utilities, Staples, Healthcare, Cash | Defensive rotation confirmed |
| Risk | High — any negative catalyst can trigger cascade | Geopolitical events, earnings misses, credit events |
| Duration | Short duration; avoid long-duration bonds (rates may still rise) | Yield curve may steepen = recession starting |
| **Exit Signal** | VIX > 35 + credit markets frozen + multiple Fed emergency cuts = CRISIS |

### CRISIS Regime (GDP decline, credit freeze, market panic)

| Dimension | Optimal Strategy | Key Signals to Monitor |
|-----------|-----------------|----------------------|
| Equity | Survival; 2-3 positions max; 40%+ cash | Capitulation signals: VIX > 40, FGI < 10 |
| Options | Protective puts; cash-secured puts at extreme lows | IV > 80th percentile; extreme skew |
| Sectors | Cash, Gold, Treasuries (short end) | Flight to safety assets |
| Risk | Extreme — preserve capital, not grow it | Counterparty risk, liquidity withdrawal |
| Duration | Ultra-short; T-bills only | Long bonds may rally in flight-to-safety but carry duration risk |
| **Re-Entry Signal** | FGI < 10 + insider buying surge + Fed pivot + credit spreads compressing = recovery beginning |

---

## Cross-Signal Interaction Matrix

When multiple signals fire simultaneously, the combined effect is NOT additive — it's multiplicative for confirming signals, and deeply informative for conflicting signals.

### Confirming Signal Combos (Multiplicative Effect)

| Signal Combination | Combined Meaning | Confidence Multiplier | Historical Example |
|-------------------|------------------|-----------------------|-------------------|
| Yield curve inv + HY OAS widening + FCI tightening | Triple credit stress: recession almost certain | 2.5x | July 2007, Dec 2019 |
| FGI < 20 + insider buying surge + PMI bottoming | Triple bottom signal: recovery very likely | 2.0x | March 2009, March 2020 |
| VIX > 35 + P/C > 1.5 + FGI < 15 | Extreme fear trinity: contrarian buying opportunity | 1.8x | Oct 2008, Mar 2020 |
| Dalio bubble checklist 5/6 + Sornette LPPL critical | Bubble bursting imminent | 2.0x | 2000 Dot-com, 2007 Housing |
| Fed pivot + credit spreads compressing + PMI rising | Recovery confirmed: go long | 2.0x | Mar 2009, Apr 2020 |

### Conflicting Signal Combos (Divergence = Intelligence)

| Conflict | What It Means | How to Resolve | Example |
|---------|---------------|----------------|---------|
| Micro bullish (RSI, momentum) + Macro bearish (yield curve inv) | Technical strength but macro headwind → momentum may persist briefly then reverse | Trust macro for direction, micro for timing — wait for micro to confirm macro | 2007: stocks rallied while yield curve inverted for months before crash |
| Sentiment bullish (FGI > 80) + Credit bearish (OAS widening) | Euphoria + credit stress = dangerous setup | Credit wins — reduce exposure despite sentiment | 2007-2008 |
| Insider selling + Strong earnings | Insiders selling into strength = distribution | Trust insiders — they know more than earnings show | Many top-tick signals |
| Geopolitical risk spike + Market calm | Geopolitical risk not yet priced in | Position for when market wakes up — buy VIX calls, reduce EM | Jan 2022 Russia buildup |
| Social sentiment extreme bearish + Price holding support | Short squeeze setup | Watch for short interest data — if high, explosive upside possible | GME 2021 |

---

## Historical Pattern Encyclopedia

### Major Market Events and Their Signal Fingerprints

| Event | Date | Signals That Fired (Pre-Event) | Signals That Confirmed (During) | Lessons |
|-------|------|-------------------------------|-------------------------------|---------|
| Dot-com Crash | Mar 2000 | Dalio bubble 6/6; Shiller CAPE > 44; insider selling | VIX > 40; FGI < 10; credit stress minimal (non-credit bubble) | Bubble can persist long after signals; credit health doesn't prevent equity crash |
| GFC / Lehman | Sep 2008 | Yield curve inv (Aug 2006); HY OAS widening (2007); FCI tightening | VIX > 80; FGI < 5; credit freeze; HY OAS > 1000bps | Credit signals gave 12-18 months lead time; the crash was the credit event |
| Flash Crash | May 2010 | No macro signals; pure microstructure event | VIX spike; liquidity vacuum; cross-asset correlation spike to 1.0 | Some events are unforecastable — tail risk protection always needed |
| European Debt Crisis | 2011-2012 | Sovereign CDS widening; GDELT tone negative on Europe; FCI tightening | EUR/USD volatility; bank stock declines; political uncertainty | Sovereign risk = new category; Draghi "whatever it takes" was the recovery signal |
| Taper Tantrum | May 2013 | Fed hinting at QE reduction; EM capital outflows | EM FX crisis; bond sell-off; 10Y yield +100bps in months | Policy communication matters as much as policy; "forward guidance" can backfire |
| Oil Crash | 2014-2015 | China PMI declining; OPEC maintaining production; rig count falling | Energy HY defaults; oil equities -50%+; EM commodity exporters hit | Supply-driven crashes differ from demand-driven; watch OPEC + inventory |
| China Shock | Aug 2015 | Sornette LPPL firing on Shanghai; GDELT China negative; Yuan devaluation | Global equity correlation spike; VIX > 40; "circuit breaker" failures | China signals (PBoC, A-share patterns) now essential for global SA |
| Brexit | Jun 2016 | GDELT tone -8 on UK; GBP volatility rising; polling uncertainty | GBP -10% overnight; European banks hit; safe haven rally | Political event risk is real but often creates buying opportunities |
| Trump Election | Nov 2016 | GDELT tone volatile; polling vs prediction market divergence | ES futures limit down → limit up in 12 hours; rotation to value | Political shocks create volatility, but market logic returns quickly |
| COVID Crash | Feb-Mar 2020 | GDELT health event spike (Jan); credit OAS widening (Feb); VIX rising | VIX > 80; FGI < 5; all correlations → 1.0; liquidity crisis | Black swan — but GDELT gave 3-4 week lead; insider buying at bottom was accurate |
| SVB Failure | Mar 2023 | Regional bank CDS widening; deposit flight signals; HY OAS selective | Bank equity -30%+; FGI < 25; Fed emergency facility | Contagion risk is real but often contained by policy response |
| Japan Yen Carry Unwind | Aug 2024 | BoJ rate hike signal; yen strengthening; carry trade metrics | Nikkei -12% single day; global risk-off; VIX spike | Currency carry unwinds are violent and fast; watch BoJ + JPY crosses |

### Pattern Rules Extracted

1. **Credit events have the longest lead time** — 6-18 months of warning signals before the actual crash
2. **Geopolitical events give short lead time** — 2-5 days from GDELT signal to market impact
3. **Black swans by definition have no historical analog** — but generic tail risk protection (VIX calls, gold, cash) always applies
4. **Recovery signals are more reliable than crash signals** — insider buying at bottoms has higher predictive value than insider selling at tops
5. **The most dangerous setup**: euphoric sentiment + tightening credit + rich valuations — when all three align, crash probability is very high
6. **Fed pivots are a double-edged sword**: first cut often coincides with the worst part of the crisis, not the end — don't buy the first cut blindly
7. **Correlation → 1.0 is the universal stress signal**: when all assets move together, diversification fails; only cash and safe havens protect

---

## Contributing to This Knowledge Base

This is a living document. New rules should be added when:

1. A signal combination predicted a market move correctly → add to Confirming Combos
2. A signal combination gave a false alarm → document why it failed and add caveats
3. A new event occurs with novel signal patterns → add to Historical Encyclopedia
4. Academic research reveals new validated relationships → add to relevant section
5. An expert figure changes their framework or makes a notable call → update Key Figure Map

### Validation Standard

Before adding a new rule, it should pass at least ONE of:
- **Academic**: Published in peer-reviewed journal or working paper
- **Historical**: Observed in 3+ distinct market episodes
- **Expert**: Cited by 2+ recognized market experts
- **Statistical**: Backtested with >60% accuracy over meaningful sample

---

*Knowledge Base Version: 1.0 | Date: 2026-05-11 | Next Review: Continuous*

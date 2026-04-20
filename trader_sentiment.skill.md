# SKILL: Trader Sentiment — Analyst Views & Famous Traders

**Trigger:** User asks "what do analysts say," "trader views," "JPMorgan forecast," "what are experts saying about gold."

**Purpose:** Aggregate current views from major banks, institutional analysts, and famous traders to build sentiment consensus.

---

## Sources to Monitor (in priority order)

### Tier 1: Major Investment Banks
1. **JPMorgan** — Watch Gregory Shearer (Head of Base and Precious Metals Strategy). Known for detailed Q-by-Q forecasts.
2. **Goldman Sachs** — Commodities team, year-end targets
3. **UBS** — Precious metals desk
4. **Bank of America** — Metals strategy
5. **Morgan Stanley** — Gold outlook reports
6. **Citi** — Commodities research

### Tier 2: Specialized Institutions
7. **World Gold Council (WGC)** — Gold Outlook reports, GRAM model
8. **LBMA** — London Bullion Market Association
9. **Metals Focus** — Supply/demand research
10. **CPM Group** — Gold analytics

### Tier 3: Asset Managers
11. **VanEck** — Gold Investing Outlook
12. **State Street / SPDR Gold** — Monthly Gold Monitor
13. **WisdomTree** — Gold + Bitcoin analysis
14. **PIMCO** — Real yields framework

### Tier 4: Indian-Specific
15. **Kitco News** — Daily commentary
16. **MCX India** — Indian futures data
17. **IBJA (India Bullion and Jewellers Association)** — Daily benchmarks
18. **Motilal Oswal, HDFC Securities, Kotak** — Indian brokerage views
19. **World Gold Council India** — Regional data

### Tier 5: Independent Analysts
20. **Peter Schiff** — Perennial gold bull
21. **Jim Rickards** — Macro-gold analyst
22. **Ray Dalio (Bridgewater)** — "Gold in a portfolio" framework

---

## Workflow

### Step 1: Search for Latest Views
Use web_search with queries like:
- "JPMorgan gold price forecast 2026"
- "Goldman Sachs gold target"
- "World Gold Council outlook [current month]"
- "Kitco gold news India today"
- "MCX gold analysis [current date]"

### Step 2: Extract Key Data Points
For each analyst, capture:
- **Name & institution**
- **Current price target** (with timeframe)
- **Key reasoning** (2-3 bullet points)
- **Date of the view** (must be recent — ignore anything older than 1 month)
- **Bullish / Bearish / Neutral stance**

### Step 3: Build Sentiment Table

| Analyst | Institution | Target | Timeframe | Stance | Key Reason |
|---------|-------------|--------|-----------|--------|------------|
| G. Shearer | JPMorgan | $5,055/oz | Q4 2026 | Bullish | Central bank demand |
| ... | ... | ... | ... | ... | ... |

### Step 4: Calculate Consensus
- **Average price target** = mean of all targets
- **Bullish %** = (number of bullish analysts / total) × 100
- **Bearish %** = (number of bearish / total) × 100
- **Consensus stance** = majority view

### Step 5: Identify Divergence
- **Highest target** and who holds it
- **Lowest target** and who holds it
- **Biggest contrarian** — worth noting

### Step 6: Weight the Consensus
- JPMorgan, Goldman, WGC = higher weight (3x)
- Other banks = standard weight (2x)
- Independents = lower weight (1x)
- Retail sentiment = lowest weight (0.5x)

---

## Output Format

```markdown
## 🗣️ ANALYST SENTIMENT SNAPSHOT — [Date]

### Consensus
- **Average target (12-month):** $X,XXX/oz  (≈ ₹XX,XXX per 10g)
- **Consensus view:** [BULLISH / BEARISH / MIXED]
- **Bullish analysts:** XX%
- **Bearish analysts:** XX%

### Top Voices
**🟢 Most Bullish:** [Name, institution, target]
> "Quote or key reasoning..."

**🔴 Most Bearish:** [Name, institution, target]
> "Quote or key reasoning..."

**⚖️ Consensus (JPMorgan / Goldman / WGC):**
- JPMorgan: $X,XXX/oz target — [reasoning]
- Goldman: $X,XXX/oz target — [reasoning]
- WGC: [scenario-based view]

### Indian Market Specific
- MCX forecast: ₹XX,XXX per 10g
- Key Indian analyst view: [Name + brief]

### Signal for Gold Tracker
Based on sentiment, assign score:
- Strongly bullish consensus = +2
- Mildly bullish = +1
- Mixed = 0
- Mildly bearish = −1
- Strongly bearish = −2
```

---

## Red Flags to Watch

1. **Sudden shift in consensus** — when multiple big banks change view in same week, expect volatility
2. **Extreme optimism/pessimism** — historically, peak consensus = near-term reversal
3. **Contrarian whales** — when a major fund manager breaks with consensus, investigate why
4. **Stale forecasts** — targets from 6+ months ago should be discounted heavily

---

## Key Traders' Known Frameworks

### Ray Dalio — "All Weather Portfolio"
- Allocates ~7.5% to gold
- Triggers: inflation, currency debasement, geopolitical stress

### Paul Tudor Jones
- Treats gold as "store of value against money printing"
- Often allocates 5-10%

### Stanley Druckenmiller
- Gold as currency alternative
- Triggers: Fed policy, dollar weakness

### Peter Schiff
- Perma-bull on gold
- Treat views with grain of salt — but useful for bearish-dollar arguments

### Jeffrey Currie (formerly Goldman)
- Commodity super-cycle framework
- Central bank reserves, de-dollarization

---

## Common Pitfalls

- ❌ Don't rely on a single analyst — build consensus
- ❌ Don't ignore contrarians — they often spot turning points
- ❌ Don't quote outdated targets — check date always
- ❌ Don't confuse short-term trader calls with long-term analyst targets
- ❌ Don't miss Indian-specific views — global forecasts don't capture import duty + INR dynamics

# SKILL: Gold Analysis — Full Prediction Workflow

**Trigger:** User asks "should I buy gold," "predict gold price," "gold forecast," or any general question about where gold is heading.

**Purpose:** Run the complete 7-step prediction workflow and output a full Gold Tracker report.

---

## Step-by-Step Instructions

### Step 1: Fetch Current Market Data
Use web_search with these queries:
- "MCX gold price today 24K 22K"
- "XAU USD current price"
- "USD INR today"
- "India gold price today [current date]"

**Extract and record:**
- MCX 24K per 10g (INR)
- MCX 22K per 10g (INR)
- Spot gold XAU/USD per oz
- USD/INR rate
- Previous close and % change

### Step 2: Fetch Latest News (last 48 hours)
Use web_search:
- "gold price news today"
- "Fed rate decision gold"
- "central bank gold buying news"
- "geopolitical tension gold impact"

List top 5 relevant news items.

### Step 3: Score All 18 Factors
Open `factors_reference.md`. For each of the 18 factors:
1. Check current state from recent news/data
2. Assign score: +2 / +1 / 0 / −1 / −2
3. Multiply by weight (3x, 2x, 1.5x, 1x, 0.5x)

Create a table:

| # | Factor | Score | Weight | Weighted |
|---|--------|-------|--------|----------|
| F1 | Inflation | +1 | 3x | +3 |
| F2 | Real Rates | +2 | 3x | +6 |
| ... | ... | ... | ... | ... |
| | **TOTAL** | | | **XX** |

### Step 4: Calculate Probability
Convert weighted score to probability using the table in `factors_reference.md`:

- Weighted score → Probability of RISE
- Probability of FALL = 100 − Rise%
- Probability of SIDEWAYS = subtract 10-20% from both if signals conflict

### Step 5: Set Price Targets

**Today's range:**
- If bullish: Current price to Current + 0.5% to 1.5%
- If bearish: Current price minus 0.5% to 1.5%
- If neutral: ±0.3%

**This week's range:**
- If bullish: Current + 1% to 3%
- If bearish: Current − 1% to 3%
- If neutral: ±0.5%

**This month's range:**
- If bullish: Current + 3% to 8%
- If bearish: Current − 3% to 8%
- If neutral: ±2%

**Adjust ranges based on volatility:** In high-volatility periods (major news, Fed meetings), widen ranges by 50%.

### Step 6: Generate Recommendation

| Weighted Score | Action | Confidence |
|----------------|--------|------------|
| +30 to +45 | STRONG BUY | High |
| +15 to +29 | BUY | Medium-High |
| +5 to +14 | MILD BUY / HOLD | Medium |
| −4 to +4 | HOLD | Medium |
| −5 to −14 | REDUCE / HOLD | Medium |
| −15 to −29 | SELL | Medium-High |
| −30 to −45 | STRONG SELL | High |

### Step 7: Set Stop-Loss and Target
- **Stop-loss:** 2-3% below current price (tighter for short-term trades, wider for long-term holds)
- **Profit target:** Based on weekly/monthly projection upper bound
- **Risk-to-reward ratio:** Always aim for 1:2 minimum (risk 1 rupee to make 2)

### Step 8: Format Output
Use the STANDARD OUTPUT FORMAT from `project_instructions.md`.

---

## Example Walkthrough

**User asks:** "Should I buy gold today?"

**Claude workflow:**
1. Searches current MCX price → ₹78,450 per 10g (24K)
2. Checks news → Fed signals rate cut, Iran tensions rising
3. Scores factors → +27 (moderate bullish)
4. Probability → 68% rise, 22% fall, 10% sideways
5. Targets:
   - Today: ₹78,200 – ₹79,000
   - Week: ₹79,500 – ₹81,200
   - Month: ₹80,000 – ₹84,500
6. Recommendation: **BUY** (Medium-High confidence)
7. Stop-loss: ₹76,500 | Target: ₹82,000
8. Outputs full report.

---

## Critical Rules

- **Never skip steps 1 and 2.** Always fetch live data.
- **Never say "I cannot predict."** Give a probabilistic view.
- **Always show your math.** Users must see the factor table.
- **Always include stop-loss.** Risk management is non-negotiable.
- **Use INR for everything.** Only mention USD for reference.

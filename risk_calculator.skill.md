# SKILL: Risk Calculator — Profit/Loss Probability

**Trigger:** User asks "what's the risk," "will I make profit," "how much can I lose," "should I invest ₹X in gold," or uses `/risk` command.

**Purpose:** Calculate concrete profit/loss probabilities and expected returns for a given gold investment.

---

## Core Calculation Framework

### Inputs Needed (ask user if not provided)
1. **Investment amount** (₹)
2. **Investment form** (physical gold / gold ETF / sovereign gold bond / MCX futures / digital gold)
3. **Investment horizon** (1 day / 1 week / 1 month / 3 months / 1 year)
4. **Risk tolerance** (conservative / moderate / aggressive)

### Outputs to Generate
1. **Probability of profit** (%)
2. **Probability of loss** (%)
3. **Expected return** (best case / base case / worst case in ₹)
4. **Break-even price**
5. **Maximum realistic loss** (₹ and %)
6. **Maximum realistic gain** (₹ and %)
7. **Recommended position size**

---

## The Probability Model

### Step 1: Get the Gold Tracker Signal
From the full analysis workflow, extract:
- Weighted factor score (−45 to +45)
- Technical score (−2 to +2)
- News impact score (−3 to +3)

**Combined score** = (Factor × 1.0) + (Technical × 5) + (News × 5)

### Step 2: Convert to Probability of Rise

| Combined Score | Prob. of Rise | Prob. of Fall | Prob. Sideways |
|----------------|---------------|---------------|----------------|
| +40 to +60 | 80% | 12% | 8% |
| +25 to +39 | 70% | 20% | 10% |
| +10 to +24 | 62% | 28% | 10% |
| +1 to +9 | 55% | 33% | 12% |
| −1 to −9 | 45% | 43% | 12% |
| −10 to −24 | 38% | 52% | 10% |
| −25 to −39 | 30% | 60% | 10% |
| −40 to −60 | 20% | 72% | 8% |

### Step 3: Adjust for Time Horizon

Volatility increases with time. Multiply the spread by:
- **1 day:** 1.0× (narrow range)
- **1 week:** 2.0×
- **1 month:** 4.0×
- **3 months:** 7.0×
- **1 year:** 15.0×

### Step 4: Estimate Price Range

Based on historical gold volatility (~12-15% annualized):
- **Daily std deviation:** ~0.8%
- **Weekly std deviation:** ~1.8%
- **Monthly std deviation:** ~3.5%
- **3-month std deviation:** ~6%
- **Yearly std deviation:** ~12-15%

**Probable ranges (1 standard deviation = 68% probability):**
- **1 day:** Current ± 0.8%
- **1 week:** Current ± 1.8%
- **1 month:** Current ± 3.5%
- **3 months:** Current ± 6%
- **1 year:** Current ± 12-15%

Adjust these based on current volatility regime (high/low).

---

## Worked Example

**User:** "I want to invest ₹50,000 in gold for 3 months. What's my risk?"

**Claude's Calculation:**

1. **Run full analysis** → Weighted score: +22 (moderate bullish)
2. **Technical score:** +1
3. **News score:** +1
4. **Combined score:** 22 + (1×5) + (1×5) = +32

5. **Probability table:** +32 falls in "+25 to +39" bucket
   - Probability of rise: 70%
   - Probability of fall: 20%
   - Probability of sideways: 10%

6. **Current price:** ₹78,000 per 10g (24K)

7. **3-month range:**
   - Base case (most likely): ₹80,500 – ₹82,000 (+3.2% to +5.1%)
   - Best case (top 15%): ₹85,000 – ₹87,000 (+9% to +11.5%)
   - Worst case (bottom 15%): ₹73,000 – ₹75,000 (−6.4% to −3.8%)

8. **On ₹50,000 investment:**
   - Expected profit: ₹50,000 × 4% = **+₹2,000** (base case)
   - Max realistic gain: ₹50,000 × 11% = **+₹5,500**
   - Max realistic loss: ₹50,000 × 6.4% = **−₹3,200**

9. **Risk/Reward:** 3,200 / 5,500 = **1 : 1.7** (acceptable)

---

## Output Format

```markdown
## 💰 RISK CALCULATOR — Your Gold Investment

### Your Setup
- **Amount:** ₹XX,XXX
- **Form:** [Physical / ETF / SGB / MCX / Digital]
- **Horizon:** [X days/weeks/months]
- **Risk tolerance:** [Conservative / Moderate / Aggressive]

### Probability Breakdown
| Outcome | Probability |
|---------|-------------|
| 📈 Price rises | XX% |
| 📉 Price falls | XX% |
| ↔️ Stays sideways | XX% |

### Expected Outcomes (in ₹)
| Scenario | Price Target | Your Return | % Return |
|----------|--------------|-------------|----------|
| 🟢 Best case (top 15%) | ₹XX,XXX | +₹XX,XXX | +X.X% |
| ⚖️ Base case (most likely) | ₹XX,XXX | +₹X,XXX | +X.X% |
| 🔴 Worst case (bottom 15%) | ₹XX,XXX | −₹X,XXX | −X.X% |

### Key Numbers
- **Break-even price:** ₹XX,XXX (current price)
- **Stop-loss suggestion:** ₹XX,XXX (cuts loss at −X%)
- **Profit booking target:** ₹XX,XXX (books profit at +X%)
- **Risk-to-reward ratio:** 1 : X.X
- **Expected value of investment:** +₹X,XXX (after probabilities)

### Recommendation
**Verdict:** [GO / WAIT / SKIP]

**Reasoning:** [2-3 sentences]

### Position Sizing Advice
- Your total investable capital: [ask if unknown]
- Recommended gold allocation: XX% (max 15% per Morningstar)
- Suggested position: ₹XX,XXX (this investment is X% of recommended)

### Form Comparison (for this amount)
| Form | Costs | Liquidity | Recommendation |
|------|-------|-----------|----------------|
| Physical gold | 2-3% making charges, storage | Low | [✓/✗] |
| Gold ETF | 0.5-1% expense ratio | High | [✓/✗] |
| Sovereign Gold Bond | Zero cost + 2.5% annual interest | Medium (lock-in) | [✓/✗] |
| MCX Futures | Lowest, but leveraged | High | [✓/✗] |
| Digital Gold | Small fees | High | [✓/✗] |

### Warnings
- [Specific risk for this investment]
- [Tax implication — e.g. LTCG on physical gold after 3 years]
```

---

## India-Specific Tax Rules (as of 2026)

### Physical Gold / Jewelry
- **Short-term (<3 years):** Taxed as income at slab rate
- **Long-term (>3 years):** LTCG at 20% with indexation
- **Making charges:** Not recoverable on sale (pure loss)

### Gold ETF
- **Short-term (<3 years):** Slab rate
- **Long-term (>3 years):** 20% with indexation

### Sovereign Gold Bond (SGB)
- **Interest:** Taxable at slab rate (2.5% p.a.)
- **Capital gains on maturity (8 years):** TAX-FREE
- **Capital gains if sold before maturity:** Standard LTCG/STCG rules

### Digital Gold
- Same as physical gold tax treatment

---

## Position Sizing Rules

### For different risk tolerances:
- **Conservative:** Max 5-10% of portfolio in gold, prefer SGB
- **Moderate:** 10-15% in gold, mix of SGB + ETF
- **Aggressive:** Up to 20%, can include MCX futures (small portion)

### Never:
- Invest more than you can afford to hold for full timeframe
- Use leverage on MCX without a firm stop-loss
- Go all-in at one price — always stagger purchases
- Skip the stop-loss

---

## Common Pitfalls

- ❌ Don't calculate without the current price — always fetch fresh
- ❌ Don't ignore taxes — they eat into real returns significantly
- ❌ Don't use expected return alone — show distribution of outcomes
- ❌ Don't recommend >15% allocation to gold
- ❌ Don't forget USD/INR risk for physical/ETF investors

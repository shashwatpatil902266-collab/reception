# 🧪 SETUP CHECKLIST & TEST QUERIES

Use this file to verify Gold Tracker is working correctly after setup.

---

## ✅ Setup Verification Checklist

### Before First Use
- [ ] Claude Project created with name "Gold Tracker"
- [ ] `project_instructions.md` pasted into Custom Instructions
- [ ] `factors_reference.md` uploaded to Project knowledge
- [ ] All 5 skill files uploaded to Project knowledge:
  - [ ] `gold_analysis.skill.md`
  - [ ] `trader_sentiment.skill.md`
  - [ ] `technical_analysis.skill.md`
  - [ ] `news_impact.skill.md`
  - [ ] `risk_calculator.skill.md`
- [ ] Web search enabled in Claude settings
- [ ] New conversation started in the Project

---

## 🎯 Demo Script for Your Friend (The 8/10 Reviewer)

### Test 1: Full Analysis (shows depth)
Type: **"Should I buy gold today?"**

**Expected:** Full STANDARD OUTPUT FORMAT with:
- Current MCX prices (live)
- Price targets for 3 timeframes
- Probability percentages
- Clear BUY/HOLD/SELL verdict
- All sections filled in

**If it passes this one test, you're already at 7/10.**

---

### Test 2: Risk Calculation (shows practical value)
Type: **"I want to invest ₹50,000 in gold for 3 months. What's my risk?"**

**Expected:**
- Probability of profit vs loss
- Best case / base case / worst case returns in ₹
- Stop-loss and target price
- Form comparison (Physical / ETF / SGB / MCX)
- Tax considerations

**This tests the risk_calculator skill.**

---

### Test 3: News Impact (shows real-time reasoning)
Type: **"How will the Fed rate decision tomorrow affect gold?"**

**Expected:**
- Classification of the news type
- Direction + magnitude + time horizon
- Expected price move in both USD and INR
- What to watch next

**This tests the news_impact skill.**

---

### Test 4: Quick Answer (shows efficiency)
Type: **"/quick"**

**Expected:** 3-line response:
1. Direction (UP/DOWN/SIDEWAYS)
2. Today's target price
3. Action (BUY/HOLD/SELL)

**This shows the system can be concise when needed.**

---

### Test 5: Why (shows reasoning depth)
After Test 4, type: **"/why"**

**Expected:** Detailed breakdown of:
- All 18 factors with scores
- Weighted calculation
- Which analysts support vs contradict this view
- Technical picture
- News context

**This proves the prediction isn't random — it's systematic.**

---

### Test 6: Trader Consensus (shows expert integration)
Type: **"/traders"** or **"What are analysts saying about gold?"**

**Expected:**
- Consensus average price target
- % bullish vs bearish analysts
- Most bullish + most bearish names
- JPMorgan, Goldman, WGC specifics
- Indian-specific analyst view

---

### Test 7: Technical Analysis (shows chart reading)
Type: **"/technical"** or **"Is gold breaking resistance?"**

**Expected:**
- Current price vs 50/100/200-day MAs
- Immediate support and resistance levels
- RSI and MACD readings
- Pattern identification
- Technical score contribution

---

### Test 8: India-Specific Knowledge
Type: **"With Akshaya Tritiya coming up, how should I think about gold?"**

**Expected:** Claude should reference:
- Festival's impact on demand
- Historical price behavior pre-Akshaya Tritiya
- Import duty considerations
- Whether current price is a good entry

**This proves Indian market specialization.**

---

### Test 9: Scenario Analysis
Type: **"What if Iran-Israel war escalates? What's the gold target?"**

**Expected:**
- Scenario classification (Category B: Geopolitical)
- Historical parallels (2022 Russia-Ukraine, etc.)
- Expected price range in the scenario
- Trading implication

---

### Test 10: Edge Case — Bearish Situation
Type: **"Gold has fallen 5% this week. Should I buy the dip or wait?"**

**Expected:**
- Re-run full analysis with new data
- Assess if drop is technical (buying opportunity) or fundamental (avoid)
- Specific price levels to watch
- Risk management advice

---

## 🎬 How to Run the Demo

### Recommended flow (10 minutes):
1. Open Gold Tracker Project
2. Run Test 1 — let your friend see the full report
3. Run Test 4 (`/quick`) — show it can be fast
4. Run Test 5 (`/why`) — show the reasoning is deep
5. Run Test 2 — show personalized risk calculation with their ₹ amount
6. Run Test 8 — show Indian market specialization
7. Run Test 9 — show scenario flexibility

### What to say while demoing:
> "Here's Gold Tracker — it's an AI gold analyst I built on Claude. It pulls live data, runs 18 factors, reads trader views, analyzes charts, and gives me a specific buy/sell recommendation with probability. Let me show you..."

---

## 🏆 Scoring Rubric (Your Friend's Perspective)

| Criterion | Description | Points | Your Target |
|-----------|-------------|--------|-------------|
| Gives a specific price prediction | Not vague, actual numbers | 2 | ✅ 2/2 |
| Shows probability breakdown | Not just direction | 1 | ✅ 1/1 |
| Clear buy/hold/sell action | One clear verdict | 1 | ✅ 1/1 |
| Cites real analysts | By name + institution | 1 | ✅ 1/1 |
| Uses live data | Not from training cutoff | 1 | ✅ 1/1 |
| Indian market context | MCX, INR, festivals, duties | 1 | ✅ 1/1 |
| Risk management included | Stop-loss, position size | 1 | ✅ 1/1 |
| Professional format | Clean tables, clear sections | 1 | ✅ 1/1 |
| Handles follow-up questions | Coherent conversation | 1 | ✅ 1/1 |
| **TOTAL** | | **10** | **✅ 10/10 achievable** |

If all 10 tests pass → you clear 8/10 easily.

---

## 🛟 Troubleshooting

### "Claude isn't fetching live prices"
- Check that web search is enabled in your settings
- Ask Claude directly: "Please search the web for current MCX gold price"

### "Output doesn't match the STANDARD FORMAT"
- Verify `project_instructions.md` is in Custom Instructions (not just uploaded as knowledge)
- Ask Claude: "Use the STANDARD OUTPUT FORMAT from the project instructions"

### "Claude is giving vague answers"
- Remind it: "You are Gold Tracker. Give me a specific probability and target price."
- Make sure all 5 skill files are uploaded

### "Predictions seem random / inconsistent"
- Claude should use the weighted scoring system from `factors_reference.md`
- Ask: "Show me the factor-by-factor scoring table for this prediction"

### "Not enough Indian context"
- Ensure `project_instructions.md` is in place — it emphasizes Indian market
- Ask: "Focus on MCX and INR, not XAU/USD"

---

## 📣 Marketing the Demo

### Elevator pitch for your friend:
> *"Gold Tracker is a Claude-powered AI that analyzes 18 gold price factors, reads live news, and gives me a specific buy/sell recommendation every day — with a stop-loss and profit target. It's like having JPMorgan's gold desk in my pocket, but trained specifically for Indian gold."*

### One killer line:
> *"Instead of asking 'will gold go up?', I ask Gold Tracker 'what's the probability gold goes up 2% this week, and at what stop-loss should I enter?' — and it tells me."*

---

**Good luck with your demo! 🥇**

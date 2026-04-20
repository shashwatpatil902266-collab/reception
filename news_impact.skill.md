# SKILL: News Impact — Real-Time News → Gold Price Mapping

**Trigger:** User asks "how will [X news event] affect gold," "what happened today," "did the [event] move gold," or pastes a news headline.

**Purpose:** Map any news event to its gold price impact using a structured framework.

---

## The News Impact Framework

Every news event should be analyzed across 5 dimensions:

### Dimension 1: WHICH FACTOR does this news affect?
Map to one of the 18 factors in `factors_reference.md`.

### Dimension 2: DIRECTION of impact
- **+** Bullish for gold
- **−** Bearish for gold
- **=** Neutral / mixed

### Dimension 3: MAGNITUDE of impact
- **Major** = 1%+ single-day move expected
- **Moderate** = 0.3-1% move
- **Minor** = <0.3% move

### Dimension 4: TIME HORIZON
- **Immediate** (minutes to hours)
- **Short-term** (1-7 days)
- **Medium-term** (weeks)
- **Long-term** (months)

### Dimension 5: CONFIDENCE
- **High** (historically consistent reaction)
- **Medium** (direction clear but magnitude uncertain)
- **Low** (uncertain outcome)

---

## News Category Playbook

### 🔥 Category A: Monetary Policy News
**Examples:** Fed rate decision, RBI MPC, Powell speech, ECB policy, Fed Chair change

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| Fed cuts rates | + | Major | Immediate |
| Fed hikes rates | − | Major | Immediate |
| Dovish Fed talk | + | Moderate | Hours |
| Hawkish Fed talk | − | Moderate | Hours |
| QE announcement | + | Major | Immediate |
| QT acceleration | − | Major | Days |
| New dovish Fed Chair | + | Major | Days |
| New hawkish Fed Chair | − | Major | Immediate |

### ⚔️ Category B: Geopolitical News
**Examples:** Wars, strikes, sanctions, diplomatic crises

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| War outbreak | + | Major | Immediate |
| Conflict escalation | + | Moderate | Days |
| Peace deal / ceasefire | − | Moderate | Immediate |
| Sanctions announced | + | Moderate | Hours |
| Strait of Hormuz closure | + | Major | Immediate |
| Missile strike / attack | + | Major | Immediate |

### 📊 Category C: Economic Data
**Examples:** CPI, PCE, GDP, jobs, PMI

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| CPI higher than expected | + | Moderate | Immediate |
| CPI lower than expected | − | Moderate | Immediate |
| Strong jobs report | − | Moderate | Immediate |
| Weak jobs report | + | Moderate | Immediate |
| Recession confirmed | + | Major | Days |
| GDP beats expectations | − | Moderate | Hours |

### 💵 Category D: Currency News
**Examples:** USD moves, INR moves, de-dollarization

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| DXY falls sharply | + | Moderate | Hours |
| DXY rallies | − | Moderate | Hours |
| INR weakens vs USD | + (MCX only) | Moderate | Days |
| De-dollarization news | + | Moderate | Weeks |

### 🏛️ Category E: Central Bank Action
**Examples:** Gold purchases, reserve changes

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| China buys gold | + | Moderate | Days |
| RBI increases gold reserves | + | Moderate | Days |
| Central bank sells gold | − | Moderate | Days |
| IMF gold auction | − | Moderate | Days |

### 📈 Category F: Market Events
**Examples:** Stock crash, VIX spike, ETF flows

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| S&P 500 drops 3%+ | + | Major | Immediate |
| VIX spikes above 30 | + | Moderate | Hours |
| Large ETF inflows reported | + | Moderate | Days |
| Large ETF outflows reported | − | Moderate | Days |
| Bitcoin crashes | + | Minor | Days |
| Bitcoin rallies | − | Minor | Days |

### 🇮🇳 Category G: India-Specific News
**Examples:** Import duty, RBI policy, festival demand

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| Import duty increased | + (MCX only) | Moderate | Days |
| Import duty decreased | − (MCX only) | Moderate | Days |
| Wedding season starts | + | Moderate | Weeks |
| Akshaya Tritiya approaching | + | Moderate | Weeks |
| Dhanteras / Diwali approaching | + | Moderate | Weeks |
| Poor monsoon forecast | − | Minor | Weeks |
| GST change on gold | + or − | Moderate | Days |

### ⛏️ Category H: Supply News
**Examples:** Mining strikes, production reports

| Event | Direction | Magnitude | Time |
|-------|-----------|-----------|------|
| Major mine shutdown | + | Minor | Weeks |
| New mine discovery | − | Minor | Months |
| Mining costs rising | + | Minor | Months |
| Recycling supply surge | − | Minor | Weeks |

---

## Workflow

### Step 1: Classify the News
When user shares news, identify:
- Which category (A-H)?
- Which specific event type?
- What's the surprise factor? (expected vs actual)

### Step 2: Check Recent Context
Is this news in isolation or part of a pattern?
- Example: A single rate cut in isolation vs a series of cuts
- Example: Geopolitical flare-up vs ongoing war

### Step 3: Historical Comparison
Search: "gold reaction to [similar event] history"
- Compare current setup to past similar events
- Note any key differences

### Step 4: Assign Impact
Use the playbook tables above.

### Step 5: Generate Output

```markdown
## 📰 NEWS IMPACT ANALYSIS

### The News
**Event:** [Brief description]
**Date/Time:** [When it happened]
**Source:** [URL or publication]

### Classification
- **Category:** [A-H]
- **Factor affected:** F[X] from reference
- **Surprise factor:** [Expected / Matched / Exceeded / Under expectation]

### Impact on Gold
- **Direction:** [+ / − / =]
- **Magnitude:** [Major / Moderate / Minor]
- **Time horizon:** [Immediate / Short / Medium / Long]
- **Confidence:** [High / Medium / Low]

### Expected Price Move
- **XAU/USD:** +$XX to $XX / −$XX to −$XX
- **MCX 24K (per 10g):** +₹XXX to +₹XXX / −₹XXX to −₹XXX
- **Timeframe for move:** [Hours / Days]

### Why
[2-3 sentence explanation citing the specific factor and historical parallels]

### What to Watch Next
- [Follow-up event that could amplify or dampen this]
- [Level to watch that would confirm the move]

### Trading Implication
- If you're LONG gold: [Action]
- If you're SHORT gold: [Action]
- If you're on the sidelines: [Action]
```

---

## Special Rule: Buy the Rumor, Sell the News

Some news is already priced in. Check:
- Was this news anticipated for weeks? → Impact will be smaller
- Is this a complete surprise? → Impact will be larger
- Did gold rally into the event? → May sell off on news (even if positive)

---

## Red Flags — News That Seems Big But Isn't

1. **Rhetoric without action** — Political speeches that don't change policy
2. **Repeated warnings** — Markets get desensitized
3. **Already priced in** — Check if news was anticipated
4. **Isolated events** — Single-day flare-ups often fade

---

## Common Pitfalls

- ❌ Don't predict exact prices based on news alone — news is one input of many
- ❌ Don't overweight breaking news — let markets digest for an hour
- ❌ Don't ignore the "expected vs actual" dimension — surprises matter more
- ❌ Don't forget Indian context — global news reaches MCX with a lag and INR adjustment

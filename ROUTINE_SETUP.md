# 🤖 GOLD TRACKER ROUTINE — Complete Setup Guide

**Version:** 1.0 | **Platform:** Claude Code Routines | **Cadence:** Daily

This file converts Gold Tracker from a Claude Project (manual) into a **Claude Routine** (automated) that runs on Anthropic's cloud infrastructure daily, analyzes gold prices, and sends you a full report automatically — even while you sleep.

---

## 🎯 What This Routine Will Do

Every morning at 9 AM IST (before Indian markets open strongly):
1. Fetch current MCX gold prices
2. Check XAU/USD, USD/INR, DXY
3. Read latest gold news (last 24h)
4. Score all 18 factors
5. Check analyst consensus
6. Run technical analysis
7. Calculate probability & price targets
8. Generate BUY/HOLD/SELL recommendation
9. **Send to your Gmail** (or Slack/WhatsApp)
10. **Save the report to Google Drive** for history tracking

---

## 📋 Prerequisites

### Required Subscription
- **Claude Pro** (₹1,700/month) — 5 routines/day ← Minimum
- **Claude Max** — 15 routines/day ← Better for multiple daily runs
- **Team/Enterprise** — 25 routines/day

### Required Setup
- [x] Claude Code on the web enabled (free on all paid plans)
- [ ] GitHub account (for repo storage)
- [ ] Connectors set up (see below)

---

## 🔌 Required Connectors

You need to connect these **MCP connectors** in Claude settings → Connectors **BEFORE** creating the routine:

### Essential (Must Have)
| Connector | Purpose | Where to Get It |
|-----------|---------|-----------------|
| **Gmail** | Receive daily reports | Settings → Connectors → Gmail |
| **Google Drive** | Archive historical reports | Settings → Connectors → Google Drive |
| **Web Search** | Fetch live prices & news | Built-in (already enabled) |

### Recommended (Makes It Powerful)
| Connector | Purpose | Where to Get It |
|-----------|---------|-----------------|
| **Slack** | Send alerts to your Slack channel | Settings → Connectors → Slack |
| **Notion** | Build a dashboard database | Settings → Connectors → Notion |
| **Google Calendar** | Add important events (Fed meetings, festivals) | Settings → Connectors → Calendar |

### Optional (Advanced Users)
| Connector | Purpose | Where to Get It |
|-----------|---------|-----------------|
| **Telegram Bot** | Daily push notifications | Custom MCP server |
| **WhatsApp Business API** | WhatsApp alerts | Custom MCP server |
| **Twilio SMS** | SMS alerts on big moves | Custom MCP server |

---

## 🏗️ Setup Steps

### Step 1: Create a GitHub Repository
1. Go to github.com → New repository
2. Name: `gold-tracker-routine`
3. Make it **private**
4. Initialize with README
5. Install **Claude GitHub App** on the repo

### Step 2: Push Gold Tracker Files to Repo
Copy all 11 files from Gold Tracker project into this repo:
```
gold-tracker-routine/
├── README.md
├── project_instructions.md
├── factors_reference.md
├── historical_patterns.md
├── glossary.md
└── skills/
    ├── gold_analysis.skill.md
    ├── trader_sentiment.skill.md
    ├── technical_analysis.skill.md
    ├── news_impact.skill.md
    ├── risk_calculator.skill.md
    └── indian_market.skill.md
```

### Step 3: Connect Your Connectors
1. Go to **claude.ai → Settings → Connectors**
2. Connect Gmail (authorize access)
3. Connect Google Drive (authorize access)
4. Connect Slack (optional)
5. Verify each shows "Connected" status

### Step 4: Create the Routine
1. Go to **claude.ai/code/routines**
2. Click **"Create Routine"**
3. **Name:** `Gold Tracker Daily Brief`
4. **Repository:** Select `gold-tracker-routine`
5. **Prompt:** Paste the prompt from `DAILY_ROUTINE_PROMPT.md` (see below)
6. **Trigger:** Schedule → Daily → 9:00 AM IST
7. **Connectors:** Select Gmail + Google Drive + Web Search
8. Click **Create**

### Step 5: Test with "Run Now"
1. Click the "Run Now" button on the routine
2. Wait 3-5 minutes for completion
3. Check your Gmail for the report
4. Verify Google Drive has the archived copy

---

## 📝 THE ROUTINE PROMPT (Copy This Exactly)

Save the following as the **prompt** for your routine. This is the complete instruction set Claude will follow every time the routine runs:

```
You are Gold Tracker, a professional Indian gold market analyst.

READ THESE FILES FROM THE REPOSITORY BEFORE ANALYZING:
- project_instructions.md (your core behavior)
- factors_reference.md (18 factors to score)
- skills/gold_analysis.skill.md (7-step workflow)
- skills/trader_sentiment.skill.md (analyst sources)
- skills/technical_analysis.skill.md (chart analysis)
- skills/news_impact.skill.md (news interpretation)
- skills/risk_calculator.skill.md (probability math)
- skills/indian_market.skill.md (India-specific rules)
- historical_patterns.md (historical parallels)

TODAY'S TASK — Execute this checklist:

1. FETCH LIVE DATA (use web_search):
   - MCX Gold 24K price per 10g (INR)
   - MCX Gold 22K price per 10g (INR)
   - XAU/USD spot price
   - USD/INR exchange rate
   - DXY dollar index
   - US 10-year Treasury yield
   - India 10-year G-Sec yield

2. FETCH NEWS (use web_search):
   - Search "gold price news [today's date]"
   - Search "Fed rate decision gold latest"
   - Search "geopolitical news gold impact today"
   - Search "India gold demand news"
   - Extract top 5 most impactful items

3. RUN 18-FACTOR ANALYSIS:
   - Score each factor from factors_reference.md: -2 to +2
   - Apply weights (VERY HIGH = 3x, HIGH = 2x, MEDIUM = 1.5x, LOW-MEDIUM = 1x, LOW = 0.5x)
   - Calculate weighted total

4. CHECK ANALYST VIEWS (use web_search):
   - JPMorgan latest gold target
   - World Gold Council latest outlook
   - Any major Indian analyst view (Motilal Oswal, Kotak, HDFC Sec)
   - Compute consensus

5. DO TECHNICAL ANALYSIS:
   - Determine trend (uptrend/downtrend/sideways)
   - Identify support & resistance levels
   - Check RSI, MACD state
   - Identify any chart patterns

6. CALCULATE PROBABILITY & TARGETS:
   - Convert weighted score to probability of rise/fall
   - Set today, weekly, monthly target ranges
   - Compute stop-loss (2-3% below entry)
   - Compute target price
   - Calculate risk:reward ratio

7. GENERATE INDIA-SPECIFIC CONTEXT:
   - Check if near any festival (Akshaya Tritiya, Dhanteras, Diwali, wedding season)
   - Check USD/INR contribution to price move
   - Flag any tax/policy news

8. COMPOSE THE DAILY REPORT:
   Use the STANDARD OUTPUT FORMAT from project_instructions.md
   Include:
   - Date and time
   - Current prices snapshot
   - Price predictions (today/week/month)
   - Probability breakdown
   - BUY/HOLD/SELL recommendation with confidence
   - Top 3 bullish factors
   - Top 3 bearish factors
   - Expert consensus summary
   - Historical parallel (if applicable)
   - Risk warnings
   - Action items with stop-loss and target

9. DELIVER THE REPORT:

   A) SEND VIA GMAIL:
      - To: [YOUR_EMAIL@gmail.com]
      - Subject: "🥇 Gold Tracker Daily — [Date] — [BUY/HOLD/SELL] signal"
      - Body: Full formatted report (use HTML for nice formatting)

   B) SAVE TO GOOGLE DRIVE:
      - Folder: "Gold Tracker Reports"
      - Filename: "gold-report-YYYY-MM-DD.md"
      - Content: The complete report in markdown

   C) (OPTIONAL) POST TO SLACK:
      - Channel: #gold-alerts
      - Quick summary: current price + signal + confidence
      - Link to full report in Drive

10. UPDATE TRACKING LOG:
    - Append today's prediction to Google Drive file "gold-tracker-log.csv"
    - Columns: Date, Price, Signal, Probability_Rise, Target, Stop_Loss, Factor_Score
    - This enables backtesting accuracy over time

ERROR HANDLING:
- If web_search fails, retry 2 times
- If any connector fails, still generate the report and note which delivery failed
- Never skip the analysis even if delivery fails

SUCCESS CRITERIA:
- Report delivered to Gmail ✓
- Report archived to Drive ✓
- Log entry added ✓
- All 18 factors scored with evidence ✓
- Clear actionable recommendation given ✓

Begin now.
```

---

## 🗓️ Recommended Schedule Options

### Option A: Single Daily Report (Basic)
- **Trigger:** Daily at 9:00 AM IST
- **Use case:** One comprehensive morning brief

### Option B: Three Daily Reports (Professional)
1. **Morning Brief** — 9:00 AM IST → Overnight news + day-ahead
2. **Midday Update** — 2:00 PM IST → Asian/European session summary
3. **Evening Close** — 8:00 PM IST → US session preview + next day plan

### Option C: Event-Driven (Advanced)
- **Daily baseline** at 9:00 AM IST
- **Plus API triggers** fired by:
  - Big gold moves (>1.5% in a day)
  - Fed announcements
  - Major geopolitical events

---

## 🎚️ Multi-Routine Architecture (Professional Setup)

Create **3 separate routines** for different purposes:

### Routine 1: `Gold Daily Brief`
- Cadence: Daily 9:00 AM IST
- Purpose: Full analysis report
- Output: Gmail + Drive
- Uses: All connectors

### Routine 2: `Gold Alert Monitor`
- Cadence: Every hour during market hours (9 AM-11 PM IST)
- Purpose: Check for >1% price moves
- Output: Slack alert only if move detected
- Uses: Slack + Web Search

### Routine 3: `Weekly Gold Review`
- Cadence: Saturday 10:00 AM IST
- Purpose: Full week performance + next week outlook
- Output: Detailed PDF via Gmail
- Uses: Gmail + Drive + Web Search

---

## 🔧 Routine Configuration Details

### Environment Settings
- **Environment:** Default (Anthropic-managed cloud)
- **Network access:** Internet-enabled (for web search)
- **Setup script:** None needed (routine uses MCP tools, not local dependencies)

### Branch Protection
- Keep default: Claude can only push to `claude/*` branches
- This prevents accidental changes to main branch

### Connector Permissions
Only enable the connectors the routine actually uses:
- ✅ Gmail (for sending reports)
- ✅ Google Drive (for archiving)
- ✅ Slack (if using alerts)
- ✅ Web Search (for live data)
- ❌ Everything else (principle of least privilege)

---

## 📊 Daily Limits (Know Your Quota)

| Plan | Routines/Day | Best For |
|------|--------------|----------|
| Pro | 5 runs | 1 routine, 3-5 times/day max |
| Max | 15 runs | Multiple routines, active usage |
| Team | 25 runs | Team dashboards, many alerts |
| Enterprise | 25+ | Custom quotas available |

**Your math for Pro plan:**
- 1 daily brief = 1 run
- 3 checkpoint updates = 3 runs
- 1 weekly review = ~1/7 = negligible
- **Total: ~5 runs/day = fits Pro plan**

---

## 💰 Cost Calculation

### Claude Pro: ₹1,700/month
Includes:
- 5 routine runs/day
- Unlimited Claude Project chats (for manual queries)
- Web search included
- All connectors included

### Per-prediction cost:
- ₹1,700 / 30 days / 5 runs = **~₹11 per daily prediction**

Comparison:
- Professional gold advisory service: ₹2,000-5,000/month
- Motilal Oswal gold research: ₹3,000/month
- **Gold Tracker Routine: ₹340/month** (at 1 daily brief)

---

## 📧 Sample Email Output

Subject: `🥇 Gold Tracker Daily — April 20, 2026 — BUY signal (68% confidence)`

```
Good morning!

Here's your Gold Tracker Daily Brief for Monday, April 20, 2026.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 QUICK SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Signal: 🟢 BUY (Medium-High confidence)
Current Price: ₹1,54,605 (24K per 10g)
Today's Target: ₹1,54,200 – ₹1,55,800
Probability of Rise: 68%
Stop-Loss: ₹1,49,500
Target (1 week): ₹1,58,500

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Full analysis follows...]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Full report archived to:
Google Drive → Gold Tracker Reports → gold-report-2026-04-20.md

Have a great trading day!
— Gold Tracker AI
```

---

## 🚨 Troubleshooting

### "Routine failed to run"
- Check Claude Code web access is enabled
- Verify daily quota not exceeded
- Check connector auth hasn't expired

### "Gmail not sending"
- Re-authenticate Gmail connector in Settings
- Check spam folder
- Verify the email address in prompt is correct

### "Web search returning no data"
- Web search has internal rate limits
- Retry the routine run
- Simplify the search queries if persistent

### "Report quality dropped"
- Check if all 11 MD files are in the repo
- Verify repo is properly connected to routine
- Review recent changes to knowledge files

### "Drive archive not working"
- Create "Gold Tracker Reports" folder manually first
- Re-authenticate Drive connector
- Check folder permissions

---

## 🔄 Conversion from Manual Project to Automated Routine

### What Changed
| Manual Project | Automated Routine |
|----------------|-------------------|
| You type queries | Runs on schedule |
| You read responses | Delivered to Gmail |
| History in chat | History in Drive |
| One-off analysis | Daily consistent output |
| No alerts | Can trigger alerts |

### What Stayed the Same
- All 11 skill/reference files are identical
- Scoring system unchanged
- Output format identical
- India-specific knowledge intact
- 18-factor analysis unchanged

---

## 🎁 Bonus: Advanced Routine Ideas

Once basic setup works, you can expand:

### Idea 1: Portfolio Tracker Routine
- Read your gold holdings from a Google Sheet
- Calculate current portfolio value vs cost basis
- Alert if you should rebalance

### Idea 2: Festival Countdown Routine
- Weekly run
- Check upcoming festivals (Akshaya Tritiya, Dhanteras)
- Recommend buying window

### Idea 3: News Alert Routine
- Runs hourly during market hours
- Only sends message IF a major news event detected
- Otherwise silent

### Idea 4: Tax Planning Routine
- Monthly run
- Review all your gold purchases that month
- Calculate holding period and tax implications
- Remind you before 3-year LTCG threshold

### Idea 5: Silver + Gold Routine
- Expand to track silver alongside
- Compare gold/silver ratio (key trading signal)

---

## 📞 Support & Next Steps

### Immediate Next Actions
1. [ ] Subscribe to Claude Pro (if not already)
2. [ ] Create GitHub repo: `gold-tracker-routine`
3. [ ] Connect Gmail + Google Drive + Slack connectors
4. [ ] Push all 11 Gold Tracker files to the repo
5. [ ] Create routine at claude.ai/code/routines
6. [ ] Test with "Run Now"
7. [ ] Verify email arrives
8. [ ] Enable daily schedule

### Week 1 Goals
- [ ] Routine runs reliably every day
- [ ] Emails arrive in inbox (not spam)
- [ ] Drive archive builds up 7 reports

### Month 1 Goals
- [ ] Backtesting: compare predictions vs actual
- [ ] Tune factor weights based on accuracy
- [ ] Add Slack integration
- [ ] Add weekly review routine

---

**You now have a 24/7 AI gold analyst working for you on Anthropic's cloud infrastructure. Welcome to the future of personal finance automation!** 🥇🤖

---

*Last updated: April 2026 | Compatible with: Claude Code Routines (research preview)*

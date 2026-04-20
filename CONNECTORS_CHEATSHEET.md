# 🔌 CONNECTORS CHEAT SHEET

**Complete guide to every connector you need for Gold Tracker Routine**

---

## 🟢 Connector Priority Levels

### TIER 1: ESSENTIAL (Cannot work without these)

#### 1. Web Search (Built-in)
- **Purpose:** Fetches live gold prices, news, analyst views
- **Setup:** Already enabled on all Claude plans
- **Cost:** Free with subscription
- **Usage in routine:** EVERY run needs this
- **Permissions needed:** None — built-in

#### 2. Gmail Connector
- **Purpose:** Receive daily analysis reports in your inbox
- **Setup steps:**
  1. Go to claude.ai → Settings → Connectors
  2. Click "Connect" next to Gmail
  3. Authorize with your Google account
  4. Grant send/read email permissions
- **Cost:** Free
- **Permissions needed:** Send emails, read inbox (for threading)
- **What it does in routine:**
  - Sends the full daily report to your inbox
  - Subject line includes BUY/HOLD/SELL signal
  - HTML-formatted for easy reading

#### 3. Google Drive Connector
- **Purpose:** Archive reports for historical tracking
- **Setup steps:**
  1. Settings → Connectors → Google Drive
  2. Authorize Google account
  3. Grant file create/edit permissions
  4. **IMPORTANT:** Manually create folder named "Gold Tracker Reports" in your Drive
- **Cost:** Free
- **Permissions needed:** Create folders, create files, edit files
- **What it does in routine:**
  - Saves each day's report as a markdown file
  - Maintains a CSV log of all predictions for backtesting
  - Filename format: `gold-report-YYYY-MM-DD.md`

---

### TIER 2: HIGHLY RECOMMENDED

#### 4. Slack Connector
- **Purpose:** Real-time alerts to your phone/desktop
- **Setup steps:**
  1. Create a free Slack workspace (if you don't have one)
  2. Create a channel: `#gold-alerts`
  3. Settings → Connectors → Slack
  4. Authorize and select workspace
  5. Choose which channel Gold Tracker can post to
- **Cost:** Free (Slack free tier works)
- **Permissions needed:** Post messages to selected channels
- **What it does in routine:**
  - Quick summary alerts (signal + price)
  - More immediate than email
  - Can @-mention you for high-confidence signals

#### 5. Google Calendar Connector
- **Purpose:** Add important events (Fed meetings, festivals) to your calendar
- **Setup steps:**
  1. Settings → Connectors → Google Calendar
  2. Authorize Google account
- **Cost:** Free
- **Permissions needed:** Create events on your calendar
- **What it does in routine:**
  - Auto-adds FOMC meeting dates
  - Adds Akshaya Tritiya, Dhanteras reminders
  - Adds Indian wedding season boundaries

---

### TIER 3: OPTIONAL / ADVANCED

#### 6. Notion Connector
- **Purpose:** Build a personal dashboard database of predictions
- **Setup steps:**
  1. Sign up at notion.so (free)
  2. Create a database called "Gold Predictions"
  3. Settings → Connectors → Notion
  4. Share the database with Claude connector
- **Cost:** Free (Notion personal tier)
- **What it does:**
  - Structured database of every prediction
  - Filter by signal, confidence, outcome
  - Visual dashboard

#### 7. GitHub Connector (Required for the routine itself!)
- **Purpose:** Host your Gold Tracker knowledge files
- **Setup steps:**
  1. Sign up at github.com (free)
  2. Create private repo: `gold-tracker-routine`
  3. Install Claude GitHub App on the repo
  4. Upload all 11 Gold Tracker MD files
- **Cost:** Free
- **What it does:**
  - Stores your Gold Tracker knowledge base
  - Routine reads from this repo each run
  - Version control for your prompt improvements

#### 8. Telegram Bot (Custom MCP)
- **Purpose:** Push notifications to your phone
- **Setup:** Requires building/using custom MCP server
- **Difficulty:** Advanced
- **Cost:** Free but requires technical setup
- **What it does:**
  - Instant mobile notifications
  - Works globally (no country restrictions)

#### 9. WhatsApp Business API (Custom MCP)
- **Purpose:** WhatsApp alerts (India-specific)
- **Setup:** Requires WhatsApp Business account
- **Difficulty:** Advanced
- **Cost:** Small per-message fee
- **What it does:**
  - WhatsApp messages with daily signals
  - Great for family/friends who want alerts

---

## 📋 Recommended Setup by User Type

### Beginner (Just Starting)
Connect these 3:
- ✅ Web Search (built-in)
- ✅ Gmail
- ✅ Google Drive

**Monthly cost:** ₹1,700 (Claude Pro only)
**Time to setup:** 10 minutes
**Capability:** Full daily reports via email

### Intermediate (Active Trader)
Add these:
- ✅ Tier 1 (all 3)
- ✅ Slack (for quick alerts)
- ✅ Google Calendar (for events)

**Monthly cost:** ₹1,700 + free Slack
**Time to setup:** 20 minutes
**Capability:** Multi-channel alerts

### Professional (Serious About It)
Add these:
- ✅ All of Intermediate
- ✅ Notion (structured database)
- ✅ GitHub (version control)
- ✅ Telegram Bot (mobile push)

**Monthly cost:** ₹3,500 (Claude Max recommended)
**Time to setup:** 1-2 hours
**Capability:** Full professional dashboard

---

## 🛠️ Setup Order (Follow This Sequence)

### Day 1: Essentials (10 min)
1. Subscribe to Claude Pro/Max
2. Enable Claude Code on web
3. Connect Gmail
4. Connect Google Drive
5. Create "Gold Tracker Reports" folder in Drive

### Day 2: GitHub (10 min)
1. Create GitHub account if needed
2. Create private repo: gold-tracker-routine
3. Install Claude GitHub App
4. Upload all 11 MD files from Gold Tracker project

### Day 3: Create Routine (5 min)
1. Go to claude.ai/code/routines
2. Click "Create Routine"
3. Paste DAILY_ROUTINE_PROMPT.md content
4. Select GitHub repo
5. Set schedule: Daily 9:00 AM IST
6. Select connectors (Gmail + Drive + Web Search)
7. Click Create

### Day 4: Test & Verify (5 min)
1. Click "Run Now" on routine
2. Wait 3-5 min for completion
3. Check Gmail for report
4. Verify Drive has report file
5. Check logs if issues

### Day 5+: Enhance (Optional)
1. Add Slack integration
2. Add Calendar integration
3. Create additional routines (weekly review, hourly monitor)

---

## 🎯 Which Connector For Which Task?

| Task | Connector Needed |
|------|------------------|
| Fetch live gold prices | Web Search |
| Read latest news | Web Search |
| Get analyst views | Web Search |
| Send daily report | Gmail |
| Archive report history | Google Drive |
| Quick alerts on big moves | Slack |
| Schedule reminders (Fed, festivals) | Google Calendar |
| Structured prediction DB | Notion |
| Host knowledge files | GitHub |
| Mobile notifications | Telegram/WhatsApp |

---

## 🔒 Security & Privacy Best Practices

### Permissions — Grant Least Necessary
- Gmail: Only send/read, NOT delete
- Drive: Only create in specific folder, not root access
- Slack: Only post to specific channel, not DM
- GitHub: Only the one repo, not all repos

### Audit Regularly
- Monthly: Review connector permissions
- Remove any connectors you're not actively using
- Rotate tokens if you suspect compromise

### What Gold Tracker Will NEVER Do
- Execute actual trades (no broker connectors)
- Transfer money (no payment connectors)
- Access your banking (no financial integrations)
- Share data with third parties (only Anthropic's infrastructure)

---

## 💡 Pro Tips

### Tip 1: Use Slack with Keywords
Set up Slack keyword notifications for:
- "STRONG BUY" → Push notification
- "STRONG SELL" → Push notification
- "stop-loss triggered" → Alert
This way you only get interrupted for important signals.

### Tip 2: Gmail Filter for Organization
Create a Gmail filter:
- From: (your address)
- Subject contains: "Gold Tracker Daily"
- Action: Label as "Gold Tracker" + skip inbox

Then check the label when you want to review, not every morning.

### Tip 3: Drive Organization
Create subfolders in "Gold Tracker Reports":
- /Daily Reports (YYYY/MM/)
- /Weekly Reviews
- /Monthly Summaries
- /Special Events (for big news days)

### Tip 4: Calendar Color-Coding
Create a separate "Gold Events" calendar:
- Blue for bullish events (rate cuts)
- Red for bearish events (rate hikes)
- Yellow for festivals
- Green for FOMC meetings

### Tip 5: Backup Your Setup
Export your:
- Routine prompt (save externally)
- Connector list (screenshot)
- GitHub repo (it's already version controlled)

So if anything breaks, you can rebuild in 15 min.

---

## ❓ FAQ

### Q: Do I need to pay extra for connectors?
A: No. Connectors are included in your Claude Pro/Max subscription. The external services (Gmail, Slack) have their own free tiers.

### Q: How much Claude usage does one routine run consume?
A: A full Gold Tracker daily run uses roughly the same as a long manual chat session — maybe 5-10% of a Pro user's daily quota.

### Q: Can I run it more than once per day?
A: Yes! On Pro (5/day), Max (15/day), Team (25/day). Different schedules can be set up for morning/midday/evening.

### Q: What if a connector stops working?
A: The routine will try to complete analysis even if one delivery method fails. Check claude.ai/code for session logs to debug.

### Q: Can I pause the routine temporarily (e.g., on vacation)?
A: Yes. Go to claude.ai/code/routines → select your routine → toggle off. No usage counts during paused time.

### Q: Does it work if I switch phones/laptops?
A: YES! This is the whole point of routines. They run on Anthropic's cloud infrastructure, not your device.

---

## 🚀 Next Step

Once your connectors are set up, go to `DAILY_ROUTINE_PROMPT.md` to copy the exact prompt you'll paste into the routine creation form.

Welcome to the automated gold tracking era! 🥇

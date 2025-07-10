# 📈 Market Insights Aggregator Workflow

## 🔍 Overview

This **n8n workflow** is designed to gather real-time financial and sentiment data from various free sources to identify booming or doomed sectors in the stock market. It supports hybrid decision-making with optional API integration for enhanced insights.

---

## ⚙️ Features

- ✅ Manual trigger to execute the workflow on demand
- ⚙️ Conditional logic to use APIs based on configuration
- 🌐 Web scraping from Reuters, MoneyControl, Reddit, Chittorgarh
- 📊 Free market data from Yahoo Finance
- 💬 Sentiment extraction from Reddit investment communities
- 📈 IPO and Mutual Fund tracking via Chittorgarh and RapidAPI

---

## 🧩 Workflow Structure

```plaintext
[Manual Trigger]
      |
      v
[Set Configuration Node] --> [IF: use_apis == true]
                                  |
                                  v
                            [HTTP Request - Reuters]
                                  |
                                  v
                   [Yahoo Finance → MoneyControl → Reddit →
                   Mutual Funds → IPO Tracker (Chittorgarh)]
| Source                | Type     | Purpose                                 |
| --------------------- | -------- | --------------------------------------- |
| **Reuters**           | News     | Latest business headlines               |
| **Yahoo Finance**     | API      | Stock data (e.g., RELIANCE.NS)          |
| **MoneyControl**      | Scraping | Market prices & sentiments              |
| **Reddit**            | Scraping | Investor sentiment (r/IndiaInvestments) |
| **RapidAPI (MF NAV)** | API      | Mutual fund NAVs                        |
| **Chittorgarh**       | Scraping | Upcoming and ongoing IPOs               |


NEWS_API_KEY=
ALPHA_VANTAGE_KEY=
FMP_API_KEY=
RAPID_API_KEY=
TWITTER_BEARER_TOKEN=

CALLMEBOT_API_KEY=
WHATSAPP_PHONE_NUMBER=
WHATSAPP_BUSINESS_TOKEN=

{
  "mode": "hybrid",
  "market": "India",
  "use_apis": true,
  "preferences": {
    "risk_tolerance": "moderate",
    "investment_horizon": "1-3 years",
    "sectors_focus": ["IT", "Banking", "Healthcare", "Energy"],
    "include_smallcap": true,
    "include_mutual_funds": true,
    "include_ipos": true,
    "max_recommendations": 10,
    "min_confidence": 70
  }
}
Great job on completing 69% of my project! Based on my current progress and the n8n workflow I've shared, here's how you can track the remaining 31% and what you might focus on next to complete the project successfully:

✅ What You've Completed (69%)
✅ Manual Trigger setup

✅ JSON configuration with API keys and preferences

✅ Conditional execution for using APIs or not

✅ Scraping and HTTP requests for:

Reuters (Business news)

Yahoo Finance (stock prices)

MoneyControl (company sentiment)

Reddit (social sentiment)

Mutual Fund NAVs via RapidAPI

IPO list from Chittorgarh

🔜 What’s Likely Remaining (31%)
1. Data Parsing & Normalization (10%)
Extract relevant data (titles, prices, sentiment scores, NAVs, IPO names) from responses

Convert HTML/JSON to structured format using HTML extract or code nodes

2. Sentiment Analysis / Scoring Logic (7%)
Analyze Reddit/news sentiment (basic keyword-based or using NLP API)

Assign scores to stocks/sectors based on frequency, polarity, etc.

3. Ranking & Recommendation Engine (6%)
Sort and recommend top sectors/stocks/IPOs based on user preferences

Apply filters (confidence, max results, risk tolerance)

4. Reporting / Output Generation (5%)
Send results via:

WhatsApp (CallMeBot or Business API)

Email or Telegram

Dashboard (optional)

5. Final Testing & Optimization (3%)
Optimize execution times

Add error handling for failed HTTP requests

Clean UI structure in n8n (group nodes, add descriptions)


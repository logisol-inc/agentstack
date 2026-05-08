---
title: "How I Built a Free AI Prediction Market Monitor"
date: 2026-05-07
draft: false
tags: ["prediction markets", "AI agents", "Polymarket", "passive income"]
description: "How I built an AI-powered monitor that scans Polymarket for mispriced odds and sends Telegram alerts — using only free tools."
---

Prediction markets are inefficient by nature. Odds move slower than reality because most traders aren't watching news 24/7. Information takes time to be priced in.

I built a monitor that watches constantly and spots the lag between what happened and what the market still believes.

## What it does

Every 30 minutes, the system:

1. Fetches the top 20 open markets on Polymarket by volume
2. Pulls live headlines from BBC World, BBC Business, CoinDesk, and ESPN
3. Asks an AI to assess whether any market odds lag behind the news
4. Fires a Telegram alert if confidence exceeds 65%

## The stack

- **Polymarket Gamma API** — free, no auth required
- **Groq API** — free tier, llama-3.3-70b-versatile model
- **BBC RSS feeds** — free, reliable, no rate limits
- **Telegram Bot API** — free
- **Python** — runs on any Linux VM

Total cost: **$0/month**

## Sample alert

\`\`\`
🎯 OPPORTUNITY DETECTED
──────────────────────────────
Market: US x Iran permanent peace deal by April 22?
Odds: YES 45% / NO 55%
Signal: 🔽 NO underpriced
Confidence: ████████░░ 80%
──────────────────────────────
Why: BBC reports Iran nuclear talks collapsed with no agreement reached.
\`\`\`

## The income angle

With $20 deployed on Polymarket and a working signal system, even a 10% edge per trade compounds meaningfully over time. The real play is building a track record over 30–60 days, then packaging the alerts as a paid signal service.

## Want the code?

The full source is available on GitHub. Drop your email below and I will send you the setup guide.

---

*Affiliate note: If you want a cheap VPS to run this yourself, [Vultr](https://vultr.com) starts at $2.50/month and gives you $100 free credit.*

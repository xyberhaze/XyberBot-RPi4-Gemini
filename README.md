# 🦞 OpenClaw Node: Raspberry Pi 4 Optimization
### Strategic Migration: Paid Models (Claude) to Free-Tier Stability (Gemini)

This repository documents the deployment of a 24/7 autonomous AI agent on Raspberry Pi 4 hardware. The core goal of this build was **cost optimization**: moving from high-cost API credits to a stable, free-tier architecture.

## 🛠 Tech Stack
* **Hardware:** Raspberry Pi 4 (8GB RAM)
* **Framework:** OpenClaw 2026.3.12 (Stable)
* **AI Engine:** Google Gemini 3.1 Flash (Free Tier)
* **Messaging Channel:** Telegram (@XyberBot)
* **Host OS:** Raspberry Pi OS 64-bit

---

## 🚀 Build & Logic

### 1. Cost Efficiency (The "Free-Tier Hero")
We migrated from paid providers to **Gemini 3.1 Flash** via Google AI Studio. 
* **Logic:** Gemini Flash allows for 1,500 requests per day for free, providing high-speed reasoning with zero monthly overhead.
* **Optimization:** Selected "Flash" over "Pro" to maintain low latency on the Raspberry Pi's ARM architecture.

### 2. Strategic Setup & Initialization
To ensure a clean deployment on the Pi, we used non-interactive onboarding and mapped the system paths for persistent CLI access.

```bash
# Ensure OpenClaw is in the system path
export PATH="$(npm prefix -g)/bin:$PATH"

# Non-interactive onboarding (Bypassing manual menus)
openclaw onboard --non-interactive \
  --mode local \
  --auth-choice gemini-api-key \
  --gemini-api-key "YOUR_GOOGLE_API_KEY_HERE" \
  --accept-risk

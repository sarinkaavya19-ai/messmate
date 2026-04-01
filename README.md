# 🍛 MessMate — AI-Powered Hostel Meal Planner

> Plan your daily hostel meals, track nutrition, compare mess subscriptions, and get real-time AI advice — all in a single HTML file.

![MessMate Preview](https://img.shields.io/badge/status-live-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![No Dependencies](https://img.shields.io/badge/dependencies-none-orange) ![Powered by Claude](https://img.shields.io/badge/AI-Claude%20by%20Anthropic-8B5CF6)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🗓️ **Daily Meal Planner** | Pick breakfast, lunch, snack & dinner from a library of 24 hostel-friendly dishes |
| 📊 **Live Nutrition Tracker** | Calories, protein, carbs & fat update in real time as you plan |
| 💰 **Budget Tracker** | Set a daily budget (₹80–₹400), get instant over/under alerts |
| 🏠 **Mess Subscriptions** | Browse 5 local messes, compare weekly vs monthly plans & savings |
| 🤖 **AI Chef (Claude API)** | Chat with Claude for personalised meal advice, nutrition tips & hostel hacks |
| ✦ **AI Nutrition Tip** | One-tap AI tip based on exactly what you've planned for the day |

---

## 🚀 Live Demo

👉 **[Try it here](https://sarinkaavya19-ai.github.io/messmate/hostel_meal_planner_ai.html)**



---

## 📸 Screenshots
<img width="1895" height="874" alt="Screenshot 2026-04-01 182020" src="https://github.com/user-attachments/assets/b38f7a15-1522-4441-bccd-9679837f798a" />

<img width="1895" height="877" alt="Screenshot 2026-04-01 182036" src="https://github.com/user-attachments/assets/191ae841-acc5-42a6-94b4-cda9f8f39ba5" />

<img width="1899" height="879" alt="image" src="https://github.com/user-attachments/assets/d83073a9-a582-42ac-bc4a-06bc27ae68cc" />

---

## 🛠️ Tech Stack

```
HTML5         — Structure & layout
CSS3          — Custom design system, animations, responsive grid
Vanilla JS    — State management, UI rendering, API calls
Anthropic API — Claude claude-sonnet-4-20250514 for AI Chef & nutrition tips
Google Fonts  — Fraunces (display) + DM Sans (body)
```

**No frameworks. No npm. No build step. Just one `.html` file.**

---

## 📂 Project Structure

```
messmate/
├── index.html      ← The entire app (HTML + CSS + JS in one file)
└── README.md       ← This file
```

---

## ⚡ Getting Started

### Option 1 — Just open it
Download `index.html` and open it in any browser. Done.

### Option 2 — Host on GitHub Pages
1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Your app goes live at `https://YOUR-USERNAME.github.io/messmate/`

### Option 3 — Run locally with a server
```bash
git clone https://github.com/YOUR-USERNAME/messmate.git
cd messmate
npx serve .
# Open http://localhost:3000
```

---

## 🤖 How the Anthropic API Works

MessMate uses the **Anthropic Messages API** to power two AI features:

### 1. AI Chef (full chat)
Every message you send goes to:
```
POST https://api.anthropic.com/v1/messages
```
with a **system prompt** that secretly includes your current meal plan and daily budget — so Claude's advice is always personalised to you.

```js
{
  model: "claude-sonnet-4-20250514",
  max_tokens: 1000,
  system: "You are MessMate's AI Chef... user's budget: ₹150, plan: Dal Rice, Poha...",
  messages: [ ...last 10 messages ]  // conversation memory
}
```

### 2. AI Nutrition Tip (one-shot)
A single API call that sends your planned meals and gets back a 2–3 sentence actionable tip.

> **Note:** The API key is handled automatically when running inside Claude.ai artifacts. If you host this externally, you will need to add your own key via a backend proxy — never expose API keys in client-side code.

---

## 🍽️ Meal Database

24 hostel-friendly Indian dishes across all price points:

| Range | Examples |
|---|---|
| ₹15–₹30 | Chai & Biscuits, Poha, Maggi, Peanut Chaat |
| ₹35–₹60 | Upma, Idli Sambar, Dal Rice, Egg Rice |
| ₹65–₹90 | Rajma Chawal, Paneer Bhurji, Chicken Curry |
| ₹100–₹120 | Fish Fry & Rice, Mutton Curry |

Each meal includes: price, calories, protein, carbs, fat, type (veg/non-veg), and compatible meal slots.

---

## 🏠 Mess Providers

| Mess | Type | Weekly | Monthly |
|---|---|---|---|
| Shri Sai Mess | Pure Veg | ₹420 | ₹1,600 |
| Annapurna Kitchen | Veg & Non-Veg | ₹500 | ₹1,900 |
| Home Flavours | Pure Veg | ₹380 | ₹1,450 |
| Dil Se Dhaba | Non-Veg Special | ₹600 | ₹2,200 |
| Green Bowl | Healthy / Veg | ₹560 | ₹2,100 |

---

## 💡 Ideas for Contributors

- [ ] Add dark mode toggle
- [ ] Weekly meal planning view (7-day calendar)
- [ ] Export plan as PDF / share as image
- [ ] Add more cities' mess providers
- [ ] Calorie goal customisation (bulk / cut / maintain)
- [ ] PWA support (installable on mobile)
- [ ] Backend integration for real mess bookings

---

## 📄 License

MIT — free to use, modify, and share.

---

## 🙏 Built With

- [Claude by Anthropic](https://anthropic.com) — AI Chef powered by claude-sonnet-4-20250514
- [Fraunces](https://fonts.google.com/specimen/Fraunces) & [DM Sans](https://fonts.google.com/specimen/DM+Sans) — Google Fonts
- Built entirely inside [Claude.ai](https://claude.ai) — no external editor used

---

*Made with ❤️ for hostel students everywhere*

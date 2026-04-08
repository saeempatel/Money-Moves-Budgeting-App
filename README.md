# MoneyMoves
> An interactive financial literacy web app for teens and young adults, built with zero dependencies.

<img width="1435" height="762" alt="Screenshot 2026-04-08 at 1 58 11 PM" src="https://github.com/user-attachments/assets/1acab6c2-aea6-4bd6-89ce-f6b81d2a133b" />

---

## Overview

Money Moves is a standalone educational web application that teaches personal finance through tools and scenario based gameplay. Users can plan a real budget, track debts, set savings goals, read financial lessons, and play a decision making game, all in one file, no installation required.

An AI financial coach (Coach Quinn) powered by Groq's Llama 3.3 70B is embedded in the app and gives personalized advice based on the user's actual data.

---

## Features

| Module | Description |
|---|---|
| **Dashboard** | Live financial health score, stats snapshot, and rotating financial facts |
| **Budget Planner** | Enter income, categorize expenses (Needs/Wants/Save), live donut chart, 50/30/20 rule checker |
| **Debt Tracker** | Add debts with APR, payoff timeline calculator, extra payment slider, Avalanche vs Snowball strategy comparison |
| **Savings Goals** | Named goals with progress bars, milestone dots, and projected completion dates |
| **Learn** | 5 lessons, 16 term searchable glossary, 6 key financial formulas with examples |
| **Game** | 4 personas, 8 financial scenarios, XP system, letter grade results |
| **AI Coach (Quinn)** | Floating chat assistant that reads your live data and gives personalized advice |
| **Light / Dark Mode** | Full theme toggle with saved preference |

---

## Tech Stack

- **HTML5** — structure and markup
- **CSS3** — styling, animations, CSS custom properties for theming
- **Vanilla JavaScript (ES6+)** — all logic, no frameworks
- **Canvas API** — donut chart rendering (built into browser)
- **Google Fonts** — Syne + DM Mono (loaded via CDN)
- **Groq API** — AI Coach powered by Llama 3.3 70B

No React, Angular, Vue, jQuery, Bootstrap, or npm packages.

---

## Getting Started

### Option A — Open directly (no setup needed)

All features except the AI Coach work offline:

1. Download `MoneyMoves.html`
2. Double-click the file — it opens in your browser
3. Done

### Option B — Run via local server (required for AI Coach)

```bash
# Navigate to the folder containing MoneyMoves.html
cd ~/Downloads

# Start the server
python3 -m http.server 8000
```

Then open your browser and go to:
```
http://localhost:8000/MoneyMoves.html
```

To stop the server, press `Ctrl + C` in the terminal.

---

## AI Coach Setup

The AI Coach requires a free Groq API key.

1. Sign up at [console.groq.com](https://console.groq.com) (free)
2. Go to **API Keys** → **Create API Key** → copy it
3. Open `MoneyMoves.html` in a text editor and find line ~1860:
   ```js
   const GROQ_API_KEY = 'YOUR_GROQ_KEY_HERE';
   ```
4. Replace `YOUR_GROQ_KEY_HERE` with your key
5. Save the file and refresh your browser

Or use this terminal command (replace the key):
```bash
sed -i '' "s/YOUR_GROQ_KEY_HERE/gsk_your_key_here/" ~/Downloads/MoneyMoves.html
```

> ⚠️ Keep your API key private. Do not commit it to GitHub or share the file publicly with the key inside.

---

## File Structure

```
MoneyMoves.html          ← entire app in one file
│
├── <style>              ← styles.css (inlined)
│
├── <script>
│   ├── app.js           ← global state, nav(), toast(), addXP()
│   ├── dashboard.js     ← health score, facts, updateDashboard()
│   ├── budget.js        ← budget planner, donut chart, 50/30/20
│   ├── debt.js          ← debt tracker, payoff calculator
│   ├── savings.js       ← goals, milestones, timeline
│   ├── learn.js         ← lessons, glossary, formulas
│   └── game.js          ← scenarios, personas, scoring
│
└── <script>             ← coach.js (AI coach) + bootstrap init
```

The multi-file version (for hosting) is available in the `budget-quest-app/` folder:
```
budget-quest-app/
├── index.html
├── css/
│   └── styles.css
└── js/
    ├── app.js
    ├── dashboard.js
    ├── budget.js
    ├── debt.js
    ├── savings.js
    ├── learn.js
    └── game.js
```

---

## Hosting

To host on the web, drag the `budget-quest-app/` folder onto [netlify.com/drop](https://app.netlify.com/drop) — it instantly gets a public URL with no configuration needed.

---

## Screenshots

| Dashboard | Budget Planner | Game |
|---|---|---|
| Financial health score + quick actions | Live donut chart + 50/30/20 checker | Scenario based decisions + XP |

---

## Roadmap

- [ ] LocalStorage data persistence (budget, debts, goals survive refresh)
- [ ] Confirmation dialogues for all destructive actions
- [ ] ARIA labels and full keyboard navigation
- [ ] Interactive compound interest calculator
- [ ] Drag-and-drop budget categorization quiz
- [ ] Lesson completion tracking and badges
- [ ] Font scaling / accessibility controls
- [ ] Branching game scenarios based on prior decisions
- [ ] PDF export for budget and game results

---

## License

This project was built as an academic prototype. Feel free to fork, extend, or use it as a learning reference.

---

*Built with vanilla HTML, CSS, and JavaScript. No frameworks were harmed in the making of this app.*

# FarmSense 🌱

**Agentic AI micro-farmer for your pocket.**

FarmSense is a single-file progressive web app that gives every grower — backyard gardener or small-scale farmer — an AI agronomist on demand. Powered by Claude claude-sonnet-4-6, it runs a multi-tool agentic loop to scan each crop, identify disease, prescribe treatment, and build a harvest plan, all before you type your first question.

---

## Features

### Agentic AI Scan
When you add a crop, FarmSense automatically fires 5 tools in sequence — health assessment, disease ID, treatment recommendation, soil analysis, and planting schedule — before you say a word. You can re-run a full scan anytime with one tap.

### 10 Specialized Claude Tools
| Tool | What it does |
|------|-------------|
| `assess_crop_health` | Health score (0–100) with contributing factors |
| `identify_plant_disease` | Disease name, severity, and confidence rating |
| `recommend_treatment` | Organic treatment protocol with timeline |
| `analyze_soil_requirements` | pH target, N-P-K profile, amendment plan |
| `create_planting_schedule` | Week-by-week care calendar to harvest |
| `identify_pest` | Pest ID with organic response plan |
| `calculate_yield_estimate` | Projected harvest weight and quality rating |
| `recommend_companion_plants` | 3-plant companion layout with spacing tips |
| `generate_care_plan` | Full seasonal care plan per crop |
| `find_local_resources` | Nearby nurseries, extension offices, seed banks |

### Agent Task Bar
An animated progress bar tracks each tool as it runs (○ → ⟳ → ✓), so you always know what the AI is doing.

### 11 Supported Crop Types
Tomato · Pepper · Lettuce · Cucumber · Carrot · Basil · Beans · Corn · Strawberry · Broccoli · Onion

### Demo Mode
No API key? No problem. Demo mode pre-seeds your garden with 3 realistic crops (Cherry Tomatoes, Bell Peppers, Butter Lettuce) and simulates the full tool pipeline with real delays — great for a walkthrough without any setup.

---

## Screens

```
Splash → Auth (PIN / biometric)
       → Setup (first run: name, location, grow zone, farm type)
       → Home     — crop cards with health scores and disease badges
          Scout   — AI chat interface for the selected crop
          Garden  — full crop roster with add/manage
          Settings — API key, demo toggle, biometric, reset
```

---

## Getting Started

### Option A — Demo (no API key needed)
1. Open `index.html` in any modern browser.
2. Complete the one-time setup (name, location, zone, farm type).
3. Demo mode is on by default — three crops are ready immediately.

### Option B — Live AI with Claude
1. Get an API key at [console.anthropic.com](https://console.anthropic.com).
2. Open Settings → paste your key → demo mode turns off automatically.
3. Add a crop. FarmSense runs the full 5-tool intake scan instantly.

> **Note:** The app calls the Anthropic API directly from the browser using the `anthropic-dangerous-direct-browser-access` header. Keep your API key private and do not deploy publicly with your key embedded.

---

## Tech Stack

| Layer | Choice |
|-------|--------|
| Runtime | Vanilla JS — no build step, no dependencies |
| UI | Single HTML file (CSS + HTML + JS inline) |
| AI | Claude claude-sonnet-4-6 via Anthropic Messages API |
| Storage | `localStorage` (`farmsense_` prefix) |
| Auth | PIN keypad + Web Biometrics API |
| Deploy | Any static host or open locally |

---

## Project Structure

```
farmsense/
└── index.html   # entire app — 1,572 lines
```

That's it. No `node_modules`, no build pipeline, no server.

---

## Local Development

```bash
# Clone
git clone git@github.com:808cadger/FarmSense.git
cd FarmSense

# Open directly — no server needed for demo mode
open index.html          # macOS
xdg-open index.html      # Linux

# For live API calls, serve over HTTPS (required by some browsers for biometrics)
npx serve .
# or
python3 -m http.server 8080
```

---

## Design

- **Background:** Dark soil `#050C07`
- **Primary:** Deep forest green `#1A4D2E`
- **Accent:** Fresh growth green `#7CB342`
- **Gold:** Golden wheat `#D4A853`
- **Font:** SF Pro Display / system-ui

---

## Roadmap

- [ ] Camera-based plant photo scanning
- [ ] Weather API integration (frost alerts, rain forecast)
- [ ] Push notifications for watering and harvest reminders
- [ ] Export crop journal as PDF
- [ ] PWA manifest + service worker for offline use

---

## License

MIT — do whatever you want, just give the plants some water.

---

*Built with [Claude claude-sonnet-4-6](https://anthropic.com) · Part of the [808cadger](https://github.com/808cadger) agentic app series*


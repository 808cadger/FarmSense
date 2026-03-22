# FarmSense

> AI farm monitoring and crop management — scan a crop, get a diagnosis, treatment plan, and full harvest schedule before you ask a question.

[**PWA →**](https://cadger808.codeberg.page/farmsense) · [**Download APK / Desktop →**](https://codeberg.org/cadger808/farmsense/releases) · [Codeberg](https://codeberg.org/cadger808/farmsense)

---

## Can anyone use this?

**Yes — install in 10 seconds, no account needed.**

1. Open [cadger808.codeberg.page/farmsense](https://cadger808.codeberg.page/farmsense) on any device
2. Tap "Add to Home Screen" (or download the APK for Android / AppImage for Linux)
3. Open the app → tap ⚙️ Settings → paste your [Anthropic API key](https://console.anthropic.com)

That's it. The key is stored only on your device.

---

## What it does

| Feature | Description |
|---------|-------------|
| 🌱 **Auto crop scan** | On crop add, Claude runs 5 tools — health score, disease ID, treatment, soil, schedule |
| 🐛 **Pest & disease ID** | Identifies threats with confidence rating and organic response plan |
| 🗓️ **Harvest planner** | Week-by-week care calendar to harvest |
| 🌍 **Local resources** | Nearby nurseries, extension offices, seed banks |
| 🤖 **AI avatar** | Floating agronomist on every screen |
| 📤 **Share / install** | One-tap PWA install + Download APK button in the share widget |
| 🖥️ **Desktop app** | Electron build (AppImage + RPM) for Linux |

**10 farm tools:** `assess_crop_health` · `identify_plant_disease` · `recommend_treatment` · `analyze_soil_requirements` · `create_planting_schedule` · `identify_pest` · `calculate_yield_estimate` · `recommend_companion_plants` · `generate_care_plan` · `find_local_resources`

Supports 11 crop types: Tomato · Pepper · Lettuce · Cucumber · Carrot · Basil · Beans · Corn · Strawberry · Broccoli · Onion

---

## Install options

| Method | Steps |
|--------|-------|
| **PWA** | Open link → "Add to Home Screen" — works on Android, iOS, desktop |
| **Android APK** | [Download](https://codeberg.org/cadger808/farmsense/releases) → open file on device |
| **ADB install** | `adb install -r app-debug.apk` |
| **Linux desktop** | Download `.AppImage` or `.rpm` from [Releases](https://codeberg.org/cadger808/farmsense/releases) |

---

## Dev quick start

```bash
git clone https://codeberg.org/cadger808/farmsense.git
cd farmsense && npm install

npx serve .                                            # browser dev
npx cap sync android && cd android && ./gradlew assembleDebug  # APK
npm run electron:dist                                  # Electron
```

---

## Tech stack

| Layer | Tech |
|-------|------|
| UI | Vanilla HTML/CSS/JS |
| AI | Claude Sonnet 4.6 with 10 farm tools |
| Mobile | Capacitor → Android APK |
| Desktop | Electron (AppImage / RPM) |
| CI | Forgejo Actions (APK + Pages + Electron) |

---

**Developer:** [codeberg.org/cadger808](https://codeberg.org/cadger808)

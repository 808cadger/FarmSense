# FarmSense

<!-- INSTALL-START -->
## Install and run

These instructions install and run `FarmSense` from a fresh clone.

### Clone
```bash
git clone https://github.com/808cadger/FarmSense.git
cd FarmSense
```

### Web app
```bash
npm install
python3 -m http.server 8080
```

### Android build/open
```bash
npm run cap:sync
npm run cap:android
```

### Desktop app
```bash
npm run electron
npm run electron:dist
```

### Notes
- Use Node.js 22 or newer for the current package set.
- Android builds require Android Studio, a configured SDK, and Java 21 when Gradle is used.

### AI/API setup
- If the app has AI features, add the required provider key in the app settings or local `.env` file.
- Browser-only apps store user-provided API keys on the local device unless a backend endpoint is configured.

### License
- Apache License 2.0. See [`LICENSE`](./LICENSE).
<!-- INSTALL-END -->


> AI farm monitoring and crop management — scan a crop, get a diagnosis, treatment plan, and full harvest schedule before you ask a question.

[**PWA →**](https://cadger808.codeberg.page/farmsense) · [**Download APK / Desktop →**](https://codeberg.org/cadger808/farmsense/releases) · [Codeberg](https://codeberg.org/cadger808/farmsense)

---

## Easiest way to get it — Zephyr

**[Zephyr](https://cadger808.codeberg.page/zephyr)** is the open PWA network that distributes every app in this suite. Open Zephyr, tap FarmSense, install. Done.

- No account. No sign-up. No data saved anywhere.
- Zephyr doesn't store your crop data, scans, or API key — everything stays on your device.
- The app ships fresh every time via PWA — nothing cached on the distribution side.

---

## Can anyone use this?

**Yes — install in 10 seconds, no account needed.**

1. Open [Zephyr](https://cadger808.codeberg.page/zephyr) → find FarmSense → tap Install
2. Or open [cadger808.codeberg.page/farmsense](https://cadger808.codeberg.page/farmsense) directly on any device
3. Tap "Add to Home Screen" (or download APK for Android / AppImage for Linux)
4. Open the app → tap ⚙️ Settings → paste your [Anthropic API key](https://console.anthropic.com)

The key is stored only on your device. Nothing leaves without you asking it to.

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
| **Zephyr** | [cadger808.codeberg.page/zephyr](https://cadger808.codeberg.page/zephyr) → FarmSense → Install — zero data saved |
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
| Distribution | Zephyr PWA network |
| CI | Forgejo Actions (APK + Pages + Electron) |

---

**Developer:** [codeberg.org/cadger808](https://codeberg.org/cadger808)
---

© 2026 cadger808 — All rights reserved.

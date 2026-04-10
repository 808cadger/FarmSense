CLAUDE.md — FarmSense
AI farm monitoring, crop management, and home service verification app. Stack: HTML + Capacitor + Electron | Deploy: APK + PWA + Electron AppImage/RPM

Repo Identity
Codeberg: https://codeberg.org/cadger808/farmsense
PWA: https://cadger808.codeberg.page/farmsense
Releases: https://codeberg.org/cadger808/farmsense/releases

Key Files
index.html — single-page app entry point
api-client.js — Claude API calls (load FIRST before other widgets)
avatar-widget.js / share-widget.js — floating UI widgets
electron/main.js — Electron desktop entry
capacitor.config.json — Capacitor/Android config
.github/workflows/build-apk.yml — APK CI
.github/workflows/deploy-pages.yml — PWA CI
.gitea/workflows/build-electron.yml — Electron CI

Commands
npm install
npx cap sync android
cd android && ./gradlew assembleDebug
adb install -r android/app/build/outputs/apk/debug/app-debug.apk
npm run electron:dist

Assumption-Driven Coding
When generating or editing code:
- Add // #ASSUMPTION: ... comments for each non-trivial assumption
- Ask: "What test/edge case breaks this?"
- Add defensive checks or // TODO: validate ...
- Review all #ASSUMPTION lines before finishing

SRE & DevOps (2026 Standards)
SLOs: 99.9% availability, <200ms P95 latency, 0.1% error budget monthly
SLIs: Track via Prometheus/Grafana golden signals
Deploy: Zero-downtime (blue-green), IaC-first (Pulumi/Terraform)
MCP Integration: Secure cloud access (AWS, Vercel)
Monitoring: Golden signals + AI anomaly detection
Chatbot: Agentic chatbot in every app (UI + API + safe prompts)

Auto-Debug Engine (Always On)
Before every change: Run tests/lint, fix failures first
After code: Self-review: "SRE checks? Edge cases? Security?"
Loop: error → fix → retest → confirm clean → proceed
Tools: Playwright MCP for UI tests; background terminal logs
Never skip: No deploy without "Debug complete: [tests passed]"

Goal
Ship production-ready agentic AI apps with embedded chatbots, SRE-grade reliability, Fiverr-ready polish. Every deploy <30min.

## FarmSense Modes
### Crop Mode (Core)
Input: Yard/plant photos + location/weather
Output: Pest ID, soil analysis, yield prediction, Hawaii planting calendar
JSON: {"pest":"rust_mite","soil_npk":[4,2,6],"yield_forecast":2.3,"next_action":"mulch"}

### Service Verify Mode (Contractor Quality)
Input: Repair photo/video + description (e.g., "roof patch after storm")
Hawaii Context: Salt-air corrosion, volcanic substrates, 20-30% cost inflation
Analyze: CV workmanship standards (cracks, alignment, materials match)
Output JSON:
{
  "quality_score":0-100,
  "issues":["poor caulk depth", "sealant mismatch"],
  "fair_price":{"lo":1800,"hi":2500,"sources":"HI contractor avg 2026"},
  "tips":"Add copper flashing for salt-air protection",
  "cv_flags":["material_mismatch: -15pts"]
}
Example: "Cracked stucco wall repair" → quality:82, fair_price:lo$1800-hi$2500
git add CLAUDE.md
git commit -m "feat: Service Verify Mode for contractor scans"
git push origin main
# CI auto-deploys PWA in <5min
[REST OF YOUR DESIGN SYSTEM UNCHANGED — Claude warm palette, Anthropic Serif, ring shadows, etc.]

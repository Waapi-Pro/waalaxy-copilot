# Changelog

## 1.3.0 — 2026-07-15
- Flow change: **Website Analysis** is now an explicit **opt-in gate** before the prospecting
  strategy ("optimize your website, or go straight to outreach?") — never auto-run.
- **Profile Optimization** is now offered **after the target is locked** (Step 2), so rewrites align
  to the exact ICP chosen.

## 1.2.0 — 2026-07-15
- Website fetch now extracts the **light-theme design system** (colors, fonts, style, logo, art
  direction) into a "Website elements" block in `prospecting-strategy.md`.
- Profile Optimization can generate an on-brand **LinkedIn banner image prompt** for ChatGPT/Gemini,
  using the 16:9-with-white-margins → center-crop-to-4:1 layout workaround.

## 1.1.0 — 2026-07-15
- Added **Website Analyzer** module (Fletch positioning & messaging teardown) — standalone
  deliverable that also feeds targeting and sequences.
- Website Analyzer can emit a ready-to-paste **AI-builder rebuild prompt** (v0, Lovable, Bolt, …).
- Added **Profile Optimization** module (Waalaxy method) — LinkedIn profile audit + rewrites, driven
  by an uploaded profile `.html` export and the user's website.
- Added the **version check**: weekly freshness check against GitHub with a non-blocking update prompt.

## 1.0.0 — baseline
- Core flow: Targets → Search URL → Messages, plus CSV list cleaning.

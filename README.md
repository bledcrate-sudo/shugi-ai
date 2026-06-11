# Shugi AI — iOS App

Capacitor wrapper for shugiai.com. Builds unsigned `.ipa` via GitHub Actions (macOS runner).

## Build flow

1. Push repo to GitHub.
2. GitHub Actions runs `.github/workflows/ios-build.yml` on `macos-14`.
3. Download artifact `ShugiAI-unsigned-ipa` from the run.

## Install on iPhone

Unsigned IPA — pick one:

- **AltStore** (free, requires AltServer on Win/Mac) — drag IPA into AltStore, re-sign every 7 days with free Apple ID.
- **Sideloadly** (free, Win/Mac) — connect iPhone, drag IPA, sign with Apple ID.
- **Apple Developer ($99/yr)** — add signing cert + provisioning profile to repo secrets, switch workflow to signed build for TestFlight / App Store.

## Local files

- `www/` — bundled web assets (from love-or-attachment/dist)
- `resources/icon.svg`, `resources/splash.svg` — logo source, auto-rasterized in CI
- `capacitor.config.json` — app id `com.shugiai.app`, name `Shugi AI`

## Push to GitHub

```bash
cd C:/Users/Administrator/Desktop/shugi-ai
git init
git add .
git commit -m "Initial Shugi AI iOS scaffold"
gh repo create shugi-ai --private --source . --push
```

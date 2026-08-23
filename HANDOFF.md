# HANDOFF — current state

> Rolling file: overwrite when stopping mid-task. Keep under ~25 lines. History lives in LOG.md.

**Current state (2026-07-28): BOTH APPS ARE LIVE.** iOS cleared review and released
2026-07-28 (`apps.apple.com/app/id6789833467`, v1.0, Free, min iOS 15.6); Android has been live
since 2026-07-21 (`com.willeypianotuning.pianoaudit`). Both hero badges are now real store links.
Note iOS launched in **2 countries only** (Anthony's deliberate staged launch), so
`itunes.apple.com/lookup?bundleId=…` returns 0 unless you pass `&country=us` — use the id form:
`lookup?id=6789833467&country=us`. Prior
Android-era refresh (PR #1, squash `3cabe5e`) remains: iPhone+Android copy, real Yamaha GP1
screenshots (an actual before/after pitch correction) captured from the app itself, Pro sample
report rendered through the shipping PDF pipeline, favicon/OG icons from the app icon, privacy
policy covering Apple and Google (mirrored from `~/PianoAnalyzer/docs/legal/`).

**Screenshot regeneration recipe:** see README.md assets section — seed a simulator store with an
exported piano JSON, drive with the app's Debug launch args (`-uiScreen report|compare`,
`-uiDumpReportPDF`), capture via `xcrun simctl io screenshot`. A seeded "PA-Shots iPhone 16 Pro"
simulator exists on `mini`.

**Note for the next agent:** `main` had an unpushed local commit (`bc38056`, AgentHub guidance) that
the PR branch was built on; the squash-merge folded it into `3cabe5e`, so local main needed a reset
to `origin/main`. Content was verified preserved — nothing lost. Push main when you commit to it.

**Known gaps (also in TODO.md):** `/ptg` still shows "Redemption link coming shortly" for iPhone —
accurate, because Anthony's Apple offer code hasn't been issued yet. Swap in the real
`apps.apple.com/redeem?ctx=offercodes&id=6789833467&code=…` link and flip `.redeem-btn pending`
to `.live` when it is (the Android side already carries the live `PTG2026` code). Both store
badges and the support restore-purchases answer are now accurate.

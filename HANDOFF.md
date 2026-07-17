# HANDOFF — current state

> Rolling file: overwrite when stopping mid-task. Keep under ~25 lines. History lives in LOG.md.

**Current state (2026-07-16):** The Android-era refresh is MERGED and DEPLOYED (PR #1, squash
`3cabe5e`) — live pianoaudit.com verified byte-identical to `origin/main`. Live now: Google Play
"coming soon" badge, iPhone+Android copy, real Yamaha GP1 screenshots (an actual before/after pitch
correction) captured from the app itself, Pro sample report rendered through the shipping PDF
pipeline, favicon/OG icons from the app icon, privacy policy covering Apple and Google (effective
2026-07-16, mirrored from `~/PianoAnalyzer/docs/legal/`).

**Screenshot regeneration recipe:** see README.md assets section — seed a simulator store with an
exported piano JSON, drive with the app's Debug launch args (`-uiScreen report|compare`,
`-uiDumpReportPDF`), capture via `xcrun simctl io screenshot`. A seeded "PA-Shots iPhone 16 Pro"
simulator exists on `mini`.

**Note for the next agent:** `main` had an unpushed local commit (`bc38056`, AgentHub guidance) that
the PR branch was built on; the squash-merge folded it into `3cabe5e`, so local main needed a reset
to `origin/main`. Content was verified preserved — nothing lost. Push main when you commit to it.

**Known gaps (also in TODO.md):** store badges still say "coming soon" (no listings yet); no Android
screenshot yet (Pixel was mid PDF-fix verification on 2026-07-16); the support restore-purchases
answer assumes Play Billing lands before Android launch (not wired yet).

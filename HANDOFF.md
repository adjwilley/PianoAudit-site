# HANDOFF — current state

> Rolling file: overwrite when stopping mid-task. Keep under ~25 lines. History lives in LOG.md.

**Current state (2026-07-22):** Android app is LIVE on Google Play
(`com.willeypianotuning.pianoaudit`) — the hero Google Play badge is now a real link to the
listing (App Store badge stays "coming soon"; iOS still in review, iTunes lookup returns 0). Prior
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

**Known gaps (also in TODO.md):** App Store badge still "coming soon" — swap to a real link when
iOS clears review (check `itunes.apple.com/lookup?bundleId=com.willeypianotuning.pianoaudit`).
Play Billing is now wired and Android is live, so the support restore-purchases answer is accurate.
`/ptg` still holds not-yet-issued PTG offer codes (Anthony: coming soon) — left untouched.

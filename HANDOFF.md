# HANDOFF — current state

> Rolling file: overwrite when stopping mid-task. Keep under ~25 lines. History lives in LOG.md.

**Current state (2026-07-16):** Site is live at pianoaudit.com (DNS + Pages verified working).
Branch `feat/android-and-real-data` holds the Android-era refresh: Google Play badge, cross-platform
support/privacy copy, real Yamaha GP1 screenshots (before/after pitch correction) captured from the
app itself, regenerated Pro sample report, favicon/OG icons from the shipped app icon.

**Waiting on Anthony:** review + merge the PR (privacy wording and store-availability copy are
escalation items). Merging deploys publicly.

**Screenshot regeneration recipe:** see README.md assets section — seed a simulator store with an
exported piano JSON, drive with the app's Debug launch args (`-uiScreen report|compare`,
`-uiDumpReportPDF`), capture via `xcrun simctl io screenshot`.

**Known gaps (also in TODO.md):** store badges still say "coming soon"; no Android screenshot yet
(Pixel was mid PDF-fix verification on 2026-07-16); Android restore-purchases wording assumes Play
Billing lands before launch.

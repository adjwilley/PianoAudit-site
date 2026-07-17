# PianoAudit-site

Static marketing + legal site for the PianoAudit app — iOS and Android (repo codename PianoAnalyzer), served by GitHub Pages at https://pianoaudit.com. No build step: edit HTML/CSS, push to main, Pages deploys.

- `index.html` — landing page (features, technician section, pricing)
- `privacy/` `support/` — legal + help pages (keep privacy in sync with PianoAnalyzer/docs/legal/)
- `assets/` — screenshots from the app + sample report render + favicon set from the app icon. Screenshots are REAL app output: seed a simulator's store with an exported piano JSON (`Documents/PianoAudit/pianos.json`, envelope `{"schemaVersion":1,"pianos":[…]}`), then use the Debug launch args in the app's `DebugRouteOverride.swift` (`-uiScreen report|compare`, `-uiDumpReportPDF`) and `xcrun simctl io <udid> screenshot`; downscale phone shots to 414×900, report PDF to 850×1100.

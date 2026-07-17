# AGENTS.md

Canonical instructions for AI coding agents (Claude Code, Cowork, Cursor, Codex) working in this repo. CLAUDE.md imports this file. If another document disagrees with this one, this one wins—fix the other document in the same commit.

## What this is

The public static marketing, privacy, and support site for the PianoAudit app — iOS and Android (source repository `~/PianoAnalyzer`). Plain HTML and CSS are served by GitHub Pages at `https://pianoaudit.com`; there is no build system or JavaScript framework. A push to `main` changes the public site.

## Session start

1. Check `git status`, then `git pull` if the worktree is clean.
2. Read `HANDOFF.md` and the last ~10 lines of `LOG.md`.
3. For claims about app behavior, tiers, pricing, or privacy, inspect the current `~/PianoAnalyzer` source/docs rather than trusting website copy from memory.

## Commands

```bash
python3 -m http.server 8000   # preview at http://localhost:8000
git diff --check             # whitespace/conflict-marker sanity
```

There is no build or automated test suite. For visible changes, inspect desktop and narrow/mobile layouts locally and open every changed link.

## Hard rules

1. **The app is the product truth.** Website claims about features, Free/Plus/Pro access, pricing, availability, data handling, and compatibility must match `~/PianoAnalyzer`; verify before editing.
2. **Privacy stays aligned.** `~/PianoAnalyzer/docs/legal/privacy-policy.md` is the canonical policy source. Privacy changes must update/verify both repositories and preserve the meaning in `privacy/index.html`.
3. **DNS and deployment are escalation territory.** Do not change `CNAME`, GitHub Pages settings, domains, or DNS without Anthony's approval.
4. **Keep the site static.** Do not add a framework, package manager, analytics, cookies, trackers, forms, or external runtime dependency without approval and an ADR in the owning product repo when appropriate.
5. **Do not fabricate proof.** Screenshots, reports, testimonials, prices, and performance claims must come from real current product output or Anthony-provided material.
6. **Preserve accessibility and responsive behavior.** Images need meaningful alt text; navigation and content must work without hover and at narrow widths; do not trade legibility for visual polish.
7. **Single source of truth.** Every stated fact lives canonically in one place. Point to or verify the source instead of creating a second independently maintained claim.

## Escalate to Anthony (stop and ask)

- Privacy/legal wording, pricing, subscriptions, App Store availability, or product-positioning changes
- `CNAME`, DNS, GitHub Pages configuration, redirects, or deployment changes
- Analytics, tracking, cookies, data collection, forms, or any new dependency
- Replacing real product screenshots or sample reports with generated/edited representations

## Layout

| Path | Purpose |
|---|---|
| `index.html` | Marketing landing page, features, technician story, pricing |
| `style.css` | All site styling and responsive rules |
| `privacy/index.html` | Public privacy policy; keep aligned with PianoAnalyzer legal docs |
| `support/index.html` | Support and contact information |
| `assets/` | Current app screenshots and sample report |
| `CNAME` | Production custom domain; do not edit without approval |

## Git & continuity

- `main` deploys publicly through GitHub Pages. Use a `feat/` or `fix/` branch for visible, legal, or risky changes; tiny repository-documentation-only changes may go directly to `main`.
- Conventional commits (`feat:`, `fix:`, `docs:`, `chore:`).
- **Log meaningful tasks, not commits or pushes.** Keep one `LOG.md` summary line current while a task is still unpushed: `YYYY-MM-DD | tool@machine | what changed | next step`. Once published, leave it immutable; append only for a distinct task or a milestone/decision another agent needs to resume. Skip trivial formatting, comments, and administrative doc tweaks. The hook requires one summary somewhere on a substantive task branch, not one per push.
- Stopping mid-task? Update `HANDOFF.md` (≤25 lines). Out-of-scope ideas go in `TODO.md`; promote real multi-session work with `gh issue create`.
- Documentation changes in the same commit as the site behavior they describe.

## Definition of done

- [ ] Changed pages previewed locally at desktop and narrow/mobile widths
- [ ] Changed links and image paths opened successfully, including from nested pages
- [ ] Product/privacy claims verified against PianoAnalyzer when affected
- [ ] `git diff --check` passes
- [ ] One concise LOG.md task summary exists if the work is substantive
- [ ] Plain-language summary: what changed and what could be publicly wrong

## Documents

| Doc | When to read |
|---|---|
| `README.md` | Deployment and repository map |
| `~/PianoAnalyzer/AGENTS.md` | Before making or coordinating app-side changes |
| `~/PianoAnalyzer/docs/legal/privacy-policy.md` | Before any privacy wording change |

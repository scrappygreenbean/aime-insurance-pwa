# The Insurance Agent's AIME — Community OS (Installable PWA)

A designed community where **every channel opens to its own real page** — not an
endless feed. Same pattern as the Realtors PWA, branded entirely from the **Insurance**
brand kit. Installable as an app, works offline, no build step.

## Brand (pulled from the kit — not invented)
Source: `AIME/BRAND_PARENT_AIME/THE_INSURANCE_AGENTS_AIM/` (assets) and its
`AIME-Insurance-Playbook/` (the playbook CSS variables, used verbatim).

- **Palette — chrome blue on near-black navy:**
  - `--blue #3FA0DC` (primary azure), `--sky #8FD2FF` (highlight glow),
    `--deep #2C73AB`, `--slate #4C6E8C`, base `--black #000`, `--near-black #0A0E15`,
    text `#E8EEF5`, muted `#A6B6C6`. (Taken straight from the playbook's `:root`.)
- **Logos (real kit assets, copied in):**
  - `FAVICON.PNG` → `aime-emblem.png` — the circular chrome-blue **A** emblem; header logo
    **and** the home-screen app icon.
  - `HERO_BANNER.PNG` → `aime-hero-banner.png` — cinematic hero image on the home page.
  - `WORDMARK.PNG` → `aime-wordmark.png`, `EMBLEM.PNG` → `aime-lockup.png` — kept for reuse.
- **Fonts:** Playfair Display (headers) + Montserrat (body) — the parent AIME type system.

## What's inside
- `index.html` — home hub: channel tiles (**AI Employees** live, **AI Headshots** live,
  Start Here, Resources, Wins, Office Hours) + cinematic hero banner + value strip.
- `ai-employees.html` — gallery of **6 insurance AI Employees**, each opening a detail page
  with a real, ready-to-paste prompt + one-click **Copy**:
  **Policy Explainer, Quote Follow-Up, Claims Helper, Renewal Reminder, Cross-Sell Assistant,
  Review Requester** — written in AIME's voice (direct, honest, client-first, compliance-aware).
- `assets/js/employees.js` — the roster + prompts (edit here to change content).
- `manifest.webmanifest`, `sw.js`, `assets/js/pwa.js` — PWA: installable, offline app-shell
  cache, custom **Install app** button.
- **AI Headshots** → https://headshots.gotaime.com (tile on home + nav link on the team page).

### A note on the prompts
Insurance agents aren't fiduciaries in the legal sense, so the guardrail framing is
**"You stay the licensed advisor."** Every prompt is built so the AI *drafts* but never
makes a coverage determination, promises a claim will be paid, guarantees a price, or
replaces the policy/carrier/adjuster. Suitability and compliance come first.

## View it locally
From this folder:
```
python -m http.server 8078
```
Then open **http://localhost:8078/**. (Use `localhost`/HTTPS — the service worker and
"Install" prompt require a secure context; they won't run from a raw `file://` open.)

To install: open in Chrome/Edge → address-bar install icon, or the **Install app** button.

## Deploy (later)
Any static host. Serve the folder as-is at the domain root. Bump `CACHE` in `sw.js` on each
release so clients pick up changes.

# Runklub Website

Landing page for the Runklub app — a platform connecting runners with local run clubs. Captures waitlist signups and communicates the product's core value proposition.

## Stack

- Pure HTML/CSS/JavaScript — no build tools or npm dependencies
- Hosted on Netlify (form submissions via Netlify Forms)
- Single file: `index.html` contains all markup, styles, and scripts

## Project Structure

```
index.html     — complete website (markup, styles, scripts)
_headers       — Netlify security header configuration
.gitignore
.github/
  workflows/
    claude.yml — Claude Code GitHub Actions integration
```

## Running Locally

Open `index.html` directly in a browser, or serve it with any static file server:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

No build step required.

## Deployment

The site deploys automatically to Netlify on push to `main`. The `_headers` file configures:

- `X-Frame-Options: DENY` — prevents iframe embedding
- `X-Content-Type-Options: nosniff` — prevents MIME sniffing
- `Content-Security-Policy` — restricts resources to self + Google Fonts (inline styles/scripts permitted)
- `Permissions-Policy` — disables camera, microphone, geolocation

## Page Sections

| Section | ID | Purpose |
|---|---|---|
| Navigation | — | Fixed header with links to mission, how it works, waitlist, and app |
| Hero | — | Headline, tagline, CTA button, animated phone mockup |
| Ticker | — | Horizontal scroll banner with location and keyword callouts |
| Why We Built This | `#why` | Mission, core pillars |
| How It Works | `#how` | 4-step user flow |
| Who It's For | — | Audience cards (locals, travellers, athletes) |
| Instagram | — | Placeholder grid, social handle |
| Waitlist | `#waitlist` | Email signup form |
| Footer | — | Links and location |

## JavaScript Functionality

All scripts are inline at the bottom of `index.html`.

**Custom cursor** — tracks `mousemove` events and applies a `.hovered` class when the cursor is over interactive elements (links, buttons, form inputs). CSS handles the visual transformation.

**Waitlist form** — submits to Netlify Forms via `fetch`. On success, swaps the form for a confirmation message. On failure, displays an inline error. Basic email format validation runs client-side before submission.

**Scroll reveal** — uses `IntersectionObserver` to add a `.visible` class when elements with `.step-card`, `.stat`, `.audience-card`, or `.pillar` enter the viewport. CSS transitions handle the fade-in/slide-up effect.

## Responsive Behaviour

Single breakpoint at `900px` (via `@media (max-width: 900px)`):

- Navigation links collapse (hamburger menu not implemented — links are hidden)
- Grid layouts switch from multi-column to single-column
- Phone mockup and hero layout stack vertically
- Typography scales down

## Design Tokens

CSS custom properties defined on `:root`:

| Variable | Value | Usage |
|---|---|---|
| `--ink` | `#0d0f0c` | Primary text, dark backgrounds |
| `--paper` | `#f0ede6` | Page background, light sections |
| `--grass` | `#2d5a1b` | Primary brand green |
| `--acid` | `#b8ff3c` | Accent / highlight colour |
| `--warm` | `#e8d5b0` | Warm section backgrounds |
| `--mist` | `#c8d4c0` | Subtle backgrounds |
| `--rust` | `#c4521a` | Secondary accent |
| `--text-muted` | `#6b7a63` | Secondary text |

**Fonts** (loaded from Google Fonts):
- `Bebas Neue` — display headings
- `Instrument Sans` — body text and UI

## Netlify Forms

The waitlist form uses Netlify's built-in form handling:

```html
<form name="waitlist" method="POST" data-netlify="true">
```

Form submissions appear in the Netlify dashboard under **Forms > waitlist**. No server-side code is required. The JavaScript intercepts submission, posts via `fetch`, and handles the response UI.

---
name: runklub-brand
description: Apply Runklub brand design system to any Runklub deliverable — mobile app screens (React Native / Expo / SwiftUI), website pages (HTML/CSS/React), email templates, Instagram posts, push notifications, and marketing collateral. Triggers on any mention of "Runklub", "runklub.run", "run klub app", "klub", or any task building UI, copy, or visual assets inside the Runklub ecosystem. Always use this skill before generating Runklub code, components, pages, or design files. Enforces the single-font DM Sans system, warm off-white canvas, the Coral/Gold/Sage/Ink palette, and the reserved sunset gradient.
---

# Runklub Brand System

Runklub is a social, location-based run-club app. The brand is **warm, social, dawn-run**. Think Airbnb for run clubs. Not Strava. Not Tracksmith. Not outdoor-crunchy. Warm, accessible, globally scalable.

Everything below is enforceable. If a design choice conflicts with this system, fix the design — the system is right.

---

## The five rules (read these first, every time)

1. **Colour has meaning.** Coral = action. Sage = community. Gold = accent. Ink = structure. Don't use a colour that isn't doing its job.
2. **The gradient is a moment.** Max three gradient surfaces per screen. Reserve it for the logo, splash, hero CTAs, and celebration states.
3. **Canvas, not white.** Every screen sits on `#FBF7F2`. Never pure white. Never grey. Pre-dawn eyes first.
4. **One font, many weights.** DM Sans everywhere. Regular for body, 700 for UI emphasis, 900 italic for wordmarks and display.
5. **Maps are the art.** No stock photography. The map, the pin, the place — those are the visuals. Keep the UI clean so location can shine.

---

## Design tokens (copy-paste)

### Colours

| Token | Hex | Role | Where to use |
|---|---|---|---|
| `canvas` | `#FBF7F2` | Background | Every screen, every page. The base layer. |
| `canvas-alt` | `#F3EDE4` | Contrast surface | Tab switchers, inactive states, subtle dividers, date-badge backgrounds |
| `surface` | `#FFFFFF` | Cards | Elevated content on top of canvas |
| `coral` | `#FF5A4E` | Primary action | CTAs, active tabs, primary buttons, selected states |
| `coral-deep` | `#E8422F` | Coral pressed | Button pressed / hover states |
| `coral-soft` | `#FFD9D3` | Coral tint | Event type backgrounds, subtle coral surfaces |
| `gold` | `#E8A62C` | Accent | Streaks, badges, premium markers, notification dots |
| `gold-soft` | `#F7E4B8` | Gold tint | Achievement backgrounds, highlight surfaces |
| `sage` | `#4F8A6E` | Community | People counts, organiser chips, "going" states, club memberships |
| `sage-soft` | `#D4E5D9` | Sage tint | Going-chip backgrounds, community surfaces, map fill |
| `ink` | `#1A1D24` | Structure | Primary text, tab bars, dark surfaces. Never pure black. |
| `ink-soft` | `#4A4E57` | Secondary text | Body copy, metadata, less important text |
| `ink-muted` | `#8A8F99` | Tertiary text | Labels, captions, placeholders |

### Signature gradient

```
linear-gradient(135deg, #FF5A4E 0%, #FF8A3D 45%, #E8A62C 100%)
```

**Soft variant** (for large backgrounds where the full gradient is too loud):
```
linear-gradient(135deg, #FFD9D3 0%, #FFE4C9 50%, #F7E4B8 100%)
```

### Semantic colours

| Use case | Colour |
|---|---|
| Success / joined | `sage` `#4F8A6E` |
| Error / destructive | `coral-deep` `#E8422F` |
| Warning / attention | `gold` `#E8A62C` |
| Info / neutral | `ink-soft` `#4A4E57` |

Note: Don't invent a separate green for success — sage does both jobs. Colour system stays tight.

### Typography

**One family: DM Sans.** Load from Google Fonts. Used for wordmark, display, UI, and body — every surface.

```html
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,700;0,9..40,900;1,9..40,900&display=swap" rel="stylesheet">
```

**Weights in use:**
- `400` Regular — body text, long-form reading
- `500` Medium — UI labels, metadata, secondary buttons
- `700` Bold — headlines, card titles, emphasis, primary buttons
- `900` Black — display type, large numbers, hero headlines
- `900 italic` — **wordmark only** and occasional celebratory headline accents

**Type scale (mobile and web):**

| Name | Size | Weight | Line height | Letter spacing | Use |
|---|---|---|---|---|---|
| Display XL | 56–72px | 900 | 1.0 | -0.035em | Hero headlines (web) |
| Display L | 40–48px | 900 | 1.05 | -0.03em | Section headlines |
| Display M | 28–32px | 800 | 1.1 | -0.025em | Page titles |
| Title | 18–20px | 700 | 1.2 | -0.015em | Card titles, sheet headers |
| Body L | 16–17px | 400 | 1.5 | 0 | Long-form body |
| Body | 14–15px | 400 | 1.5 | 0 | Default body, list items |
| Label | 12–13px | 600 | 1.4 | 0 | Button labels, UI labels |
| Caption | 11–12px | 500 | 1.4 | 0.02em | Metadata, timestamps |
| Overline | 10–11px | 600 | 1.3 | 0.18em uppercase | Section labels, kickers |

**Numeric / data treatment:** For paces, distances, counts — use weight 700 or 800, letter-spacing -0.015em. Numbers are the heroes of a running app. Give them weight.

### Shape language

- **Corner radii:**
  - `radius-sm`: 8px (chips, small controls)
  - `radius-md`: 12px (buttons, inputs, small cards)
  - `radius-lg`: 16–18px (cards, sheets)
  - `radius-xl`: 24px (large cards, modals)
  - `radius-full`: 999px (pills, avatars, tab switchers)
  - **App icon radius: 230px on a 1024 artboard** (iOS squircle match)

- **Default button shape:** `radius-md` (12px). Pills for filter chips and tab switchers only.

### Spacing

8px base grid. Stick to it.

`4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96, 128`

### Shadows

Lifts should feel warm, not clinical. Warm undertones, long blur, subtle opacity.

| Token | Value | Use |
|---|---|---|
| `shadow-sm` | `0 2px 8px rgba(26, 29, 36, 0.06)` | Small cards, chips |
| `shadow-md` | `0 8px 20px -8px rgba(26, 29, 36, 0.12)` | Cards, sheets |
| `shadow-lg` | `0 20px 40px -20px rgba(26, 29, 36, 0.18)` | Floating panels, tab bar |
| `shadow-coral` | `0 8px 20px -8px rgba(255, 90, 78, 0.45)` | Gradient/coral CTAs only |

---

## Wordmark

**Always:** `run` in regular (400), `klub` in 900 italic. Gradient on klub for primary treatments, solid coral or ink for mono treatments.

```html
<span class="wordmark">
  <span class="wordmark-run">run</span><span class="wordmark-klub">klub</span>
</span>
```

```css
.wordmark {
  font-family: 'DM Sans', sans-serif;
  letter-spacing: -0.035em;
  line-height: 1;
}
.wordmark-run { font-weight: 400; }
.wordmark-klub {
  font-weight: 900;
  font-style: italic;
  background: linear-gradient(135deg, #FF5A4E 0%, #FF8A3D 45%, #E8A62C 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

**Variants:**
- **Primary (sunset gradient)** — hero use, splash screens, marketing
- **Solid coral** — small UI, favicons, when gradient renders poorly
- **Solid ink** — on coloured backgrounds, single-colour print
- **Solid canvas (#FBF7F2)** — on dark backgrounds, app icon shouldn't change

**Never:**
- Bold upright on "klub" (kills the movement)
- All caps
- Tracking above 0 on the wordmark
- Break across two lines unless the whole lockup is vertical
- Outline or stroke treatments
- Drop shadows on the wordmark itself

---

## App icon

- **Artboard:** 1024 × 1024
- **Background:** `#FBF7F2` (canvas)
- **Corner radius:** 230px on the artboard (iOS-matching squircle on export)
- **Composition:** `run` (black, weight 900, upright) in the top half, `klub` (sunset gradient, weight 900, italic) in the bottom half — centered horizontally, generous vertical separation
- **Font size:** 360px at 1024 artboard, letter-spacing -20

SVG source is in `/runklub-icon.svg` — use it as the master. Export to PNG 1024×1024 for App Store.

---

## Components

### Button — primary

```jsx
// React Native
<Pressable style={styles.buttonPrimary}>
  <Text style={styles.buttonPrimaryLabel}>Join Run</Text>
</Pressable>

const styles = {
  buttonPrimary: {
    backgroundColor: '#FF5A4E',
    paddingVertical: 16,
    paddingHorizontal: 24,
    borderRadius: 12,
    alignItems: 'center',
    shadowColor: '#FF5A4E',
    shadowOpacity: 0.35,
    shadowOffset: { width: 0, height: 8 },
    shadowRadius: 20,
    elevation: 4,
  },
  buttonPrimaryLabel: {
    fontFamily: 'DMSans-Bold',
    fontSize: 15,
    fontWeight: '700',
    color: '#FFFFFF',
    letterSpacing: 0.01,
  },
};
```

For hero moments (splash CTA, onboarding completion, "create your first klub"), replace the flat coral with the sunset gradient — but max one per screen.

### Button — secondary

Ink border 1px, transparent fill, ink text, weight 600. `radius-md`. No shadow.

### Button — tertiary / ghost

No border, ink-soft text, weight 500. Underline or chevron on hover.

### Event card (horizontal)

```jsx
<View style={styles.eventCard}>
  <View style={styles.dateBadge}>
    <Text style={styles.dateDow}>SAT</Text>
    <Text style={styles.dateDay}>18</Text>
    <Text style={styles.dateMon}>APR</Text>
  </View>
  <View style={styles.eventBody}>
    <Text style={styles.eventTitle}>Saturday long run</Text>
    <Text style={styles.eventMeta}>4:50/km · 21km · 7:00am · Kurrawa</Text>
    <View style={styles.goingChip}>
      <View style={styles.goingDot} />
      <Text style={styles.goingText}>4 going</Text>
    </View>
  </View>
</View>
```

**Date badge:** `canvas-alt` background (NOT green — green has been retired). Dow label in coral 700 weight, day in ink 900 weight, month in ink-soft 600 weight.

**Going chip:** `sage-soft` background, `sage` text and dot, `radius-full`, weight 700. This is the Sage = Community rule in practice.

### Tab bar (mobile)

- Positioned 16px from bottom
- White surface with `shadow-lg`
- `radius-full` (pill shape)
- Active icon in coral, inside a `coral-soft` rounded-square chip
- Inactive icons in `ink-muted`
- Labels in weight 600, 10px

### Date badges

**Replaced the green badges from the current build.** New rule: date badges use `sunset-soft` gradient background with `coral-deep` DOW label. This reclaims the gradient as a soft brand moment while freeing green-adjacent colours for community-only use (sage).

### Map styling

- Map fill uses `sage-soft` for land
- Water / voids use `canvas`
- Event pins: coral circle, 3px white border, `shadow-coral`
- Club pins: sage circle, 3px white border, standard `shadow-md`
- Selected pin: gradient fill, scales to 1.15x

### Sheets / modals

- `radius-xl` top corners only
- White surface
- Grab handle in `ink-muted`, 36×4px, 8px from top
- `shadow-lg` on the sheet itself
- Backdrop: `rgba(26, 29, 36, 0.4)` with 20px blur

### Input fields

- White surface
- 1px border in `rgba(26, 29, 36, 0.1)`
- `radius-md`
- Focused state: 2px coral border
- 14px/20px padding
- Label above in weight 600, 12px, ink-soft

### Avatars

- `radius-full`
- Default state: sage background, initial in white weight 700
- When user has a photo: 2px white ring
- VIP / organiser states: gradient ring 2px

---

## Voice and copy

Runklub speaks like a friend who runs. Warm, direct, a little playful. Never bro-y. Never corporate. Never aspirational-influencer.

**Do:**
- "Find your people."
- "Run together, live better."
- "3 klubs within 2km."
- "Spin up a klub in 60 seconds."

**Don't:**
- "Unleash your potential." (aspirational-influencer)
- "Optimise your training." (performance-tech — that's Strava)
- "Authenticate your account." (corporate)
- "Crush your PB!" (bro)

**Spelling:** "Klub" with a K, always. "Runklub" as one word, no space, no hyphen. The wordmark is `run` + `klub` but in body copy it's one word.

---

## The gradient — where and where not

**Use it for:**
- Wordmark (klub only)
- App icon
- Splash screen
- Onboarding completion celebration
- Empty state illustrations
- One hero CTA per screen max
- Avatar ring for featured users / organisers
- Push notification icon backgrounds

**Don't use it for:**
- Card backgrounds with text on top
- Tab bars
- Status bars
- Tables / data-dense surfaces
- Large text blocks
- Any surface where it would appear more than twice on screen

**Quick check:** If a teammate looks at a screen and the gradient is the second or third thing they notice, it's being used right. If it's the first and only thing, reduce. If it doesn't appear, the screen is probably fine — the gradient is for moments, not for defaults.

---

## Platform implementation

### Web (HTML/CSS or React)

Use CSS custom properties:

```css
:root {
  --canvas: #FBF7F2;
  --canvas-alt: #F3EDE4;
  --surface: #FFFFFF;
  --coral: #FF5A4E;
  --coral-deep: #E8422F;
  --coral-soft: #FFD9D3;
  --gold: #E8A62C;
  --gold-soft: #F7E4B8;
  --sage: #4F8A6E;
  --sage-soft: #D4E5D9;
  --ink: #1A1D24;
  --ink-soft: #4A4E57;
  --ink-muted: #8A8F99;
  --sunset: linear-gradient(135deg, #FF5A4E 0%, #FF8A3D 45%, #E8A62C 100%);
  --sunset-soft: linear-gradient(135deg, #FFD9D3 0%, #FFE4C9 50%, #F7E4B8 100%);

  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-full: 999px;

  --shadow-sm: 0 2px 8px rgba(26, 29, 36, 0.06);
  --shadow-md: 0 8px 20px -8px rgba(26, 29, 36, 0.12);
  --shadow-lg: 0 20px 40px -20px rgba(26, 29, 36, 0.18);
}

body {
  font-family: 'DM Sans', -apple-system, sans-serif;
  background: var(--canvas);
  color: var(--ink);
  -webkit-font-smoothing: antialiased;
}
```

### React Native / Expo

Create a single `theme.ts` file and import it everywhere. Never hardcode a colour in a component file.

```typescript
// theme.ts
export const colors = {
  canvas: '#FBF7F2',
  canvasAlt: '#F3EDE4',
  surface: '#FFFFFF',
  coral: '#FF5A4E',
  coralDeep: '#E8422F',
  coralSoft: '#FFD9D3',
  gold: '#E8A62C',
  goldSoft: '#F7E4B8',
  sage: '#4F8A6E',
  sageSoft: '#D4E5D9',
  ink: '#1A1D24',
  inkSoft: '#4A4E57',
  inkMuted: '#8A8F99',
} as const;

export const radius = {
  sm: 8, md: 12, lg: 16, xl: 24, full: 999,
} as const;

export const spacing = {
  xs: 4, sm: 8, md: 12, lg: 16, xl: 20, xxl: 24, xxxl: 32,
} as const;

export const type = {
  displayXL: { fontFamily: 'DMSans-Black', fontSize: 56, lineHeight: 56, letterSpacing: -2 },
  displayL:  { fontFamily: 'DMSans-Black', fontSize: 40, lineHeight: 42, letterSpacing: -1.2 },
  displayM:  { fontFamily: 'DMSans-ExtraBold', fontSize: 28, lineHeight: 31, letterSpacing: -0.7 },
  title:     { fontFamily: 'DMSans-Bold', fontSize: 18, lineHeight: 22, letterSpacing: -0.3 },
  bodyL:     { fontFamily: 'DMSans-Regular', fontSize: 16, lineHeight: 24 },
  body:      { fontFamily: 'DMSans-Regular', fontSize: 14, lineHeight: 21 },
  label:     { fontFamily: 'DMSans-SemiBold', fontSize: 13, lineHeight: 18 },
  caption:   { fontFamily: 'DMSans-Medium', fontSize: 12, lineHeight: 17, letterSpacing: 0.25 },
  overline:  { fontFamily: 'DMSans-SemiBold', fontSize: 11, lineHeight: 14, letterSpacing: 2, textTransform: 'uppercase' as const },
} as const;
```

For the gradient in React Native, use `expo-linear-gradient`:

```jsx
import { LinearGradient } from 'expo-linear-gradient';

<LinearGradient
  colors={['#FF5A4E', '#FF8A3D', '#E8A62C']}
  start={{ x: 0, y: 0 }}
  end={{ x: 1, y: 1 }}
  locations={[0, 0.45, 1]}
>
  {/* ... */}
</LinearGradient>
```

For gradient text (the wordmark on the splash screen), use `react-native-masked-view` with `LinearGradient`.

### Font loading

**Web:** Google Fonts link (see Typography section).

**React Native / Expo:** Use `expo-font` with the DM Sans files from Google Fonts (download and bundle).

Required weights to bundle: Regular (400), Medium (500), SemiBold (600), Bold (700), ExtraBold (800), Black (900), Black Italic (900 italic).

---

## Do's and don'ts (quick reference)

**Do:**
- Use `canvas` (`#FBF7F2`) as the default background, everywhere
- Make coral mean "action" — never decorative
- Use sage for anything community/people-related (going counts, organiser chips)
- Reserve the gradient for the wordmark and one hero moment per screen
- Use weight 900 italic on "klub" in the wordmark, every time
- Keep DM Sans as the only font — don't bring in secondary fonts
- Use ink (`#1A1D24`) not pure black for text
- Use warm shadows with subtle opacity

**Don't:**
- Use pure white (`#FFFFFF`) as a page background (it's for cards only)
- Use gold as a primary action colour (it's an accent, not a CTA)
- Use the gradient on anything text-heavy
- Use green for date badges or success states — sage handles community, and success shares sage
- Introduce a second font family, even for a specific component
- Hardcode colours or font sizes in components — import from the theme
- Add drop shadows to the wordmark
- Add new colours to the palette without a functional reason

---

## When Claude Code uses this skill

Every time a Runklub-related task comes in — screen, page, component, email, landing page, Instagram asset, push notification design — follow this sequence:

1. Reference the design tokens from this file. Don't invent new colours.
2. Pick the right colour for the job: coral for action, sage for community, gold for accent, ink for structure.
3. Use DM Sans only. Never import a second font family.
4. Respect the canvas. Background is `#FBF7F2` unless there's a specific reason.
5. Use the gradient sparingly — no more than three surfaces per screen, ideally one.
6. When creating a wordmark, it's always `run` (regular) + `klub` (900 italic, gradient or solid per context).
7. Use the component patterns in this file as starting points, not templates to slavishly copy — they're the language, not the phrasebook.

If a request would break a rule (e.g. "make the background black" or "use a different font for headlines"), push back briefly with the reason and ask if they really want to deviate — one-time override is fine, drift is not.

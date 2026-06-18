---
version: "2.0"
name: "Infisical Design System — Vibe Code Reference"
description: >
  Design tokens and rules for building Infisical-branded mini sites, tools,
  games, and one-off pages. Read this before writing any CSS, JSX, or
  Tailwind. The goal: looks intentional, not AI-generated.
colors:
  bg: "#ffffff"
  bg-dark: "#111111"
  bg-page: "#f3f4f6"
  shade: "#111111"
  void: "#000000"
  text: "#000000"
  text-subtle: "#737373"
  text-muted: "rgba(38,38,38,0.32)"
  text-on-dark: "#e4e4e7"
  text-on-dark-subtle: "#a1a1aa"
  border: "#dcdcdc"
  border-soft: "#dcdcdc"
  border-dark: "#2a2a2a"
  tint: "#c3c3c3"
  tint-strong: "#ececec"
  volt: "#F7FE62"
  accent-green: "#56a600"
  accent-deep-green: "#23776a"
  error: "#8a1208"
typography:
  display:   { font: "500 clamp(36px, 5vw, 56px)/1.1 'Alliance No.2'",  letterSpacing: "-0.03em", textWrap: "balance" }
  headline:  { font: "500 clamp(24px, 3.5vw, 36px)/1.1 'Alliance No.2'", letterSpacing: "-0.03em" }
  title:     { font: "600 18px/1.1 'Alliance No.2'", letterSpacing: "0.02em" }
  body-lg:   { font: "400 18px/1.5 'Alliance No.2'" }
  body-md:   { font: "400 16px/1.5 'Alliance No.2'" }
  body-sm:   { font: "400 14px/1.5 'Alliance No.2'" }
  label:     { font: "600 12px/1.1 'JetBrains Mono'", letterSpacing: "0.06em", textTransform: "uppercase" }
  mono:      { font: "400 14px/1.5 'JetBrains Mono'" }
spacing:
  xs: "4px"
  sm: "14px"
  md: "20px"
  lg: "28px"
  xl: "40px"
  2xl: "68px"
  3xl: "112px"
  layout-max-width: "1280px"
  layout-padding: "40px"
  btn-px: "16px"
  btn-py: "8px"
  card-padding: "32px"
  navbar-height: "56px"
rounded:
  none: "0px"
  mock: "4px"
motion:
  ease:        "cubic-bezier(0.25, 0.1, 0.25, 1)"
  ease-out:    "cubic-bezier(0.23, 1, 0.32, 1)"
  ease-in-out: "cubic-bezier(0.77, 0, 0.175, 1)"
  ease-drawer: "cubic-bezier(0.32, 0.72, 0, 1)"
  dur-press: "120ms"
  dur-fast:  "160ms"
  dur-base:  "200ms"
  dur-slow:  "280ms"
  stagger-step: "50ms"
  press-scale: "0.97"
  enter-scale: "0.95"
---

# Infisical Design System — Vibe Code Reference

> Drop this file into any project or paste it into your agent's context.
> Follow the tokens. Follow the named rules. Ship something that looks
> like it belongs.

This is the whole system. Tokens, components, and rules are all below — copy the snippets you need into your project. There is no `npm install`, no CDN link, no framework dependency. The format is deliberate: a single Markdown file is what an agent can read in one shot, what a designer can skim in five minutes, and what a developer can grep through later.

Every CSS variable, component pattern, and named rule below is the source of truth. If two snippets disagree, the named rule wins. If you find yourself reaching for something that isn't here, check the **Don't Ship These** table at the end before inventing it — the gap is usually intentional.

The minimum install for any consuming project is a Google Fonts import (for the Inter and JetBrains Mono fallbacks) and the token block from §1:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
```

From there, paste the tokens into your stylesheet's `:root` and start building.

---

## 1. Colors

```css
/* === SURFACES === */
--color-bg:               #ffffff;   /* default page/component background */
--color-bg-dark:          #111111;   /* dark variant background */
--color-bg-page:          #f3f4f6;   /* subtle page wash behind content */

/* === TEXT === */
--color-text:             #000000;   /* primary body text */
--color-text-subtle:      #737373;   /* secondary/muted — passes AA */
--color-text-muted:       rgba(38,38,38,0.32); /* decorative metadata only, fails 4.5:1 on white */
--color-text-on-dark:     #e4e4e7;   /* body text on dark surfaces */
--color-text-on-dark-subtle: #a1a1aa;

/* === THE ACCENT === */
--color-volt:             #F7FE62;   /* the one charged accent. use sparingly. */

/* === BORDERS === */
--color-border:           #dcdcdc;   /* all structural lines on light surfaces */
--color-border-dark:      #2a2a2a;   /* all structural lines on dark surfaces */

/* === SYSTEM === */
--color-error:            #8a1208;
```

**Named rules:**

**One-Volt Rule.** Volt (`#F7FE62`) is the single accent. Use it for primary CTA hover state, highlight marks, corner accents, and key data callouts. Never as a section background, body link color, or heading color. If Volt is everywhere, it means nothing.

**Volt-on-Light Rule.** `#F7FE62` on `#ffffff` fails contrast. On light surfaces, Volt is a background highlight only:

```css
/* ✅ correct */
.highlight { background: #F7FE62; color: #000000; padding: 0 4px; }

/* ❌ wrong */
color: #F7FE62; /* on a white/light background */
```

**Binary Surface Rule.** Backgrounds are either `--color-bg` (white) or `--color-bg-dark` (`#111`). No off-white, no warm cream, no gray-800 mid-tones. Pick one and commit.

**Dark Surface Pairings.** Volt on dark *does* pass contrast — it is valid as a text color on `#111111` (unlike light surfaces where it only works as a background).

| Element | Token | Value |
|---|---|---|
| Page background | `--color-bg-dark` | `#111111` |
| Body text | `--color-text-on-dark` | `#e4e4e7` |
| Muted text | `--color-text-on-dark-subtle` | `#a1a1aa` |
| Borders | `--color-border-dark` | `#2a2a2a` |
| Accent | `--color-volt` | `#F7FE62` |

```css
/* Dark surface starter — or drop .theme--dark on any wrapper */
body {
  background: #111111;
  color: #e4e4e7;
}
::selection { background: #F7FE62; color: #000000; }
```

**Selection Rule.** Apply globally in every project:

```css
::selection { background: #F7FE62; color: #000000; }
```

`infisical.css` ships this for you.

---

## 2. Typography

Two fonts. No others.

- **Alliance No.2** — all UI text, headings, body, buttons, labels
- **JetBrains Mono** — code, numbers, metadata, status labels

**Font availability.** Alliance No.2 is a private font (not on Google Fonts). Before sharing a project, copy `Alliance No.2 Regular.otf` and `Alliance No.2 SemiBold.otf` from `~/Library/Fonts/` into your project's fonts folder and update the `@font-face` `src` to point to them. If the font is missing, the stack falls back to **Inter** (Google Fonts) then `system-ui`. Inter is a close geometric match and looks intentional.

```html
<!-- Required Google Fonts import (Inter fallback + JetBrains Mono): -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
```

```css
font-family: 'Alliance No.2', Inter, system-ui, sans-serif;
```

### Type scale

```css
--type-display:   500 clamp(36px, 5vw, 56px)/1.1   'Alliance No.2';  /* letter-spacing: -0.03em; text-wrap: balance — hero headlines */
--type-headline:  500 clamp(24px, 3.5vw, 36px)/1.1 'Alliance No.2';  /* letter-spacing: -0.03em — section headers */
--type-title:     600 18px/1.1                     'Alliance No.2';  /* letter-spacing: 0.02em */
--type-body-lg:   400 18px/1.5                     'Alliance No.2';  /* default prose */
--type-body-md:   400 16px/1.5                     'Alliance No.2';  /* cards, dense areas */
--type-body-sm:   400 14px/1.5                     'Alliance No.2';  /* labels, buttons, nav */
--type-label:     600 12px/1.1                     'JetBrains Mono'; /* letter-spacing: 0.06em; uppercase */
--type-mono:      400 14px/1.5                     'JetBrains Mono'; /* code, data, metadata */
```

**Responsive clamps** are baked into `--type-display` and `--type-headline`. Components inherit responsiveness for free.

**Named rules:**

**One-Family Rule.** Alliance No.2 carries every UI role. JetBrains Mono only for code, numeric data, and the Label role. No third font under any circumstance.

**Uppercase Restraint Rule.** No `text-transform: uppercase` on Alliance No.2 — it breaks the letterforms. Uppercase is only allowed on JetBrains Mono (the Label role), where the monospaced rhythm makes it work. Everything else: sentence case.

**Token-Sized Type Rule.** No hard-coded font sizes in component code. If the size you need isn't in the scale above, use the closest token. If the token genuinely doesn't exist, add it to `infisical.css` first — then use it.

---

## 3. Spacing

```css
--space-xs:    4px;
--space-sm:    14px;
--space-md:    20px;
--space-lg:    28px;
--space-xl:    40px;
--space-2xl:   68px;
--space-3xl:   112px;

--layout-max-width:   1280px;
--layout-padding:     40px;    /* default horizontal page padding */
--btn-px:             16px;
--btn-py:             8px;
--card-padding:       32px;
--navbar-height:      56px;
```

The scale is geometric on purpose — multiples that read as deliberate rhythm, not arbitrary numbers. Stay on the scale. If you need a value between two tokens, you probably need a different layout.

---

## 4. Borders + Shape

```css
--border-width:   1px;
--border-style:   solid;

--radius-none:    0px;    /* all marketing/UI components */
--radius-mock:    4px;    /* product UI illustrations only */
```

**Sharp-Corner Rule.** `border-radius: 0` on every UI element — buttons, cards, inputs, modals, tooltips, dropdowns, panels, banners. Always. No exceptions on marketing or product chrome.

If you're building a game and rounding a sprite or avatar, that's fine — but any UI chrome (buttons, HUD, panels) stays sharp.

**Hairline Rule.** Every layout line reads from `--border-width: 1px`. Sub-pixel widths render inconsistently between `border:` shorthand and background-color divs, so hold the line at 1px. Change the token, change the entire grid.

---

## 5. Elevation

```css
/* No box-shadow on UI chrome. */

/* Only allowed shadow — product illustration elements: */
--shadow-mock: 0 1px 2px rgba(0,0,0,0.06);
```

**Flat-By-Doctrine Rule.** No `box-shadow`, no `drop-shadow`, no glassmorphism on UI surfaces. Depth comes from 1px borders and contrast between surfaces. If you're reaching for a shadow, rethink the layout.

---

## 6. Motion

```css
/* Strong custom easings — not the weak CSS defaults. */
--ease:         cubic-bezier(0.25, 0.1, 0.25, 1);     /* hover, color changes */
--ease-out:     cubic-bezier(0.23, 1, 0.32, 1);       /* entrances, reveals */
--ease-in-out:  cubic-bezier(0.77, 0, 0.175, 1);      /* on-screen movement */
--ease-drawer:  cubic-bezier(0.32, 0.72, 0, 1);       /* iOS-like sheets */

/* Durations — UI animations stay under 300ms. */
--dur-press:  120ms;   /* button press feedback */
--dur-fast:   160ms;   /* button color, tooltips, small popovers */
--dur-base:   200ms;   /* dropdowns, nav state, standard reveals */
--dur-slow:   280ms;   /* modals, drawers, staggered entrances */

--stagger-step: 50ms;
--press-scale:  0.97;
--enter-scale:  0.95;
```

**Frequency Rule.** Before adding motion, count how often the user will see it. Animations on keyboard-initiated actions and anything triggered 100+ times a day are banned — they make the interface feel slow at the exact moment the user expects an instant response. Occasional events (modals, drawers, toasts, section reveals) get standard motion. Rare or first-time events (onboarding, crosshair lens, hero reveals) can carry the most delight.

**Easing Rule.** Entering or exiting → `--ease-out`. Already-on-screen morphing → `--ease-in-out`. Hover and color change → `--ease`. Constant motion → `linear`. **`ease-in` is banned on UI** — it delays the moment the user is watching most closely.

**Physicality.** Nothing in the real world appears from nothing. Entering elements start at `transform: scale(0.95)` with `opacity: 0`, never `scale(0)`. Buttons take `transform: scale(0.97)` on `:active` for tactile feedback. Popovers, dropdowns, and tooltips set `transform-origin` to their trigger location so they scale out from where the user clicked. Modals are the exception — they appear centered and keep `transform-origin: center`.

**Transform-Only Rule.** Animate `transform`, `opacity`, `filter`, and `clip-path` only. Never animate `width`, `height`, `margin`, `top`, `left` — they trigger layout and paint. Cap `blur()` at 8px (Safari performance). Never use `transition: all` — it animates unintended properties off the GPU.

**Interruptibility.** Anything triggered rapidly (toasts, toggles, drags) uses CSS transitions or springs, not `@keyframes`. Transitions retarget mid-flight; keyframes restart from zero and look broken when interrupted. For entry without JS, prefer `@starting-style`. For programmatic CSS animations, prefer WAAPI over Framer Motion shorthand props (`x`, `y`, `scale` are *not* hardware-accelerated; use the full `transform` string).

**Reduced-Motion Rule.** Always include:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

`infisical.css` ships this. Reduced motion means *gentler*, not zero — keep opacity and color transitions that aid comprehension, drop position and scale changes.

---

## 7. Components

### Button

```tsx
// Props
variant: 'primary' | 'secondary' | 'ghost'
size?: 'sm' | 'md' | 'lg'   // default: md
```

| Variant | Default state (light) | Hover state |
|---|---|---|
| `primary` | bg `#000`, text `#fff`, 1px border `#000` | pixel-dither Volt fill, text → `#000` |
| `secondary` | bg transparent, text `rgba(38,38,38,0.32)`, 1px border `#dcdcdc` | text + border → `#000` |
| `ghost` | bg transparent, text `#000`, no border | text → muted |

| Variant | Default state (dark) | Hover state |
|---|---|---|
| `primary` | bg `#000`, text `#e4e4e7`, 1px border `#000` | pixel-dither Volt fill, text → `#000` |
| `secondary` | bg transparent, text `#a1a1aa`, 1px border `#2a2a2a` | text + border → `#e4e4e7` |
| `ghost` | bg transparent, text `#e4e4e7`, no border | opacity 0.6 |

```css
/* All variants share */
border-radius: 0;
position: relative;
overflow: hidden;
transition:
  color           var(--dur-fast)  var(--ease-out),
  background-color var(--dur-fast) var(--ease-out),
  border-color    var(--dur-fast)  var(--ease-out),
  transform       var(--dur-press) var(--ease-out);

&:active { transform: scale(var(--press-scale)); }

@media (prefers-reduced-motion: reduce) {
  transform: none !important;
}
```

**Pixel-dither fill (primary hover).** On `mouseenter`, a grid of Volt-colored cells fills the button in a random shuffled order. On `mouseleave`, cells clear in reverse order. Text sits above the fill on `z-index: 2`. Hover text color must be `#000` — black on Volt passes contrast.

Companion CSS:

```css
.btn--primary { position: relative; overflow: hidden; isolation: isolate; }
.btn--primary > .btn-label { position: relative; z-index: 2; }
.btn--primary .pixel-fill {
  position: absolute; inset: 0; z-index: 1; pointer-events: none; display: grid;
}
.btn--primary .pixel-fill__cell {
  background: var(--color-volt);
  opacity: 0;
  transition: opacity 10ms linear;
}
.btn--primary .pixel-fill__cell.on { opacity: 1; }
@media (prefers-reduced-motion: reduce) {
  .btn--primary .pixel-fill__cell { transition: none; }
}
```

Vanilla JS — drop this in a `<script defer>` and it auto-applies to every `.btn--primary`:

```js
(() => {
  const PIXEL_SIZE = 8;
  const STEP_MS = 10;
  const reduce = matchMedia('(prefers-reduced-motion: reduce)').matches;
  document.querySelectorAll('.btn--primary').forEach((btn) => {
    if (!btn.querySelector('.btn-label')) {
      const label = document.createElement('span');
      label.className = 'btn-label';
      while (btn.firstChild) label.appendChild(btn.firstChild);
      btn.appendChild(label);
    }
    const overlay = document.createElement('span');
    overlay.className = 'pixel-fill';
    overlay.setAttribute('aria-hidden', 'true');
    btn.appendChild(overlay);

    let cells = [], order = [], timer = null;
    const shuffle = (a) => {
      for (let i = a.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [a[i], a[j]] = [a[j], a[i]];
      }
      return a;
    };
    const build = () => {
      const { width, height } = btn.getBoundingClientRect();
      const cols = Math.max(1, Math.ceil(width / PIXEL_SIZE));
      const rows = Math.max(1, Math.ceil(height / PIXEL_SIZE));
      overlay.style.gridTemplateColumns = `repeat(${cols}, 1fr)`;
      overlay.style.gridTemplateRows = `repeat(${rows}, 1fr)`;
      overlay.innerHTML = '';
      cells = Array.from({ length: cols * rows }, () => {
        const c = document.createElement('span');
        c.className = 'pixel-fill__cell';
        overlay.appendChild(c);
        return c;
      });
      order = shuffle([...cells.keys()]);
    };
    const clear = () => { if (timer) { clearInterval(timer); timer = null; } };
    const fill = (dir) => {
      clear();
      if (reduce) { cells.forEach((c) => c.classList.toggle('on', dir === 'in')); return; }
      let i = 0;
      timer = setInterval(() => {
        if (i >= order.length) { clear(); return; }
        const idx = dir === 'in' ? order[i] : order[order.length - 1 - i];
        cells[idx].classList.toggle('on', dir === 'in');
        i++;
      }, STEP_MS);
    };
    build();
    new ResizeObserver(() => {
      const wasOn = cells.some((c) => c.classList.contains('on'));
      build();
      if (wasOn) cells.forEach((c) => c.classList.add('on'));
    }).observe(btn);
    btn.addEventListener('mouseenter', () => fill('in'));
    btn.addEventListener('mouseleave', () => fill('out'));
    btn.addEventListener('focus',      () => fill('in'));
    btn.addEventListener('blur',       () => fill('out'));
  });
})();
```

### Card

```css
/* Light */
background: #ffffff;
border: 1px solid #dcdcdc;
border-radius: 0;
padding: 32px;

/* Dark */
background: #111111;
border: 1px solid #2a2a2a;
border-radius: 0;
padding: 32px;

/* Hover — color transition only, no lift */
transition: border-color var(--dur-fast) var(--ease);
&:hover { border-color: #000000; }
```

### Input / Form Field

```css
/* Light surface */
background: transparent;
border: 1px solid #dcdcdc;
border-radius: 0;
padding: 12px;
font: var(--type-body-sm);
color: #000000;

&:focus-visible {
  border-color: #000000;
  outline: none;
}

/* Dark surface */
background: transparent;
border: none;
border-bottom: 1px solid #2a2a2a;
border-radius: 0;
color: #e4e4e7;
caret-color: #e4e4e7;

&:focus-visible {
  border-bottom-color: #e4e4e7;
  outline: none;
}
/* No glow, no shadow, no ring — on either surface */
```

### Section break

A labelled divider that anchors a section header and proves the F-grid alignment with a green tick at col 1.

```html
<div class="section-break">
  <span class="section-break__tick"></span>
  <span>01 / The case against cleartext context</span>
</div>
```

### Log / code block

Use `.log` for any monospace block — code samples, traces, terminal output. Drop `.redacted` on a span to highlight scrubbed content in Volt; drop `.key` for a muted label.

```html
<pre class="log"><span class="key">auth</span> Bearer <span class="redacted">scoped · 60s</span></pre>
```

---

## 8. Tailwind Quick Reference

Configure your `tailwind.config`:

```js
theme: {
  extend: {
    fontFamily: {
      alliance: ["'Alliance No.2'", "Inter", "system-ui", "sans-serif"],
      mono: ["'JetBrains Mono'", "monospace"],
    },
    colors: {
      volt: "#F7FE62",
    },
  },
}
```

**Common patterns:**

```tsx
// Primary button
"bg-black text-white border border-black hover:text-volt rounded-none px-4 py-2 text-sm transition-colors duration-150"

// Secondary button
"bg-transparent text-[rgba(38,38,38,0.32)] border border-[#dcdcdc] hover:text-black hover:border-black rounded-none px-4 py-2 text-sm transition-colors duration-150"

// Light card
"bg-white border border-[#dcdcdc] p-8"

// Dark card
"bg-[#111111] border border-[#2a2a2a] p-8 text-[#e4e4e7]"

// Volt highlight on text
"bg-volt text-black px-1"

// Muted text
"text-[#737373]"

// Section wrapper
"max-w-[1280px] mx-auto px-10 py-28"

// Mono label
"font-mono text-xs tracking-wider text-[#737373] uppercase"
```

**Tailwind classes to never use:**

```tsx
"rounded"          // ❌ border radius
"rounded-*"        // ❌ any radius variant
"shadow"           // ❌ box shadow
"shadow-*"         // ❌ any shadow variant
"bg-gradient-*"    // ❌ gradient backgrounds
"bg-clip-text"     // ❌ gradient text
"transition-all"   // ❌ animates unintended props off-GPU
```

---

## 9. Copy Voice

- Sentence case everywhere — UI labels, headings, body. No title case kickers.
- No exclamation marks.
- No hype copy (`supercharge`, `blazing fast`, `next-gen`, `revolutionize`).
- No FUD (`don't be the next breach`, `before it's too late`).
- Numbers read as numerals. Code, keys, paths, identifiers run in JetBrains Mono.
- CTAs are imperative and short — `Start`, `Talk to sales`, `Read the docs`.

---

## 10. Don't Ship These

| Pattern | Example | Why it's wrong |
|---|---|---|
| Gradient text | `bg-clip-text text-transparent bg-gradient-to-r` | banned outright |
| Rounded anything | `rounded-lg` on a button or card | sharp corners are the brand |
| Any shadow | `shadow-md` on a panel | flat by doctrine |
| Tracked uppercase on Alliance | `uppercase tracking-widest` on a heading | breaks the letterforms |
| Volt as text color on white | `text-[#F7FE62]` on `#fff` | fails contrast |
| Third font | importing Inter or Plus Jakarta Sans alongside Alliance + Mono | one family + mono only |
| Stock security imagery | shield SVGs, padlock icons, fingerprints | security cliché |
| FUD copy | "Don't be the next breach" | not the voice |
| Generic SaaS layout | hero metric strip + identical icon-and-text card grid | looks templated |
| `transition: all` | `transition: all 300ms` | animates unintended properties off-GPU |
| `scale(0)` entrance | `transform: scale(0)` on enter | nothing appears from nothing — use `scale(0.95)` + opacity |
| `ease-in` on UI | dropdown / modal entering with ease-in | delays the moment the user is watching most |
| Motion on keyboard actions | animated command palette, animated `⌘K` | makes 100+/day actions feel slow |
| `transform-origin: center` on popovers | tooltips scaling from viewport center | popovers scale from their trigger; modals stay centered |
| `@keyframes` on rapid-triggered UI | toast slide-in via keyframes | keyframes restart from zero on interrupt — use transitions |
| Framer Motion `x`/`y` under load | `<motion.div animate={{x:100}} />` while page is loading | shorthands aren't hardware-accelerated — use full `transform` string |
| CSS var on parent driving child transform | `parent.style.setProperty('--x', …)` | recalcs styles on every descendant |

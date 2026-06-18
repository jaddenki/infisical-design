---
version: "2.0"
name: Infisical
description: Infisical's design system. A high-contrast, binary-surface aesthetic with hairline structure, sharp corners, two type families, and Volt as the one charged accent. Drop this file into any project (microsite, tool, game, internal app) and follow the tokens and named rules below.
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
  border-dark: "#2a2a2a"
  tint: "#c3c3c3"
  tint-strong: "#ececec"
  volt: "#F7FE62"
  accent-green: "#56a600"
  accent-deep-green: "#23776a"
  error: "#8a1208"
typography:
  display:
    fontFamily: Alliance No.2
    fontSize: clamp(36px, 5vw, 56px)
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: -0.03em
    textWrap: balance
  headline:
    fontFamily: Alliance No.2
    fontSize: clamp(24px, 3.5vw, 36px)
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: -0.03em
  title:
    fontFamily: Alliance No.2
    fontSize: 18px
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: 0.02em
  body-lg:
    fontFamily: Alliance No.2
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.5
  body-md:
    fontFamily: Alliance No.2
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.5
  body-sm:
    fontFamily: Alliance No.2
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: 0.06em
    textTransform: uppercase
  mono:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
spacing:
  xs: 4px
  sm: 14px
  md: 20px
  lg: 28px
  xl: 40px
  2xl: 68px
  3xl: 112px
  layout-max-width: 1280px
  layout-padding: 40px
  card-padding: 32px
  navbar-height: 56px
  base: 4px
rounded:
  none: 0px
  mock: 4px
motion:
  ease: "cubic-bezier(0.25, 0.1, 0.25, 1)"
  ease-out: "cubic-bezier(0.23, 1, 0.32, 1)"
  ease-in-out: "cubic-bezier(0.77, 0, 0.175, 1)"
  ease-drawer: "cubic-bezier(0.32, 0.72, 0, 1)"
  dur-press: 120ms
  dur-fast: 160ms
  dur-base: 200ms
  dur-slow: 280ms
  stagger-step: 50ms
  press-scale: 0.97
  enter-scale: 0.95
components:
  button-primary:
    backgroundColor: "{colors.void}"
    textColor: "{colors.bg}"
    border: "1px solid {colors.void}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    padding: "8px 16px"
    height: 36px
    hover: "pixel-dither Volt fill; text becomes {colors.void}"
    active: "scale({motion.press-scale})"
  button-secondary:
    backgroundColor: transparent
    textColor: "{colors.text-muted}"
    border: "1px solid {colors.border}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    padding: "11px 20px"
    hover: "text and border become {colors.void}; label scrambles via cipher hover"
    showArrow: "optional 12x12 chevron before label, stroke 1.2, currentColor"
  button-ghost:
    backgroundColor: transparent
    textColor: "{colors.void}"
    border: none
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    padding: "11px 20px"
    hover: "text becomes {colors.text-subtle}; label scrambles via cipher hover"
  cipher-hover:
    appliesTo: "secondary and ghost buttons, inline arrow links — never primary (it has pixel-dither instead)"
    glyphSet: "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%&*?/<>+=-"
    stagger: 22ms
    revealPerChar: 90ms
    glyphInterval: 38ms
    layoutStable: "ghost text reserves final width; absolute-positioned live text overlays during scramble"
    trigger: "mouseenter, focus"
  link-arrow:
    typography: "{typography.body-sm}"
    fontWeight: 500
    textColor: "{colors.void}"
    chevron: "10x10, stroke 1.4, currentColor, 6px gap before label"
    hover: "text becomes {colors.text-subtle}; label scrambles via cipher hover"
  card:
    backgroundColor: "{colors.bg}"
    border: "1px solid {colors.border}"
    rounded: "{rounded.none}"
    padding: "{spacing.card-padding}"
    hover: "border becomes {colors.void}"
  card-dark:
    backgroundColor: "{colors.bg-dark}"
    border: "1px solid {colors.border-dark}"
    rounded: "{rounded.none}"
    padding: "{spacing.card-padding}"
    textColor: "{colors.text-on-dark}"
  input:
    backgroundColor: transparent
    textColor: "{colors.void}"
    border: "1px solid {colors.border}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    padding: "12px"
    focus: "border becomes {colors.void}; no outline ring"
  input-dark:
    backgroundColor: transparent
    textColor: "{colors.text-on-dark}"
    border: "none"
    borderBottom: "1px solid {colors.border-dark}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    focus: "border-bottom becomes {colors.text-on-dark}"
  log:
    backgroundColor: "{colors.bg-dark}"
    textColor: "{colors.text-on-dark}"
    typography: "{typography.mono}"
    border: "1px solid {colors.border-dark}"
    rounded: "{rounded.none}"
    padding: "{spacing.md}"
  cipher-text:
    typography: "{typography.label}"
    glyphSet: "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%&*?/<>+=-"
    stagger: 70ms
    revealPerChar: 220ms
    glyphInterval: 80ms
    maxDuration: 1500ms
    trigger: "IntersectionObserver, threshold 0.4, once"
  highlighted-word:
    backgroundColor: "{colors.volt}"
    textColor: "{colors.void}"
    padding: "0.06em 0.18em"
    margin: "0 0.02em"
    boxDecorationBreak: clone
    pixelSize: 8px
    stepMs: 5ms
    trigger: "IntersectionObserver, paints in once on first scroll into view, then stays filled"
  toggle:
    width: 44px
    height: 22px
    border: "1px solid {colors.border}"
    rounded: "{rounded.none}"
    knobInset: 2px
    knobBackground: "{colors.void}"
    onBackground: "{colors.void}"
    onKnobBackground: "{colors.volt}"
    motion: "knob slides on cubic-bezier(0.34, 1.56, 0.64, 1) at 320ms; knob squashes wider on :active"
  checkbox:
    width: 18px
    height: 18px
    border: "1px solid {colors.border}"
    rounded: "{rounded.none}"
    checkedBackground: "{colors.void}"
    checkStroke: "{colors.volt}"
    checkStrokeWidth: 1.8
    checkLinecap: round
    motion: "stroke-dashoffset draw-in at 220ms; box :active scale(0.92)"
  radio:
    width: 16px
    height: 16px
    border: "1px solid {colors.border}"
    rounded: "{rounded.none}"
    dotSize: 6px
    dotBackground: "{colors.void}"
    motion: "dot scales 0.4 → 1 on cubic-bezier(0.34, 1.56, 0.64, 1) at 240ms"
  select:
    backgroundColor: transparent
    textColor: "{colors.void}"
    border: "1px solid {colors.border}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.none}"
    height: 38px
    padding: "0 12px"
    appearance: none
    chevron: "10x10, stroke 1.4, currentColor, nudges down 1px on hover"
  segmented:
    border: "1px solid {colors.border}"
    rounded: "{rounded.none}"
    height: 36px
    itemPadding: "0 16px"
    itemTypography: "{typography.body-sm}"
    activeBackground: "{colors.void}"
    activeTextColor: "{colors.bg}"
    indicator: "single shared element animated via JS from active button's bounding rect; transform + width on {motion.ease-out}"
  tabs:
    border: "0 0 1px 0 solid {colors.border}"
    gap: "{spacing.lg}"
    itemPadding: "10px 0"
    itemTypography: "{typography.body-sm}"
    activeTextColor: "{colors.void}"
    indicator: "1px hairline at bottom, transform + width animated from active tab's bounding rect"
  slider:
    height: 1px
    track: "{colors.border}"
    thumbWidth: 12px
    thumbHeight: 18px
    thumbBackground: "{colors.void}"
    thumbRadius: 0
  progress:
    height: 6px
    track: "{colors.tint-strong}"
    bar: "{colors.void}"
    voltVariant: "bar becomes {colors.volt}"
    transition: "width {motion.dur-slow} {motion.ease-out}"
  badge:
    border: "1px solid {colors.border}"
    background: transparent
    textColor: "{colors.text-subtle}"
    typography: "{typography.label} at 11px"
    padding: "3px 8px"
    rounded: "{rounded.none}"
    variants:
      solid: "background {colors.void}, text {colors.bg}, border {colors.void}"
      volt: "background {colors.volt}, text {colors.void}, border {colors.volt}"
      green: "text and border {colors.accent-green}"
      error: "text and border {colors.error}"
  avatar:
    size: 32px
    background: "{colors.void}"
    textColor: "{colors.bg}"
    typography: "{typography.label} at 11px"
    rounded: "{rounded.none}"
    stackOverlap: -8px
    stackRing: "2px solid {colors.bg}"
  tooltip:
    background: "{colors.void}"
    textColor: "{colors.bg}"
    typography: "{typography.label} at 11px"
    padding: "6px 10px"
    rounded: "{rounded.none}"
    offset: 8px
    motion: "fade + 4px translate on {motion.dur-fast} {motion.ease-out}; trigger-anchored transform-origin"
  breadcrumb:
    typography: "{typography.body-sm} at weight 500"
    color: "{colors.text-subtle}"
    sepColor: "{colors.text-muted}"
    currentColor: "{colors.void}"
    gap: 10px
  modal:
    background: "{colors.bg}"
    border: "1px solid {colors.void}"
    rounded: "{rounded.none}"
    width: "min(440px, 100%)"
    headerPadding: "18px 20px 16px"
    bodyPadding: "20px"
    footerPadding: "14px 20px"
    sectionDivider: "1px solid {colors.border}"
    backdrop: "rgba(17,17,17,0.5) with 2px blur"
    motion: "drops 8px and scales 0.97 → 1 on cubic-bezier(0.34, 1.2, 0.64, 1) at 360ms; transform-origin center"
    dismiss: "escape, click backdrop, explicit cancel; focus returns to trigger"
  drawer:
    background: "{colors.bg}"
    border: "1px solid {colors.void}"
    rounded: "{rounded.none}"
    width: "min(560px, calc(100% - 32px))"
    position: "bottom-anchored, centered horizontally"
    maxHeight: "calc(100vh - 64px)"
    grip: "48x3 hairline at {colors.border}, becomes {colors.void} on hover, cursor: grab"
    motion: "translateY 100% → 0 on {motion.ease-drawer} at 420ms"
    drag: "pointer drag on grip; release past 40% of drawer height dismisses with continued spring; otherwise snaps back"
  command-palette:
    background: "{colors.bg}"
    border: "1px solid {colors.void}"
    rounded: "{rounded.none}"
    width: "min(520px, 100%)"
    searchPadding: "14px 16px"
    itemPadding: "10px 16px"
    sectionDivider: "1px solid {colors.border}"
    groupLabel: "{typography.label} at 10px, {colors.text-subtle}"
    activeBackground: "{colors.void}"
    activeTextColor: "{colors.bg}"
    activeAccent: "3px {colors.volt} strip on left edge"
    keyboard: "↑/↓ navigate, ↵ select, esc close, ⌘K/⌃K toggle"
  toast:
    background: "{colors.bg-dark}"
    border: "1px solid {colors.border-dark}"
    textColor: "{colors.text-on-dark}"
    rounded: "{rounded.none}"
    padding: "14px 16px 14px 18px"
    minWidth: 320px
    severityStrip: "3px left-edge strip; {colors.volt} for success, {colors.accent-deep-green} for info, {colors.error} for error"
    countdown: "1px progress bar at bottom, scaleX 1 → 0 over 6s linear"
    motion: "enters from right with 24px translate + opacity on {motion.ease-drawer} at 420ms; exit reverses at 240ms"
    stack: "bottom-right portal, newest on top, max 3 visible, older toasts scale 0.94/0.88"
    dismiss: "auto at 6s, manual via × button, swipe-right gesture"
  accordion:
    border: "1px solid {colors.border} top + between + bottom"
    triggerPadding: "18px 16px"
    triggerTypography: "{typography.body-md} at weight 500"
    openBackground: "{colors.bg-page}"
    sign: "14x14 cell with 1.5px crossed bars; vertical bar rotates 90deg on open via cubic-bezier(0.34, 1.2, 0.64, 1)"
    panel: "height animated from 0 → measured content height on {motion.ease-drawer} at 320ms"
    panelInner: "fades + 4px translate with 80ms delay so content appears as panel expands"
  skeleton:
    background: "{colors.tint-strong}"
    animation: "opacity pulse 1 → 0.5 → 1 at 1.6s {motion.ease-in-out} infinite"
    height: 10px
    variants:
      lg: 16px
      xl: 28px
---

# Infisical

## Overview

Infisical's design system is binary and structural. Surfaces are either white (`#ffffff`) or shade (`#111111`), with no mid-tones. Lines are hairline (1px), corners are sharp (0px), and depth comes from contrast and structure rather than shadow. One charged accent, Volt (`#F7FE62`), carries every moment of emphasis. The product looks intentional, not generated: every value below is a token, every named rule below is enforced.

The reference works as a drop-in. Paste the YAML token values into a stylesheet's `:root`, follow the prose rules in each section, and copy the component primitives at the bottom. There is no `npm install` and no required framework. Inter (Google Fonts) is the public fallback for Alliance No.2; JetBrains Mono is the only second face.

## Colors

The palette is built around three surface tokens and one accent. `bg` (`#ffffff`) is the default page and card surface. `bg-dark` (`#111111`) is the only dark surface; treat it as the inverse of `bg`, not as a generic neutral. `bg-page` (`#f3f4f6`) is the optional page wash for sections that need to read quieter than full white. `void` (`#000000`) is reserved for primary text, primary buttons, and the strongest borders. Use `shade` (`#111111`) for inverse contexts.

Text uses a four-step scale. `text` (`#000000`) is primary body text on light. `text-subtle` (`#737373`) is secondary copy and metadata; it passes AA on white. `text-muted` (`rgba(38,38,38,0.32)`) is decorative only and intentionally fails 4.5:1, reserved for ghosted secondary-button labels and timestamp metadata. On dark surfaces, use `text-on-dark` (`#e4e4e7`) for body and `text-on-dark-subtle` (`#a1a1aa`) for muted.

Borders track surface: `border` (`#dcdcdc`) on light, `border-dark` (`#2a2a2a`) on dark. Hover states shift borders toward `void` or `text-on-dark`. Never use a border color outside this pair.

Volt (`#F7FE62`) is the single charged accent. Apply the **One-Volt Rule**: Volt appears as primary-button hover fill, selection background, highlight marks on a single word, corner accents, and key data callouts. Never as a body link color, section background, or heading color. If Volt is everywhere it means nothing.

Volt fails contrast as text on white, so apply the **Volt-on-Light Rule**: on light surfaces, Volt is a background only, paired with `void` text. On dark surfaces Volt does pass contrast and may carry text. Apply `::selection { background: #F7FE62; color: #000000; }` globally in every project.

`accent-green` (`#56a600`) and `accent-deep-green` (`#23776a`) are reserved for tick marks and status indicators in the F-grid; they are not part of the general palette. `error` (`#8a1208`) is the only red.

Apply the **Binary Surface Rule**: backgrounds are `bg` or `bg-dark`, nothing in between. No off-white, no warm cream, no gray-800.

## Typography

Two faces. Alliance No.2 carries every UI role: headings, body, buttons, navigation, labels in sentence case. JetBrains Mono carries code, numeric data, tabular figures, and the `label` role (uppercase, tracked). Alliance No.2 is private; copy `Alliance No.2 Regular.otf` and `Alliance No.2 SemiBold.otf` into the project's fonts folder when shipping, or fall back to Inter via Google Fonts (a close geometric match that holds the personality).

The `typography` tokens define eight roles. The `display` and `headline` tokens use `clamp()` so hero copy scales between mobile and desktop without rules. `title` is the section header weight at a fixed 18px. `body-lg`, `body-md`, and `body-sm` cover long-form, default, and dense copy. `label` is the only uppercase, tracked role and only ever uses JetBrains Mono. `mono` covers all code and tabular numerics.

Apply the **One-Family Rule**: Alliance No.2 plus JetBrains Mono is the complete typographic system. Never import a third face, including Inter when Alliance is loaded, and never use system serifs.

Apply the **Uppercase Restraint Rule**: `text-transform: uppercase` is only valid on JetBrains Mono. Uppercase Alliance breaks the letterforms. Headings, buttons, and body remain sentence case.

Apply the **Token-Sized Type Rule**: never set `font-size` by hand. If the size needed is not in the scale, add the token first, then use it.

Apply the **Navbar Sans Rule**: navbar brand text and nav links use Alliance No.2 in sentence case at `body-sm` or `body-md`, never the mono `label` role. Uppercase mono is reserved for eyebrows, section labels, table headers, badges, and metadata — applying it to top-level navigation makes the chrome read as code, not product. Brand wordmarks may go slightly heavier (weight 500–600) but stay in Alliance.

## Layout

Spacing follows a deliberate, non-linear scale: 4, 14, 20, 28, 40, 68, 112 px. The jumps are intentional rhythm, not arithmetic. Hold a three-step cadence: 14px inside a group, 28px between groups, 68 to 112px between sections. Cards use 32px padding (`card-padding`).

Content sits inside a 1280px maximum width column (`layout-max-width`) with 40px horizontal padding (`layout-padding`) on each side. The navbar is 56px tall (`navbar-height`).

Section breaks anchor an F-grid: vertical hairlines (`vrule`) run the height of major sections, bleeding past the inner content padding to suggest column structure. A green tick at column one labels each section with a Mono section number (`01 / Section name`).

Every layout must work at mobile and desktop. Use the `clamp()` typography tokens and percentage-based widths rather than discrete breakpoints. When a discrete breakpoint is needed, treat 640px, 960px, and 1200px as the canonical thresholds.

## Elevation & Depth

Hierarchy comes from tonal surface change (`bg` to `bg-dark`) and from 1px borders, not from shadow. Apply the **Flat-By-Doctrine Rule**: no `box-shadow`, no `drop-shadow`, no glassmorphism, no backdrop blur on UI chrome. If the urge to reach for a shadow appears, change the layout instead.

The single exception is product illustration: mocks of the Infisical product UI may use `box-shadow: 0 1px 2px rgba(0,0,0,0.06)` to read as a screenshot rather than a panel. Real chrome stays flat.

A subtle SVG grain overlay (fractal noise at low opacity, soft-light blend) may be applied at the page level on hero sections to add tactile character. It is never applied per-component.

## Motion

Use motion only when it clarifies a state change. Most interactions should feel instant. UI motion stays under 300ms; anything slower needs a stated reason.

Apply the **Frequency Rule**: count how often the motion will be seen before adding it. Keyboard-initiated actions (command palette, shortcuts) and anything triggered 100+ times a day get no animation. Hover effects and list navigation (tens of times a day) get drastically reduced or no animation. Occasional events (modals, drawers, toasts, section reveals) get standard timing. Rare or first-time events (onboarding, hero reveals) can carry the most delight.

Apply the **Easing Rule**: entering or exiting uses `ease-out`. On-screen morphing uses `ease-in-out`. Hover and color change uses `ease`. Constant motion uses `linear`. `ease-in` is banned on UI because it delays the exact moment the user is watching most. The built-in CSS easings are too weak; the strong custom curves in the `motion` tokens are the floor.

The four durations cover the full range. `dur-press` (120ms) for button press feedback. `dur-fast` (160ms) for color transitions, tooltips, and small popovers. `dur-base` (200ms) for dropdowns and standard reveals. `dur-slow` (280ms) for modals, drawers, and staggered entrances. Stagger groups at 50ms steps; longer feels slow.

Apply the **Transform-Only Rule**: animate `transform`, `opacity`, `filter`, and `clip-path`. Never animate `width`, `height`, `margin`, `top`, `left`, or any layout property. Never use `transition: all`. Cap `blur()` at 8px for Safari performance. Framer Motion shorthand props (`x`, `y`, `scale`) are not hardware-accelerated under load; use the full `transform` string.

Physicality matters. Nothing in the real world appears from nothing, so entering elements start at `scale(0.95)` plus `opacity: 0`, never `scale(0)`. Buttons take `scale(0.97)` on `:active` for tactile feedback. Popovers, dropdowns, and tooltips set `transform-origin` to their trigger location so they scale out from where the user clicked. Modals are the exception and keep `transform-origin: center` because they appear in the viewport center.

Apply the **Interruptibility Rule**: anything triggered rapidly (toasts, toggles, drags) uses CSS transitions or springs, not `@keyframes`. Transitions retarget mid-flight; keyframes restart from zero and look broken when interrupted. For entry without JS, prefer `@starting-style`. For programmatic motion, prefer WAAPI over JS-driven `requestAnimationFrame`.

Apply the **Reduced-Motion Rule**: honor `prefers-reduced-motion: reduce` by collapsing transitions and animations to 0.01ms. Reduced motion means gentler, not zero. Keep opacity and color transitions that aid comprehension; drop position and scale changes. Gate hover-based motion behind `@media (hover: hover) and (pointer: fine)` so touch devices do not trigger false hovers on tap.

## Shapes

Apply the **Sharp-Corner Rule**: `border-radius: 0` on every UI element. Buttons, cards, inputs, modals, tooltips, dropdowns, panels, banners. The 4px `rounded.mock` token is reserved exclusively for product UI illustrations (screenshots of the Infisical app). Marketing chrome stays sharp without exception.

Apply the **Hairline Rule**: every layout line is exactly 1px. Sub-pixel widths render inconsistently between `border:` shorthand and `background-color` divs, so hold the line at 1px. Change the token, change the entire grid.

If the project is a game and a sprite or avatar needs rounding, that is fine. UI chrome (HUDs, buttons, panels) always stays sharp.

## Components

The `components` block in the frontmatter defines five primitives. Each entry resolves token references via `{colors.*}`, `{typography.*}`, `{spacing.*}`, `{rounded.*}`, and `{motion.*}`.

**Button.** Three variants: `button-primary`, `button-secondary`, `button-ghost`. All share `border-radius: 0`, `position: relative`, `overflow: hidden`, and the same transition profile across `color`, `background-color`, `border-color` (at `dur-fast` with `ease-out`) and `transform` (at `dur-press` with `ease-out`). Every button takes `transform: scale({motion.press-scale})` on `:active`.

The primary variant uses the signature pixel-dither hover fill. On `mouseenter` or `focus`, a grid of 8px Volt-colored cells fills the button in a random shuffled order at 10ms per cell. On `mouseleave` or `blur`, the cells clear in reverse order. The button label sits above the fill at `z-index: 2`. Text becomes `void` (`#000000`) during the hover state, since black on Volt passes contrast. The fill grid resizes with the button via `ResizeObserver`. The cells respect `prefers-reduced-motion` by switching to instant on/off rather than animating.

The secondary variant uses transparent background, `border` (1px `#dcdcdc`), and `text-muted` text. On hover both border and text become `void`, and the label itself runs a tight cipher scramble (see below). Secondary buttons usually carry a 12x12 chevron (`>`) before the label, drawn at `stroke-width: 1.2` in `currentColor`. The ghost variant has no border, `void` text, and shifts to `text-subtle` on hover with the same cipher scramble.

On dark surfaces the variants invert: primary keeps the pixel-dither hover; secondary uses `border-dark` and `text-on-dark-subtle`, shifting to `text-on-dark` on hover; ghost uses `text-on-dark` shifting to opacity 0.6. Both still scramble.

**Cipher hover.** A tight scramble that fires on `mouseenter` or `focus` for every button or link that does not have the pixel-dither affordance (secondary buttons, ghost buttons, inline arrow links). Same glyph set as the section-eyebrow cipher but with snappier timings: 22ms stagger, 90ms reveal per character, 38ms between glyph swaps. Total runtime is under 250ms even on long labels. The scramble must be **layout-stable**: render the final text invisibly to reserve the button's width, then absolutely position the animating text over it. Without this, the in-flight cipher glyphs (mixed-width in Alliance) shove neighboring buttons across the row. Skipped entirely under `prefers-reduced-motion`.

**Inline arrow link.** The `> Read more` pattern. A `body-sm` weight-500 link in `void` (or `text-on-dark` on dark surfaces) prefixed by a 10x10 chevron at `stroke-width: 1.4`, 6px gap. Hover shifts color to `text-subtle` and runs the cipher scramble on the label. Use it inside cards, at the foot of paragraphs, and anywhere a secondary CTA would be too heavy.

**Card.** A 32px-padded surface with a 1px border. On light, the card uses `bg` with `border`; on dark, `bg-dark` with `border-dark`. Hover shifts the border to `void` (or `text-on-dark` on dark) across `dur-fast` with `ease`. No lift, no scale, no shadow.

**Input.** Transparent background, 1px `border`, 12px padding, `body-sm` typography. On focus the border becomes `void` with no outline ring, no glow, no shadow. The dark variant drops the box border for a single bottom border (`border-dark`) that becomes `text-on-dark` on focus.

**Log block.** A monospace block for code samples, traces, and terminal output. Always on `bg-dark`, with `text-on-dark`, `border-dark`, and `mono` typography. Two helper classes: `.key` applies `text-on-dark-subtle` to label tokens, and `.redacted` applies a Volt background with `void` text to highlight scrubbed values.

**Section break.** A labelled divider that anchors a section header and proves F-grid alignment. Renders as a green tick at column one (using `accent-green`) followed by a Mono section number and title (`01 / The case against cleartext context`). The vertical hairlines bracketing the section bleed past the inner content padding to read as column structure rather than chrome.

**Highlighted word.** A flat Volt swatch around a word or short phrase inside a headline, used to charge a single emphasis moment in long display copy. Static fallback is just a Volt background with `void` text, sharp corners, `0.06em 0.18em` padding, and `box-decoration-break: clone` so it wraps cleanly across lines. The animated variant is the same swatch but it paints itself in via the pixel-dither effect the first time it scrolls into view (8px cells at 5ms per cell), then stays filled. This is the only place pixel-dither runs as an entrance rather than a hover. Use it on hero and section headlines, never on body text or buttons, and never more than once per headline.

**Cipher text.** A scramble-to-reveal effect for mono eyebrows and section labels. On scroll into view, each character cycles random glyphs from the cipher set, then locks in left-to-right with a 70ms stagger and a 220ms reveal-per-character. Total animation is capped at 1500ms regardless of string length. Triggered once via `IntersectionObserver` at 40% visibility. Honors `prefers-reduced-motion` by rendering the final string immediately. Use it on Mono labels only; the glyph widths line up with monospace and look broken on Alliance.

### Code

Two snippets that prose alone cannot carry: the pixel-dither button hover, and the cipher text scramble.

**Pixel-dither button.** Wrap the button label so the fill grid sits behind it. Apply on every `.btn--primary`.

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

```js
(() => {
  const PIXEL_SIZE = 12;
  const STEP_MS = 3;
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

**Cipher hover (buttons + links).** Wrap each button or link's text label in `<span data-cipher-hover>`. The script upgrades the span to a ghost + live structure so the scramble never shifts neighboring elements.

```css
.cipher-hover { position: relative; display: inline-block; white-space: nowrap; }
.cipher-hover__ghost { visibility: hidden; }
.cipher-hover__live  { position: absolute; inset: 0; display: flex; align-items: center; justify-content: center; white-space: nowrap; }
```

```html
<button class="btn btn--secondary">
  <svg class="btn__chev" viewBox="0 0 12 12"><path d="M4.5 2.5L8 6l-3.5 3.5"/></svg>
  <span data-cipher-hover>Read the docs</span>
</button>
```

```js
(() => {
  const GLYPHS = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%&*?/<>+=-";
  const STAGGER = 22, REVEAL_PER_CHAR = 90, GLYPH_INTERVAL = 38;
  if (matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  const rand = () => GLYPHS[Math.floor(Math.random() * GLYPHS.length)];

  document.querySelectorAll('[data-cipher-hover]').forEach((el) => {
    const target = el.textContent;
    el.classList.add('cipher-hover');
    el.innerHTML = '';
    const ghost = document.createElement('span'); ghost.className = 'cipher-hover__ghost'; ghost.textContent = target;
    const live  = document.createElement('span'); live.className  = 'cipher-hover__live';  live.textContent  = target;
    live.setAttribute('aria-hidden', 'true');
    el.append(ghost, live);

    let raf = null;
    const scramble = () => {
      cancelAnimationFrame(raf);
      const start = performance.now();
      const total = target.length * STAGGER + REVEAL_PER_CHAR + 80;
      const state = target.split('').map(() => ({ lastSwap: 0, glyph: rand() }));
      const tick = (now) => {
        const elapsed = now - start;
        let out = '';
        for (let i = 0; i < target.length; i++) {
          const ch = target[i];
          if (ch === ' ') { out += ' '; continue; }
          if (elapsed >= i * STAGGER + REVEAL_PER_CHAR) { out += ch; continue; }
          const s = state[i];
          if (elapsed - s.lastSwap >= GLYPH_INTERVAL) { s.glyph = rand(); s.lastSwap = elapsed; }
          out += s.glyph;
        }
        live.textContent = out;
        if (elapsed < total) raf = requestAnimationFrame(tick);
        else live.textContent = target;
      };
      raf = requestAnimationFrame(tick);
    };

    const parent = el.closest('button, a') || el;
    parent.addEventListener('mouseenter', scramble);
    parent.addEventListener('focus', scramble);
  });
})();
```

**Cipher text.** Vanilla port of the production React component. Add `data-cipher` to any element whose text content should scramble in on scroll.

```html
<span class="label" data-cipher>01 / The case against cleartext context</span>
```

```js
(() => {
  const GLYPHS = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%&*?/<>+=-";
  const STAGGER = 70, REVEAL_PER_CHAR = 220, GLYPH_INTERVAL = 80, MAX_DURATION = 1500;
  const reduce = matchMedia('(prefers-reduced-motion: reduce)').matches;
  const rand = () => GLYPHS[Math.floor(Math.random() * GLYPHS.length)];

  const scramble = (el) => {
    const target = el.dataset.cipherText || el.textContent;
    el.dataset.cipherText = target;
    if (reduce) { el.textContent = target; return; }
    const start = performance.now();
    const baseTotal = target.length * STAGGER + REVEAL_PER_CHAR + 200;
    const stagger = baseTotal > MAX_DURATION && target.length > 0
      ? Math.max(0, (MAX_DURATION - REVEAL_PER_CHAR - 200) / target.length)
      : STAGGER;
    const total = target.length * stagger + REVEAL_PER_CHAR + 200;
    const state = target.split('').map(() => ({ lastSwap: 0, glyph: rand() }));
    const tick = (now) => {
      const elapsed = now - start;
      let out = '';
      for (let i = 0; i < target.length; i++) {
        const ch = target[i];
        if (ch === ' ') { out += ' '; continue; }
        const revealAt = i * stagger + REVEAL_PER_CHAR;
        if (elapsed >= revealAt) { out += ch; continue; }
        const s = state[i];
        if (elapsed - s.lastSwap >= GLYPH_INTERVAL) { s.glyph = rand(); s.lastSwap = elapsed; }
        out += s.glyph;
      }
      el.textContent = out;
      if (elapsed < total) requestAnimationFrame(tick);
      else el.textContent = target;
    };
    requestAnimationFrame(tick);
  };

  const io = new IntersectionObserver((entries) => {
    entries.forEach((e) => { if (e.isIntersecting) { scramble(e.target); io.unobserve(e.target); } });
  }, { threshold: 0.4 });
  document.querySelectorAll('[data-cipher]').forEach((el) => io.observe(el));
})();
```

### Controls

Eight control primitives carry every input state in the system: `toggle`, `checkbox`, `radio`, `select`, `segmented`, `tabs`, `slider`, `progress`. All hold the **Sharp-Corner Rule** and the **Hairline Rule** — no radii, no shadows, single-pixel borders.

**Toggle.** A 44×22 rectangle with a 1px `border`. The knob is an inset 16×16 `void` square that slides on `cubic-bezier(0.34, 1.56, 0.64, 1)` at 320ms. On `aria-checked="true"`, the track fills `void` and the knob switches to `volt` — a charged moment that earns the One-Volt allowance. The knob squashes ~2px wider on `:active` and shifts back toward the trailing edge for tactile feedback. Track is the only place Volt appears on a toggle; never tint the track itself.

**Checkbox.** An 18×18 box with a 1px `border`. The check mark is an SVG path drawn at `stroke-width: 1.8` with `linecap: round`, animated via `stroke-dashoffset` from 14 to 0 over 220ms after the fill switches to `void`. Apply the **Optical-Centering Rule**: the geometric center of a check-mark path sits visually right-heavy because the long up-right stroke carries more weight. Shift the path left by ~0.5 viewBox units and pull the SVG element 1px right with margin to compensate. On `:active`, the whole box takes `scale(0.92)`.

**Radio.** A 16×16 box (not a circle — sharp corners apply) with a 6×6 `void` dot inside. The dot scales 0.4 → 1 on the same spring as the toggle knob. Group selection follows standard radio semantics; only one is checked per group.

**Select.** A 38px-tall button rendered with `appearance: none` so cross-browser height stays consistent. Holds 1px `border`, transparent background, 12px horizontal padding, no left padding adjustment for the chevron. The 10×10 chevron nudges down 1px on hover to suggest "drops down." Placeholder rows use `text-subtle`; values use `void`. The popup list itself is a `command-palette` when search is needed and a positioned dropdown when not — never a native `<select>` element in product chrome.

**Segmented.** A bordered inline-flex of equal-height buttons separated by 1px hairlines. The active button shows the `void` fill / `bg` text inversion, but the fill comes from a **single shared indicator element** positioned absolutely behind the buttons, not from a per-button background. On selection change, the indicator's `transform: translateX()` and `width` animate to the newly active button's bounding rect on `dur-slow` with `ease-out`. Apply the **Sliding-Indicator Rule** to tabs and segmented controls alike: one element, measured from the DOM with `getBoundingClientRect()`, animated with `transform` + `width`. Never animate per-button background-color cross-fades — they look like a flicker, not a slide.

**Tabs.** A flex row with a 1px bottom `border`. Active tab takes `void` text; inactive tabs take `text-subtle`. The active underline is a 1px shared indicator pinned to the bottom hairline, animated under the Sliding-Indicator Rule above. Tabs read content-width; no equal-distribution unless the container demands it.

**Slider.** A 1px hairline track in `border`, a 12×18 sharp `void` thumb (no border-radius, no thumb shadow). Cross-browser thumb rendering requires both `::-webkit-slider-thumb` and `::-moz-range-thumb` blocks. The track does not fill behind the thumb — value is read from the thumb position, not from a colored progress arc.

**Progress.** A 6px track in `tint-strong` with a `void` bar; width animates on `dur-slow` `ease-out`. The Volt variant exists for the single most-important progress moment per view (key generation, encryption, deploy). Apply the **One-Volt Rule** here too: most progress bars stay `void`; promote to Volt only when the bar itself is the story.

### Identity & metadata

**Badge.** A 1px-bordered pill (still sharp-cornered) with `label` typography at 11px. Default is a transparent background, `text-subtle`, `border` border. The four variants — `solid`, `volt`, `green`, `error` — each set background, text, and border in one move so the badge always reads as a single token. The optional 6×6 `dot` inside picks up `currentColor`, useful for status badges (`Live`, `Failed`, `Pending`). Badges never gain a third color beyond their variant.

**Avatar.** A 32×32 `void` square with `bg`-colored mono initials at `label` size. Variants: `volt` (yellow background, void text), `outline` (transparent, void text, hairline border). Stacks render as inline-flex with `-8px` margin-left overlap; each avatar in a stack gets a 2px `bg` outline to read as separated. Overflow stacks end with a `+N` count avatar in the default style.

**Breadcrumb.** A flex row of Alliance `body-sm` weight-500 links separated by `/` characters in `text-muted`. Trail links are `text-subtle`, current page is `void`. Apply the **Breadcrumb Sans Rule** (a corollary of Navbar Sans): breadcrumbs never adopt the mono `label` treatment — they are wayfinding for product, not metadata, and the mono uppercase makes them read as code paths.

**Tooltip.** A `void`-background pill with `bg` text in `label` 11px, 6×10 padding, 8px offset from trigger. Fades in with a 4px upward translate on `dur-fast` `ease-out`. Apply the **Trigger-Anchored Origin Rule** to tooltips, popovers, and dropdowns: `transform-origin` matches the side of the trigger the surface emerges from (top, bottom, left, right), not center. The triangular pointer is a CSS pseudo-element with `border` triangle hack — no SVG, no shadow.

### Overlays

Four overlay primitives — `modal`, `drawer`, `command-palette`, `toast` — share a portal-based mount, focus return on close, and `body { overflow: hidden }` while open. Each lives at `z-index: 1000+`.

**Modal.** A 440px-max sharp-cornered card with three structural zones separated by hairlines: head (eyebrow label + close button), body (title + content), foot (hint + action row). Drops in with `translateY(8px)` + `scale(0.97)` → identity on `cubic-bezier(0.34, 1.2, 0.64, 1)` at 360ms; backdrop is `rgba(17,17,17,0.5)` with a 2px blur that fades over `dur-base`. Apply the **Modal Center-Origin Rule**: modals keep `transform-origin: center` because they appear in the viewport center, not at a trigger. Esc, backdrop click, and explicit cancel all dismiss; focus returns to the trigger element via stored ref.

**Drawer.** A bottom-anchored sheet (vaul-style), 560px-max, centered horizontally with 16px gutters. Slides up from `translateY(100%)` on `ease-drawer` (`cubic-bezier(0.32, 0.72, 0, 1)`) at 420ms — a deeper, dampened curve than `ease-out` because the drawer travels further than a modal. A 48×3 hairline grip at the top reads as a drag handle (`cursor: grab`); on hover it darkens from `border` to `void`. Apply the **Drag-Dismiss Rule**: pointer drag on the grip translates the drawer in real time (no transition during drag), rubber-bands at the top boundary, and on release past 40% of drawer height continues the dismiss animation; under 40% it springs back. Use the drawer for multi-field forms, settings panels, and any flow that wants more vertical real estate than a modal grants.

**Command palette.** A 520px-max sharp card with a search input at top, grouped result rows, and a keyboard-hint footer. Search rows are 14×16 padded with a 14px search icon left of the input and an `esc` hint right. Result groups carry an uppercase mono `label`-style header (`Actions`, `Routines`, `Navigate`). Each row is a 14px icon glyph + label + `meta` tag in mono. The active row inverts to `void` background, `bg` text, and gains a 3px Volt accent strip on its left edge — the One-Volt allowance for keyboard focus. Apply the **Keyboard-First Rule**: ⌘K / ⌃K toggles globally; ↑/↓ navigates results; ↵ selects; esc closes. Per the Frequency Rule, the palette opens with no fade — it appears instantly, because anyone using it 100+ times a day must not wait.

**Toast.** A dark surface notification, 320px-min, stacked bottom-right in a fixed portal. Carries a 3px severity strip on its left edge (`volt` for success, `accent-deep-green` for info, `error` for error), a mono eyebrow with kind + relative timestamp, and an Alliance body. A 1px progress bar at the bottom counts down via `transform: scaleX(1 → 0)` over 6s linear, then the toast exits to the right with a 24px translate and an opacity fade. Apply the **Toast Stack Rule**: maximum three visible, newest on top, older toasts scale to 0.94 then 0.88 as they get buried. Manual dismiss via `×` button cancels the auto-timer immediately and runs the exit animation. Swipe-right gesture also dismisses on touch. Toasts never carry buttons — they are notifications, not interactions; route any action to the originating surface.

### Feedback

**Accordion.** A vertical list of items separated by 1px hairlines, with the open item taking a `bg-page` wash. Trigger row is a grid of `[24px num | 1fr label | 14px sign]` — the number is a `label`-style "01" mono prefix, the sign is a 14×14 cell holding crossed `void` bars. Apply the **Plus-to-Minus Rule**: the vertical bar of the sign rotates 90° to merge with the horizontal bar on open, using `cubic-bezier(0.34, 1.2, 0.64, 1)` at 320ms — a morph, not a scale-out. The expand uses the **Measured-Height Rule**: read `inner.getBoundingClientRect().height` via JS and animate the panel's `height` property from `0px` to that measured value on `ease-drawer` at 320ms, then set `height: auto` after the transition completes so the open content can resize freely. The `grid-template-rows: 0fr → 1fr` trick is too new and too inconsistent across browsers to rely on. Inner content fades + translates 4px with an 80ms delay so it appears as the panel opens rather than during.

**Skeleton.** A `tint-strong` block that pulses opacity from 1 → 0.5 → 1 on a 1.6s `ease-in-out` infinite loop. Apply the **Skeleton-Pulse Rule**: no shimmer gradient, no animated background-position, no traveling highlight band. Just opacity. The skeleton's job is to hold the row geometry while data loads, not to perform — a shimmer reads as decoration and competes with surrounding content. Three sizes: 10px default, 16px `lg` (titles), 28px `xl` (heading rows or buttons). Group skeletons into a bordered list that mirrors the final layout exactly (avatar block + line stack + status badge + action) so the swap from skeleton to data is geometrically silent.

## Voice & Content

Copy is part of the design.

Use sentence case everywhere, including UI labels, headings, and body. No title-case kickers. No exclamation marks. No hype copy (`supercharge`, `blazing fast`, `next-gen`, `revolutionize`) and no FUD (`don't be the next breach`, `before it's too late`). Numbers read as numerals. Code, keys, paths, and identifiers always set in JetBrains Mono.

CTAs are imperative and short: `Start`, `Talk to sales`, `Read the docs`. Errors are concrete: what happened plus what to do next. Empty states point to the first action. In-progress states use the present participle with an ellipsis character (`Saving…`).

Curly quotes, the ellipsis character (not three dots), and en dashes for ranges. No `please` and no marketing superlatives.

## Do's and Don'ts

Hold the gray scale for hierarchy: `text` for primary, `text-subtle` for secondary, `text-muted` for decorative metadata only.

Hold WCAG AA contrast (4.5:1) on every body text token. Volt only ever appears on `void` or `bg-dark`. Show a visible focus state on every interactive element at `:focus-visible`, and never remove an outline without a visible replacement.

Apply the typography tokens instead of setting font size, line height, or weight by hand. Apply the spacing tokens instead of one-off pixel values.

Do not signal state with color alone; pair it with an icon or text label. Do not use `bg-page` as a general fill; it is for subtle separation only. Do not mix sharp and rounded corners in one view. Do not import a third font family.

Specific patterns to never ship:

Gradient text (`bg-clip-text` with a gradient), any border-radius variant on chrome, any `box-shadow`, `text-transform: uppercase` on Alliance, Volt as a text color on white, a third font, stock security imagery (shield SVGs, padlock icons, fingerprints), FUD copy, generic SaaS hero-and-icon-card layouts, `transition: all`, `scale(0)` entrances, `ease-in` on UI, animation on keyboard-triggered actions, `transform-origin: center` on trigger-anchored popovers, `@keyframes` on rapidly-triggered UI, Framer Motion `x`/`y` shorthand under load, and updating a CSS variable on a parent to drive a child transform.

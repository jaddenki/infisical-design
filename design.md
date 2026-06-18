---
name: Infisical Design System
description: The Infisical design system — binary surfaces, hairline chrome, one charged Volt accent, x-ray motion. Black, white, and #F7FE62.
version: 2.0
colors:
  bg: "#ffffff"
  bg-dark: "#111111"
  bg-page: "#000000"
  shade: "#111111"
  void: "#000000"
  text: "#000000"
  text-subtle: "#737373"
  text-muted: "rgba(38,38,38,0.32)"
  text-on-dark: "#e4e4e7"
  text-on-dark-subtle: "#a1a1aa"
  border: "#c3c3c3"
  border-soft: "#dcdcdc"
  border-dark: "#2a2a2a"
  tint: "#c3c3c3"
  tint-strong: "#ececec"
  volt: "#F7FE62"
  accent-green: "#56a600"
  accent-deep-green: "#23776a"
  error: "#8a1208"
  mock-surface: "#ffffff"
  mock-border: "#dbdee5"
  mock-text: "#14171f"
  mock-text-muted: "#808591"
  mock-check: "#3ba55d"
  mock-badge-green-bg: "#e0f7e8"
  mock-badge-green-text: "#0f7a47"
  mock-badge-red-bg: "#faebeb"
  mock-badge-red-text: "#b82924"
  mock-badge-amber-bg: "#fdf0dd"
  mock-badge-amber-text: "#b45309"
typography:
  display:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "clamp(36px, 5vw, 56px)"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "-0.03em"
    textWrap: "balance"
  headline:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "clamp(24px, 3.5vw, 36px)"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "-0.03em"
  title:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "18px"
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: "0.02em"
  body-lg:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1.5
    textWrap: "pretty"
  body-md:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.5
  body-sm:
    fontFamily: "Alliance No.2, Inter, system-ui, sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontFamily: "JetBrains Mono, ui-monospace, monospace"
    fontSize: "12px"
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: "0.06em"
    textTransform: "uppercase"
  mono:
    fontFamily: "JetBrains Mono, ui-monospace, monospace"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.5
spacing:
  xs: "4px"
  sm: "14px"
  md: "20px"
  lg: "28px"
  xl: "40px"
  2xl: "68px"
  3xl: "112px"
  4xl: "128px"
  gutter: "28px"
  content-padding: "40px"
  grid-padding: "68px"
  section-py: "112px"
  sectionbreak-py: "128px"
  btn-px: "16px"
  btn-py: "8px"
  card-padding: "32px"
  max-width: "1280px"
  navbar-height: "56px"
  announcement-height: "40px"
rounded:
  none: "0px"
  mock: "4px"
motion:
  ease: "cubic-bezier(0.25, 0.1, 0.25, 1)"
  ease-out: "cubic-bezier(0.23, 1, 0.32, 1)"
  ease-in-out: "cubic-bezier(0.77, 0, 0.175, 1)"
  ease-drawer: "cubic-bezier(0.32, 0.72, 0, 1)"
  dur-press: "120ms"
  dur-fast: "160ms"
  dur-base: "200ms"
  dur-slow: "280ms"
  stagger-step: "50ms"
  press-scale: "0.97"
  enter-scale: "0.95"
components:
  button-primary:
    backgroundColor: "{colors.void}"
    textColor: "{colors.bg}"
    border: "1px solid {colors.void}"
    rounded: "{rounded.none}"
    padding: "{spacing.btn-py} {spacing.btn-px}"
    typography: "{typography.body-sm}"
  button-primary-hover:
    backgroundColor: "{colors.void}"
    textColor: "{colors.volt}"
    effect: "pixel-dither fill"
  button-secondary:
    backgroundColor: "transparent"
    textColor: "{colors.text-muted}"
    border: "1px solid {colors.border-soft}"
    rounded: "{rounded.none}"
    padding: "{spacing.btn-py} {spacing.btn-px}"
    typography: "{typography.body-sm}"
  button-secondary-hover:
    backgroundColor: "transparent"
    textColor: "{colors.void}"
    border: "1px solid {colors.void}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.text}"
    border: "none"
    rounded: "{rounded.none}"
    padding: "{spacing.btn-py} {spacing.btn-px}"
    typography: "{typography.body-sm}"
  card:
    backgroundColor: "{colors.bg}"
    textColor: "{colors.text}"
    border: "1px solid {colors.border-soft}"
    rounded: "{rounded.none}"
    padding: "{spacing.card-padding}"
  card-dark:
    backgroundColor: "{colors.bg-dark}"
    textColor: "{colors.text-on-dark}"
    border: "1px solid {colors.border-dark}"
    rounded: "{rounded.none}"
    padding: "{spacing.card-padding}"
  input:
    backgroundColor: "transparent"
    textColor: "{colors.text}"
    border: "1px solid {colors.border-soft}"
    rounded: "{rounded.none}"
    padding: "12px"
    typography: "{typography.body-sm}"
  input-focus:
    border: "1px solid {colors.void}"
    outline: "none"
  section-container:
    backgroundColor: "{colors.bg}"
    rounded: "{rounded.none}"
    padding: "{spacing.section-py} {spacing.grid-padding}"
  section-container-dark:
    backgroundColor: "{colors.shade}"
    textColor: "{colors.text-on-dark}"
    rounded: "{rounded.none}"
    padding: "{spacing.section-py} {spacing.grid-padding}"
---

# Infisical

The Infisical design system reads like an instrument, not a brochure. The surface is built to be inspected: hairline borders divide every region, an F-grid sits behind the layout to prove the alignment, and a constant grain overlay reminds you you are looking at something rendered, not painted. A secrets-management product that takes engineering seriously builds its interfaces the same way.

The palette is binary by intent. Surfaces are white or near-black, ink is the opposite, and one charged lime — Volt, `#F7FE62` — does all the energy work. There is no secondary or tertiary accent in the marketing chrome. Color carries meaning, not decoration. Remove Volt and the page should still feel like Infisical.

## Colors

A binary palette: pure white or near-black surfaces, with one charged accent. The supporting greens are reserved for narrow product use (label ticks, gradient termini), never as CTAs.

**Volt** (`#F7FE62`) is the single brand accent. It appears on no more than ten percent of any screen — as a primary-button hover text color, a CTA panel fill in the footer accent gutter, highlight marks behind short phrases, key data callouts, and corner accents. It is never a section background, never a body link color, never a heading color. Its rarity is the point. Volt fails contrast as a foreground on white, so on light surfaces it is a background only; place black text on top and treat it as a highlight chip, not a hue.

**Void** (`#000000`) is primary text and the primary button fill on light surfaces, and the page-outer background on dark wrappers. **Shade** (`#111111`) is the dark-section background — black-but-not-pure, so on-shade hairlines have somewhere to sit. **Bg White** (`#ffffff`) is the default section surface; the grain overlay supplies texture, the surface itself stays pure.

Borders are quiet but constant. **Hairline** (`#c3c3c3`) and the slightly warmer **Border Soft** (`#dcdcdc`) carry every horizontal rule, vertical content border, and F-grid line on light surfaces; **Hairline Dark** (`#2a2a2a`) does the same on Shade. **Tint** (`#c3c3c3`) and **Tint Strong** (`#ececec`) are non-line greyscale used for subtle zone fills.

Body text uses **Void** on light and **Text on Dark** (`#e4e4e7`) on shade. **Text Subtle** (`#737373`) carries muted prose on either surface and passes AA. **Text Muted** (`rgba(38,38,38,0.32)`) is decorative only — it fails 4.5:1 against white and must be reserved for non-essential metadata such as timestamps, captions, and inactive nav chevrons.

The product-mock palette (`#dbf530`-era badge greens, ambers, and reds) is siloed inside `.v2-mock-*` dashboard illustrations. It signals "this is the app UI," not the marketing site, and never bleeds into chrome.

**Selection.** Apply globally: `::selection { background: #F7FE62; color: #000000; }`.

## Typography

Two families, no others. **Alliance No.2** carries every UI text role — display, headlines, body, buttons, navigation, prose. **JetBrains Mono** enters for code, numeric data, status labels, and field metadata. Alliance is private; copy `Alliance No.2 Regular.otf` and `Alliance No.2 SemiBold.otf` into the project and update `@font-face`. Fall back to Inter, then `system-ui`.

Hierarchy comes from scale and weight, never from typeface mixing. The Display role is Alliance No.2 at weight 500, clamping from 36px to 56px with `-0.03em` letter-spacing and `text-wrap: balance` — reserved for hero headlines and section breakouts. Headline is the same family and weight, clamping 24px to 36px, used for section openers. Title is Alliance No.2 at weight 600, 18px, with `0.02em` tracking — named sub-blocks, used sparingly. Body is Alliance No.2 at weight 400 in three sizes: 18px for marketing prose, 16px for cards and dense regions, 14px for nav and metadata, all at 1.5 line-height with `text-wrap: pretty`.

Label is the one role that flips families. Twelve pixel JetBrains Mono at weight 600, uppercase, `0.06em` tracking — used inside `SectionBreak` chrome, status badges, F-grid metadata, and ticker callouts. It is the only sustained uppercase use on the site. Mono prose at 14px appears in code blocks, integration tile labels, and inline numeric data; never in paragraph copy.

Three named rules govern type. The **One-Family Rule**: Alliance No.2 carries display and body; pairing it with a serif display, a humanist sans, or a script is prohibited. The **Token-Sized Type Rule**: every font-size in component code reads from a `--type-*` variable; hard-coded `px` or `rem` outside the token file is a regression. The **Uppercase Restraint Rule**: uppercase belongs to the Label role on JetBrains Mono. Alliance No.2 never goes uppercase — not for hero headlines, not for "FEATURES" eyebrows, not for body emphasis. Letterforms break at scale.

## Layout

The page lands on a 7-column F-grid. Horizontal section padding reads `--space-grid-padding` (68px desktop, scaling on narrower viewports), so content edges align with col 1 and col 7. Vertical content borders sit 40px inside the cap and render as 1px hairlines through the section chrome, bleeding past the inner content. Maximum content width is 1280px.

The spacing scale is a short, geometric progression: 4, 14, 20, 28, 40, 68, 112, 128px. Section vertical rhythm is 112px (`section-py`) for standard sections and 128px (`sectionbreak-py`) for divider rows. Cards pad to 32px internally. Buttons run 16px horizontal × 8px vertical regardless of size — sizes scale label size, not padding rhythm. The navbar is fixed at 56px tall; the announcement bar adds 40px when present.

Press `F` in dev to overlay the F-grid. The `SectionBreak` component's green tick is the col-1 anchor made visible in production — it is alignment proof, not decoration.

## Elevation & Depth

The system is flat by doctrine. Marketing surfaces do not lift, drop, or float. Depth is conveyed by chrome geometry — hairline borders, vertical content rules, F-grid cells, fills inside zones — and by a single grain pass: a fixed full-viewport SVG fractal-noise layer at `mix-blend-mode: soft-light`, scrolling with the document.

No `box-shadow` tokens exist for marketing chrome. The only shadow allowance is the product-mock dashboard family (`.v2-mock-*`), where a `0 1px 2px rgba(0,0,0,0.06)` lift signals "this is the actual app UI rendered as an illustration." That shadow never escapes those scoped classes.

Two named rules. The **Flat-By-Doctrine Rule**: no `box-shadow`, no `filter: drop-shadow`, no glassmorphism, no inner shadows on marketing surfaces. If you reach for shadow, you are solving the wrong problem — try a 1px border or a zone fill first. The **Grain-As-Atmosphere Rule**: the grain overlay is the only ambient texture. Do not stack a second noise layer, a vignette, or a gradient atmosphere on top.

## Motion

Motion is calibration, not decoration. The signature effects — crosshair lens hover, cipher-scramble button labels, scrolling grain, x-ray jitter, marquee ticker — are quiet, mechanical, and repeatable. They are the brand voice; a marketing surface with no motion is bland by default. The Infisical personality is crisp and instrument-like, never playful, never bouncy. Tune all timing to that mood.

**Should it animate at all?** Before adding motion, count how often the user will see it. Animations on keyboard-initiated actions and anything triggered 100+ times a day are banned — they make the interface feel slow at the exact moment the user expects an instant response. Tens-of-times-a-day interactions (nav hover, list focus) get reduced or no motion. Occasional events (modals, drawers, toasts, section reveals) get standard motion. Rare or first-time events (onboarding, marketing reveals, the crosshair lens) can carry the most delight. Every animation must answer a single question — spatial consistency, state indication, feedback, explanation, or preventing a jarring change. "It looks cool" on a frequently-seen element is a regression.

**Easing.** The standard CSS keywords are too weak; the system ships strong custom curves and components read them from tokens. Elements entering or exiting the viewport — dropdowns, modal panels, popovers, button color transitions, toast slides — use `--ease-out` (`cubic-bezier(0.23, 1, 0.32, 1)`). Elements already on screen that move or morph use `--ease-in-out` (`cubic-bezier(0.77, 0, 0.175, 1)`). Drawer-style sheets with momentum read `--ease-drawer` (`cubic-bezier(0.32, 0.72, 0, 1)`). Hover color changes and ambient transitions use the gentle default `--ease` (`cubic-bezier(0.25, 0.1, 0.25, 1)`). Linear is reserved for constant-motion effects only — the logo marquee, the cipher idle re-fire interval, hold-to-confirm progress fills. `ease-in` is banned on UI: it delays the moment the user is watching most closely. Spring physics with visible bounce are banned in chrome; the cipher scramble is the playfulness allowance.

**Duration.** UI motion stays under 300ms — full stop. Button-press feedback runs at `--dur-press` (120ms). Micro-interactions, tooltips, and small popovers run at `--dur-fast` (160ms). Dropdowns, selects, nav state, and standard reveals run at `--dur-base` (200ms). Modals, drawers, and the slowest staggered entrances cap at `--dur-slow` (280ms). Marketing reveals (crosshair lens, blur reveal, scrolling lens jitter) may run longer because they fire rarely. When an animation needs longer than its tier, it usually needs less — shorter duration, smaller transform, fewer animated properties.

**Physicality.** Nothing in the real world appears from nothing. Entering elements start at `transform: scale(0.95)` with `opacity: 0`, never `scale(0)`. Buttons take `transform: scale(0.97)` on `:active` for tactile feedback, with `transition: transform 160ms var(--ease-out)`. Popovers, dropdowns, and tooltips set `transform-origin` to their trigger location (`var(--radix-popover-content-transform-origin)` with Radix, `var(--transform-origin)` with Base UI), so they scale out from where the user clicked. Modals are the exception — they appear centered in the viewport and keep `transform-origin: center`. Tooltips delay before opening to prevent accidental triggers, but once one is open, adjacent tooltips on the same toolbar open instantly with no animation; the toolbar feels twice as fast for free.

**Asymmetric timing.** Slow where the user is deciding, fast where the system responds. Hold-to-confirm fills over 2s linear on press, snap back at 200ms `ease-out` on release. Drag-to-dismiss damps as the gesture passes its natural boundary, dismisses on velocity (`Math.abs(distance) / elapsed > 0.11`) so a flick is enough without crossing a hard threshold. Toast exits run ~20% faster than entrances. Symmetric timing on a press-and-release interaction is a regression.

**Interruptibility.** Anything triggered rapidly — toasts being stacked, toggles, drags, gestures — uses CSS transitions or springs, not `@keyframes`. Transitions retarget from the current value mid-flight; keyframes restart from zero and look broken when interrupted. For entry animations without JavaScript, prefer `@starting-style`:

```css
.toast {
  opacity: 1;
  transform: translateY(0);
  transition: opacity 200ms var(--ease-out), transform 200ms var(--ease-out);
  @starting-style {
    opacity: 0;
    transform: translateY(100%);
  }
}
```

Fall back to the `useEffect(() => setMounted(true), [])` + `data-mounted` attribute pattern where browser support is uncertain. For programmatic CSS animations (clip-path reveals, lens jitter), prefer the Web Animations API over Framer Motion — it gives JS control with CSS-level GPU performance.

**Performance.** Animate `transform`, `opacity`, `filter`, and `clip-path` only. Animating `width`, `height`, `margin`, `padding`, `top`, or `left` triggers layout and paint and is a regression. Cap `blur()` at 8px for Safari. Use `transition` with explicit properties, never `transition: all` — it animates unintended properties off the GPU. Framer Motion shorthand props (`x`, `y`, `scale`) are *not* hardware-accelerated; they run on `requestAnimationFrame` on the main thread and drop frames while the page is loading or scripting. Use the full `transform` string for any motion that may run under load:

```jsx
<motion.div animate={{ transform: "translateX(100px)" }} />
```

Never drive a child's transform by setting a CSS variable on its parent — variable updates recalc styles on every descendant, producing a recalc storm. Set the transform directly on the moving element.

**Stagger.** When multiple elements enter together (card grids, marquee batches, list reveals), stagger by 30–80ms per item — `--stagger-step` defaults to 50ms. Long delays make the interface feel slow; stagger is decorative and never blocks interaction.

**Crossfade rescue.** When two states crossfading look like two distinct objects overlapping (icon swaps, content-swap buttons), add `filter: blur(2px)` during the transition. Blur bridges the visual gap so the eye reads a single transformation instead of a swap. Combine with `scale(0.97)` on press for a polished button state change. Keep blur under 8px.

**Reduced motion and hover gating.** Every transform-based animation honors `prefers-reduced-motion`. Reduced motion means *gentler*, not zero — keep opacity and color transitions that aid comprehension, drop position and scale changes. The reduced-motion media query zeros transform-based durations centrally; React-state-driven motion reads `useReducedMotion()` from framer-motion. Touch-device hover false-positives are blocked with `@media (hover: hover) and (pointer: fine)` around every `:hover` motion rule. Paired elements — modal and overlay, drawer and backdrop, tooltip and arrow — share easing and duration so they read as one unit.

**Reviewing motion.** Before shipping, slow the animation to 2–5x duration in DevTools and watch for: two distinct states overlapping during a crossfade, easing that starts or stops abruptly, transform-origin landing at the wrong corner, coordinated properties going out of sync. Step through frame-by-frame in Chrome DevTools' Animations panel for any motion that feels off but passes the eye at full speed. Re-watch the next morning — imperfections invisible during development surface with fresh eyes.

## Shapes

Border-radius is `0` on every marketing component. Buttons, cards, inputs, modals, navbar, banners, popovers — sharp corners are the contract. The visual system commits to right angles; rounded corners belong to in-code product mockups, where `--rounded-mock: 4px` signals "this is the product UI, not the marketing site."

Border-width is `1px` everywhere — vertical content borders, horizontal section rules, F-grid lines, card outlines, input edges. Sub-pixel widths render inconsistently between `border:` shorthand and background-color divs, so the system holds the line at 1px. Change the token, change the entire grid.

## Components

The system composes from a small set of chrome primitives — section container, vertical borders, bleed rule, fill patterns, inner max-width — plus a handful of content components: button, navbar, card, input, section header, crosshair lens, cipher text, blur reveal.

The **button** is sharp-cornered, 1px-bordered, and runs in three variants. *Primary* fills with Void (`#000000`) and labels white on light surfaces (`#e4e4e7` on dark); hover triggers a pixel-dither fill that lays an 8px Volt cell grid in random order across the button while the label flips to Void — the single color event the chrome allows. *Secondary* runs transparent with a Border Soft outline and Text Muted label; hover darkens border and label to Void. *Ghost* is a plain text-link variant with optional arrow icon; hover dims to muted. Sizes are sm (12px label), md (14px, default), lg (16px). All variants share `border-radius: 0` and a press affordance of `transform: scale(0.97)` on `:active` over `--dur-press` (120ms) with `--ease-out`, plus a `motion-reduce:transform-none` fallback. Color transitions run at `--dur-fast` (160ms) with explicit properties — never `transition: all`. An optional cipher-scramble decoration (22ms stagger, 90ms reveal-per-char, 38ms glyph-swap) fires on hover and focus, with the focus affordance being the motion itself plus the default browser ring.

**Cards** carry a 1px Border Soft outline (Border Dark on shade), 32px internal padding, and no rounding. Hover is quiet — border color shifts toward Void; no lift, no scale, no glow. Cards stack inside a section's grid separated by F-grid hairlines, never a `gap` value, so card boundaries and layout chrome are the same line.

**Inputs** run transparent with a 1px Border Soft outline, sharp corners, 12px padding, and Alliance No.2 body-sm text. Focus shifts the border to Void with `outline: none`; no shadow, no glow, no ring. On dark surfaces, inputs drop to a bottom border only — `border-bottom: 1px solid #2a2a2a`, brightening to `#e4e4e7` on focus — keeping the chrome quiet against shade.

The **navbar** is fixed at 56px, Bg White (Shade in dark contexts), z-indexed above the grain overlay. Gutters carry a tight 16px dashed-grid fill so the navbar reads in the same texture vocabulary as section gutters at a denser cadence. Links are 14px Alliance No.2, muted by default, shifting to Void on hover and focus — no underlines, no chevrons on top-level items. The mobile menu is an opacity-only transition at 200ms ease-out: no translate, no slide, no scale. Reduced motion makes the fade instant.

The **section container** is the lynchpin. Declarative props (`topRule`, `bottomRule`, `innerRules`, `borders`, `fills`, `splitAt`, `theme`) control the chrome layer; the inner max-width box holds content. The `theme="dark"` variant flips bg, border, text, and text-muted tokens at the section root so descendants flip automatically. Fills paint `grid`, `noise`, `tint`, or `gradient` patterns inside named zones (`left`, `middle`, `right`, with `top-*` / `bottom-*` when split). The default grid is a 1px dashed line at 64px cells.

Signature components carry the brand voice: the **crosshair lens** reveals an underlying x-ray image inside a movable box with steps()-driven jitter; **cipher text** scrambles glyphs on hover and focus with reduced-motion honored; **blur reveal** enhances an already-visible default so content ships even if the transition never fires; **page borders** draw continuous vertical rules across stacked sections so the inner content edge reads as one rule from hero to footer; the **section break** divider labels its row in JetBrains Mono and anchors the col-1 F-grid tick.

**Popovers, dropdowns, and tooltips** scale in from their trigger, not the viewport center. Set `transform-origin: var(--radix-popover-content-transform-origin)` (Radix) or `var(--transform-origin)` (Base UI) so the element grows from the corner the user just clicked. Entrance is `scale(0.95)` + `opacity: 0` → `scale(1)` + `opacity: 1` at `--dur-fast` (160ms) with `--ease-out`; never `scale(0)`. Modals are the exception — they stay centered and keep `transform-origin: center` because they aren't anchored to a trigger. Tooltips delay before the first open; on a toolbar of related tooltips, the second and subsequent ones open instantly (`transition-duration: 0ms`) to make the whole row feel snappy.

## Voice & Content

Sentence case everywhere — UI labels, headings, body. No title case kickers. No exclamation marks. No hype copy ("supercharge," "blazing fast," "next-gen," "revolutionize"). No FUD ("don't be the next breach," "before it's too late"). The writing is precise, technical, and confident in the same register as the chrome: a thing built by engineers, for engineers.

Numbers read as numerals. Code, keys, paths, and identifiers run in JetBrains Mono. Inline emphasis comes from weight or the Volt highlight chip — never italics, never underlines, never gradient text. CTAs are imperative and short: "Start," "Talk to sales," "Read the docs." Body links are Void underlined; Volt is not a link color.

## Do's and Don'ts

**Do** read every value from the token file. Colors via `--color-*`, type via `--type-*`, spacing via `--space-*`, motion via `--ease-*` and `--dur-*`. One edit propagates everywhere.

**Do** commit to motion. Crosshair lens, cipher scramble, scrolling grain, marquee, x-ray jitter — they are the brand voice, not decoration.

**Do** keep border-width at 1px and border-radius at 0 across marketing chrome. Sub-pixel and rounded corners break the contract.

**Do** ensure body text contrast hits ≥4.5:1 against its surface. Void on Bg White passes; the muted `rgba(38,38,38,0.32)` variant is metadata only.

**Do** include `motion-reduce` fallbacks on every transform-based animation, and use `useReducedMotion()` for React-state-driven motion.

**Do** pair section chrome from the core primitives. Local copies in section files are a violation; import from the shared core.

**Don't** ship the generic SaaS template. No hero metric strip, no identical icon-and-text card grids, no tracked-uppercase eyebrows above every section, no numbered section scaffolding.

**Don't** ship the enterprise security vendor. No navy and gold, no stock shield or padlock imagery, no fingerprint icons, no fear copy. Volt and Void carry the brand.

**Don't** ship the overly playful startup. No rainbow gradients across hero text. No bouncy spring physics. No cartoon illustrations. No exclamation marks.

**Don't** ship the minimalist-bland. All-white plus thin sans plus no accent plus no motion equals no brand. Commit to Volt, grain, F-grid chrome, and motion.

**Don't** add `border-radius` to marketing components. **Don't** add `box-shadow` to marketing surfaces. **Don't** use `background-clip: text` with a gradient. **Don't** use Volt as a text color on white. **Don't** introduce a third typeface family. **Don't** animate layout properties — transform and opacity only. **Don't** hard-code font-size, color, padding, or motion values; if the token doesn't exist, add it to the token file first. **Don't** gate content visibility on a class-triggered transition. **Don't** number sections (01 / 02 / 03) unless the section IS an ordered sequence.

**Don't** animate keyboard-initiated actions or anything the user triggers 100+ times a day — animation makes the interface feel slower at the exact moment the user expects an instant response. **Don't** use `transition: all` — specify properties. **Don't** start an entrance at `transform: scale(0)` — start at `scale(0.95)` with opacity. **Don't** use `ease-in` on any UI animation; it delays the moment the user is watching most. **Don't** set `transform-origin: center` on a trigger-anchored popover, dropdown, or tooltip (modals are exempt). **Don't** use `@keyframes` for anything that can be triggered rapidly (toasts, toggles, drags) — keyframes restart from zero on interruption; transitions retarget mid-flight. **Don't** use Framer Motion shorthand props (`x`, `y`, `scale`) for motion that runs while the page is loading or scripting — use the full `transform` string. **Don't** drive a child's transform by mutating a CSS variable on the parent — variable changes recalc styles on every descendant.

---
name: Ice Pop Perú
description: Landing comercial y de franquicias para una cadena peruana de helado soft con 9 sabores exclusivos
colors:
  fresa: "#E45490"
  fresa-deep: "#AB3F6C"
  fresa-light: "#F8D4E3"
  cielo: "#00A8CC"
  cielo-deep: "#007E99"
  cielo-light: "#BFE9F2"
  mango: "#FFC53D"
  mango-deep: "#F2A400"
  mango-light: "#FFEFC7"
  tinta: "#211334"
  crema: "#FFFBF6"
typography:
  display:
    fontFamily: "Baloo 2, sans-serif"
    fontSize: "clamp(2.25rem, 5vw, 4.5rem)"
    fontWeight: 600
    lineHeight: 0.98
    letterSpacing: "normal"
  body:
    fontFamily: "Outfit, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "normal"
rounded:
  sm: "1rem"
  md: "1.5rem"
  lg: "2.25rem"
  xl: "3rem"
  full: "9999px"
spacing:
  sm: "1rem"
  md: "1.75rem"
  lg: "3rem"
  xl: "6rem"
components:
  button-primary:
    backgroundColor: "{colors.fresa}"
    textColor: "{colors.crema}"
    rounded: "{rounded.full}"
    padding: "16px 28px"
  button-primary-hover:
    backgroundColor: "{colors.tinta}"
  button-on-color:
    backgroundColor: "{colors.crema}"
    textColor: "{colors.fresa}"
    rounded: "{rounded.full}"
    padding: "16px 28px"
  card-flavor:
    backgroundColor: "{colors.fresa}"
    textColor: "{colors.crema}"
    rounded: "{rounded.lg}"
    padding: "28px"
---

# Design System: Ice Pop Perú

## Overview

**Creative North Star: "The Swirl Bento"**

The palette and wordmark are grounded in the client's real logo (`assets/logo.png`, a turquoise-and-magenta badge with a bubble-lettered "ice pop" and a script "flavors"), sampled pixel-for-pixel rather than approximated — the two brand hues below are the exact extracted values, not a designer's guess at "playful ice cream colors." The system treats the soft-serve swirl as the one recurring form — an authored SVG silhouette, never a stock photo — repeated at every scale from a 24px social-grid glyph to a 260px hero cone. Flat, saturated color fields sit on a warm cream ground rather than a neutral gray canvas, and every container commits to a heavy, continuous corner radius so nothing on the page reads as a sharp-edged software UI. The bento grid in the flavors section — mismatched card sizes instead of a uniform icon-grid — is the system's structural signature, carried into the comparison strip and the social mosaic.

The build explicitly rejected the generic ice-cream-shop template: no stock photography of cones, no uniform three-icon feature grid as the page's backbone, no small-caps kicker labels floating above headlines (a hard refusal, not a style choice). Color and shape do the persuading; text stays direct.

**Key Characteristics:**
- Flat saturated color fields at page/section scale, never gradients
- One repeating hand-drawn swirl silhouette as the entire iconography system
- Heavy, continuous rounding (24–48px) on every container
- Bento-style size variation instead of uniform card grids
- Baloo 2 display type (echoing the logo's bubble lettering) + Pacifico script accent, paired with Outfit body type

## Colors

Two saturated brand hues, pixel-sampled from the real logo, rotate as section backgrounds and accents, grounded by a warm cream base and a deep plum-black for text and dark sections. Mango is a supporting flavor-illustration color only — it does not appear in the logo and never owns a full section.

### Primary
- **Fresa** (#E45490): The brand's loudest color — hero background, primary CTAs, the highest-priority flavor card. Sampled directly from the logo's "pop"/"flavors" lettering. Used at full field scale, not as a small accent.

### Secondary
- **Cielo** (#00A8CC): Second-most-used field color — sampled directly from the logo's badge background. Alternate section backgrounds (franchise section, secondary flavor cards), the "Ice Pop" side of the tradicional-vs-Ice-Pop comparison.

### Tertiary
- **Mango** (#FFC53D): Flavor-illustration accent only (mango, lúcuma cards; minor decorative tiles) — not part of the logo's own palette, so it never fills a full section the way fresa/cielo do.

### Neutral
- **Tinta** (#211334): Primary text color and the dark section background (Experiencia, footer). A deep plum-black, never pure black.
- **Crema** (#FFFBF6): Page background and text-on-dark color. Warm off-white, never pure white.

### Named Rules
**The Field, Not Accent Rule.** Brand colors always own a whole section or card background. They never appear as a thin accent stripe, icon tint, or gradient — a color either commits to a region or stays out of it.

**The Deep-For-Text Rule.** The logo-sampled base `fresa` (#E45490) measures only 3.4:1 against both crema and tinta — enough for large bold display type, not enough for body copy, tags, or button labels. Any surface that carries that smaller text (hero, the lead flavor card, the comparison strip's Ice Pop panel, the franchise form's submit button) uses `fresa-deep` (#AB3F6C, 5.6:1 against crema) instead. Base `fresa` stays reserved for small accents, borders, badges, and large-bold headline moments where 3:1 is enough. This was caught and fixed during finishing — an early draft shipped base `fresa` under body text and failed contrast.

## Typography

**Display Font:** Baloo 2, weights 500–800 (with system sans-serif fallback)
**Script Accent Font:** Pacifico (used sparingly — currently only the "Perú" wordmark accent in header/footer, echoing the logo's own cursive "flavors" line)
**Body Font:** Outfit (with system sans-serif fallback)

**Character:** Baloo 2 was chosen specifically to resonate with the logo's chunky bubble-lettered "ice pop" — a closer match than a generic rounded sans. Pacifico echoes the logo's own script "flavors" line and is reserved for that single accent role, never body or long headlines. Outfit keeps body copy legible and neutral so long paragraphs (franchise pitch, flavor descriptions) don't compete with headline weight.

### Hierarchy
- **Display** (600, clamp(2.25rem–4.5rem), 0.98 line-height): Section and hero headlines only.
- **Title** (600, 1.25–1.875rem): Card titles (flavor names, location names, form heading).
- **Body** (400–500, 1rem–1.125rem, 1.6 line-height): Paragraph copy, nav links, form labels.
- **Label** (600, 0.75rem): Badge pills, topping tags, footer link headings.

### Named Rules
**No Kicker Rule.** No small-caps or tracked label sits above a headline to "introduce" it. The headline carries its own weight; supporting context moves into the paragraph beneath it or is cut.

## Layout

Single-column marketing page, `max-w-7xl` centered container with `px-5`/`px-8` gutters. Sections alternate background color (fresa hero → crema → tinta → crema → cielo/crema split → cielo-tinted) so scroll position is always legible from color alone. Vertical rhythm is generous: `py-24` to `py-32` between sections, more space above a heading than below it. The flavors section breaks the single-column rule with a `grid-cols-2 md:grid-cols-4` bento grid using `col-span-2`/`row-span-2` on two cards to create size variation. The franchise section is the only 50/50 split layout, separating the investor pitch (left, colored) from the lead form (right, on cream).

## Elevation & Depth

Mostly flat — section-to-section depth comes from color contrast, not shadows. Cards and CTAs use soft, blurred shadows (offset + blur, never a hard 0-blur block) as the only elevation device, reserved for interactive elements the user should feel are "liftable."

### Shadow Vocabulary
- **cta-rest** (`box-shadow: 0 8px 24px rgba(33,19,52,0.28)`): Primary hero CTA at rest.
- **cta-hover** (`box-shadow: 0 14px 32px rgba(33,19,52,0.32)`, with `-translate-y-1`): Primary CTA on hover — deepens and lifts rather than flattening.

### Named Rules
**The Soft-Only Rule.** Every shadow in the system carries blur. A hard-edged, zero-blur offset shadow is a different (neobrutalist) visual world this project didn't choose, and it doesn't appear here even locally.

## Shapes

Corner radius is heavy and continuous everywhere: `rounded-2xl`–`rounded-[3rem]` on cards and images, `rounded-full` on every button, pill badge, and nav CTA. No sharp corners appear anywhere in the built surface, including form inputs and social-grid tiles. The swirl silhouette itself — five overlapping circles of decreasing radius, stacked and fused via SVG nonzero fill-rule into one continuous mass, tapering to a small rounded peak — is the system's one custom shape and is reused, recolored, and rescaled rather than redrawn. It was deliberately built from precise circle geometry (not a hand-drawn curve) after an early single-blob draft read as ambiguous rather than recognizably "soft-serve"; the stacked-scoop silhouette is what actually reads as ice cream at both hero and 24px icon scale. A flat waffle-cone triangle (`#E3A857`, always this one tan, never recolored per flavor) sits under every instance of the swirl — an earlier draft omitted the cone entirely and read as an unanchored dollop rather than an ice cream.

## Components

### Buttons
- **Shape:** Fully rounded (`rounded-full`).
- **Primary (on fresa/dark fields):** Cream background, fresa text, soft lifted shadow on hover.
- **Primary (on cream fields):** Fresa or tinta background, cream text.
- **Ghost/Secondary:** 2px border in current section's text color, fills solid on hover.

### Cards (flavor / feature)
- **Corner Style:** `rounded-[2.25rem]` (the `4xl` token).
- **Background:** One full brand-color field per card (fresa, mango, tinta, cielo), or a tinted 10–15% wash with a matching 2px border for the smaller bento cells.
- **Shadow Strategy:** None at rest; cards signal interactivity through the swirl icon's hover lift (`translate-y + rotate + scale`), not through elevation change.
- **Internal Padding:** 24–36px depending on card size.

### Inputs / Fields (franchise form)
- **Style:** 2px `tinta/10` border, `rounded-2xl`, white fill, generous padding.
- **Focus:** Border shifts to fresa; no glow/ring.

### Navigation
- **Style:** Fixed, translucent cream with backdrop blur; text-only links in `tinta/80`, hover to fresa; primary CTA stays a solid pill button on the right.

### Signature Component: Swirl Icon
A single authored SVG path (five fused circles forming a stacked soft-serve silhouette, no stock imagery) reused at every scale as the flavor system's entire iconography — recolored per flavor, floated with a slow idle animation in the hero, and lifted on hover inside cards.

### Logo Mark
The real client logo (`assets/logo.png`, a circular turquoise badge) renders at `w-11 h-11`/`w-9 h-9` `rounded-full` in the header and footer, paired with the "Ice Pop" (Baloo 2) + "Perú" (Pacifico script) wordmark — never redrawn or approximated as SVG.

### Background Video
Two sections carry real looping video (muted/autoplay/playsinline, `object-cover`) instead of illustration: the hero (`assets/hero-video.mp4`, a soft-serve cone being made) and La Experiencia (`assets/experiencia-video.mp4`, toppings flying onto a cone in motion — chosen specifically because it dramatizes "se ve, se siente y se comparte" rather than just filling space). Each uses a different scrim strategy suited to its content width: the hero's headline and CTAs sit only in the left column, so it uses a directional `bg-gradient-to-r from-fresa-deep/95 via-fresa-deep/75 to-fresa-deep/40`; La Experiencia's heading and cards span the full width, so it uses a flat `bg-tinta/80` section scrim plus `bg-tinta/70` on the three feature cards (raised from an initial `/55` — a dynamic video's brightest frame, not its average frame, is what a contrast check must survive). Video is reserved for sections that can prove something real is happening; it does not spread to cards, footer, or static sections.

## Do's and Don'ts

### Do:
- **Do** let a brand color fill an entire section or card background rather than tinting an accent.
- **Do** reuse the swirl SVG for every ice-cream-related visual moment instead of introducing photography or a second icon style.
- **Do** keep shadows soft (offset + blur) and reserve them for genuinely interactive elements.
- **Do** vary card size in the flavor grid (bento) rather than defaulting to uniform tiles.

### Don't:
- **Don't** add a kicker/eyebrow label above any headline — this was removed everywhere it appeared during finishing and must not return.
- **Don't** use a hard-edged, zero-blur offset shadow anywhere in this system — it was caught and corrected during finishing.
- **Don't** stand in a Unicode glyph or emoji for an icon (e.g. "✓", "#") — draw it as SVG in the swirl/heart/check vocabulary already established.
- **Don't** invent real addresses, franchise financials, or testimonials — the build ships explicit `[placeholder]` markers and a labeled illustrative social mosaic instead.
- **Don't** put body text, tags, or button labels directly on base `fresa` — it fails WCAG contrast at that scale. Use `fresa-deep`.

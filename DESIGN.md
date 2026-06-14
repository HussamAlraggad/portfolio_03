# Design

## Theme

Dark-first. The surface is a deep near-black; content glows against it. Light mode available as a user preference.

**Scene:** A hiring manager opens the portfolio late evening, dim ambient light, looking for signals of taste and ability. The dark backdrop focuses attention on the work itself — projects, code, writing — and the violet primary reads as confident and considered, not decorative.

## Color Strategy

Committed — one saturated brand color (violet) carries the identity as primary. A warm amber accent provides the sharp-warm tension. Surfaces stay neutral; the brand lives in primary + accent, not in the bg.

## Color Palette

### Dark Mode (default)

| Role | OKLCH | Usage |
|---|---|---|
| `--bg` | `oklch(0.08 0 0)` | Page background |
| `--surface` | `oklch(0.12 0.004 294)` | Cards, panels, section backgrounds |
| `--primary` | `oklch(0.62 0.18 294)` | Brand color: buttons, links, highlights |
| `--accent` | `oklch(0.70 0.14 70)` | Second brand color: badges, accent rules, small fills |
| `--ink` | `oklch(0.93 0.003 294)` | Body text |
| `--muted` | `oklch(0.50 0.006 294)` | Secondary text, metadata |

### Light Mode (optional, via prefers-color-scheme)

| Role | OKLCH | Usage |
|---|---|---|
| `--bg` | `oklch(1 0 0)` | Page background |
| `--surface` | `oklch(0.97 0.003 294)` | Cards, panels, section backgrounds |
| `--primary` | `oklch(0.45 0.18 294)` | Brand color: buttons, links, highlights |
| `--accent` | `oklch(0.55 0.14 70)` | Second brand color: badges, accent rules |
| `--ink` | `oklch(0.12 0 0)` | Body text |
| `--muted` | `oklch(0.45 0.003 294)` | Secondary text, metadata |

### Text on color fills

White text (`var(--bg)` equivalent) on all saturated fills — primary buttons, accent badges, any element where text sits on a mid-luminance saturated background. Never dark text on a colored fill.

## Typography

- **Headings:** A sharp geometric sans with character (e.g. Instrument Sans, Plus Jakarta Sans, Satoshi) — confident, precise, with weight contrast.
- **Body:** A neutral, highly readable sans (e.g. Inter, IBM Plex Sans) — warm through letterfit and spacing, not through decoration.
- **Monospace** (for code): JetBrains Mono or similar — technical credibility when showing code snippets.
- **Scale:** `clamp()` for responsive headings. Display heading ceiling ≤ `clamp(2.5rem, 5vw, 5rem)`. Body line length capped at 65–75ch.
- **Treatment:** `text-wrap: balance` on h1–h3, `text-wrap: pretty` on body prose. Display heading letter-spacing ≥ -0.02em.

## Motion

- Intentional, restrained. Ease-out exponential curves (quart/quint). No bounce or elastic.
- Scroll-driven reveals using `opacity` + `translateY` with staggered children. Non-layout properties only.
- `clip-path` reveals for hero or section entries when it materially improves the effect.
- Every animation paired with `@media (prefers-reduced-motion: reduce)` → instant or crossfade.
- Content must be fully visible at rest without JS execution — never gate visibility on class-triggered reveals (prevents blank sections in headless renderers or hidden tabs).

## Components & Layout

- **Hero:** Minimal — name, role, one sharp line of positioning copy. Optional subtle visual (glow, grid, or noise texture) in the violet family. No hero-metric template (big number, small label).
- **Project showcase:** Flexible cards that accommodate mixed content types (web apps, AI/ML, design case studies). Prioritize the visual and the outcome over tech-stack lists.
- **Navigation:** Sticky top bar with section links. Name/logo on the left, links on the right. A dark/light toggle. Clean, not crowded.
- **Spacing:** Generous vertical rhythm. 4–8rem section padding. Varied, not uniform.
- **Z-index scale:** `1` dropdown → `10` sticky → `20` modal-backdrop → `30` modal → `40` toast → `50` tooltip.

## Anti-patterns (internal bans)

- Gradient text (`background-clip: text` + gradient)
- Glassmorphism as default
- Side-stripe borders (colored `border-left`/`border-right` >1px)
- Numbered section markers (`01 / 02 / 03` above every heading)
- Tiny uppercase tracked eyebrows above every section
- Cards without content hierarchy (icon + heading + text, repeated)
- Nested cards

## Accessibility

- WCAG AA minimum across all surfaces
- `prefers-reduced-motion` respected globally
- Visible `:focus-visible` outlines styled to match brand (2px primary offset 2px)
- Semantic HTML: `nav`, `main`, `section`, `article`, headings in order
- Skip-to-content link as first focusable element
- All interactive elements keyboard-operable

## Assets

- No external brand assets identified yet. The site itself is the brand expression.

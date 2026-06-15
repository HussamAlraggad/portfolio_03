# Hussam Alraggad — Portfolio

Personal portfolio showcasing AI-assisted software engineering mastery. Built with **Astro**, designed with **OKLCH** tokens, dark-first with light mode support.

## Stack

- **Framework:** [Astro](https://astro.build) v5
- **Fonts:** Sora (display) · Figtree (body) · Fira Code (mono)
- **Color:** OKLCH — violet primary (`oklch(0.62 0.18 294)`) + amber accent (`oklch(0.70 0.14 70)`)
- **Icons:** Inline SVG
- **Animations:** CSS-only reveal on scroll via IntersectionObserver

## Sections

| Section | Component | Content |
|---|---|---|
| Hero | `Hero.astro` | Name, role, tagline, ambient glow |
| Projects | `Projects.astro` | 8 open-source repos with descriptions |
| About | `About.astro` | Background, philosophy (the four questions) |
| Achievements | `Achievements.astro` | Awards, honors, certifications (reverse chron) |
| Contact | `Contact.astro` | Email, GitHub, LinkedIn |
| Footer | `Footer.astro` | Copyright |

## Design System

Design tokens live in `src/styles/global.css` as CSS custom properties:

- `--bg` / `--surface` — backgrounds
- `--primary` / `--accent` — brand colors
- `--ink` / `--muted` / `--ink-subtle` — text
- `--border-subtle` / `--tag-bg` / `--nav-bg` — derived

Light mode is served via `@media (prefers-color-scheme: light)`.

## Live Mode

```bash
pnpm run dev          # Start dev server on :4321
/impeccable live       # Boot visual variant mode
```

Pre-configured at `.impeccable/live/config.json`.

## Development

```bash
pnpm install
pnpm run dev      # Dev server with HMR
pnpm run build    # Static export to dist/
pnpm run preview  # Preview production build
```

## License

MIT

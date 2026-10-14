# DESIGN.md · Sandi Nurpeissova portfolio

The visual system for `index.html`. It draws on Apple's DESIGN.md from getdesign.md (full-bleed imagery, generous white space, alternating light and dark tiles), Emil Kowalski's motion rules, and the impeccable.style anti-pattern list.

## Product

A portfolio and CV for a Senior BIM Coordinator. The audience is hiring architects, BIM managers and recruiters. They should see the projects first, understand the role on each in under a minute, and be able to get the CV as a PDF or printout.

## Color

| Token | Light | Dark | Use |
|---|---|---|---|
| `--canvas` | `#ffffff` | `#0f0f10` | Page |
| `--tile` | `#f5f5f7` | `#1c1c1e` | Alternate sections |
| `--ink` | `#1d1d1f` | `#f5f5f7` | Text |
| `--muted` | `#5f5f64` | `#a1a1a6` | Secondary text (4.5:1 or better) |
| `--line` | `#e2e2e5` | `#2c2c2e` | Hairlines |
| `--accent` | `#2c5e4f` | `#7fc0a8` | Links, active states, one primary button |
| `--night` | `#111112` | `#000000` | Dark feature tiles (thesis, contact) |

The green comes from the PDF portfolio. No gradients, glows, beige or glass effects.

## Type

* Display: **Archivo** 500/600, tracking -0.02em, line height 1.05.
* Body: **IBM Plex Sans** 400/500, 17px, line height 1.55, measure 64ch max.
* Data and metadata (project numbers, tools, dates): **IBM Plex Mono** 400, 13px.
* Scale: 13 / 15 / 17 / 21 / 28 / 40 / clamp(44px, 7vw, 96px).

## Space and shape

* 8px base: 4, 8, 12, 16, 24, 32, 48, 80, 128.
* Radii: 0 for full-bleed imagery, 10px for cards and sheets, 999px for buttons.
* Hairlines replace shadows. The only shadow is on the open project sheet.
* Content width 1240px, text 64ch.

## Motion

* `--ease-out: cubic-bezier(.23,1,.32,1)` for enter and exit. `--ease-in-out: cubic-bezier(.77,0,.175,1)` for on-screen movement.
* Press: `scale(.97)` over 160ms. Hover effects only under `(hover: hover) and (pointer: fine)`.
* Sheets open in 320ms and close in 200ms. Filters and tabs take 200ms.
* Scroll reveals run once: text fades up 8px, images reveal with `clip-path: inset(0 0 100% 0)` to `inset(0)`.
* Only `transform`, `opacity` and `clip-path` are animated. `prefers-reduced-motion` keeps fades and removes movement.
* Content stays visible if JavaScript does not run.

## Avoid

Eyebrow labels and badges above headings, numbered section labels, hero metric rows, identical card grids, nested cards, images that zoom on hover, bounce easing, pulsing dots, gradient text, em-dash-heavy copy.

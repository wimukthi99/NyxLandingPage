# NYX - Design System

This document outlines the visual operating system for the NYX platform, designed as the source of truth for all future prompts.

## 1. Typography

NYX employs a strict two-family system that scales continuously using CSS `clamp`. 
Fonts are optimized and served locally (or via `@fontsource`) to prevent rendering delays.

- **Functional Sans:** `Montserrat` (400, 500, 600, 700, 800)
- **Editorial Serif:** `Playfair Display` (400, 600)

**Fluid Typography Scale:**
- `--text-display`: clamp(3rem, 7vw, 6rem)
- `--text-hero`: clamp(2.75rem, 6vw, 5.5rem)
- `--text-h1`: clamp(2.25rem, 4.5vw, 4rem)
- `--text-h2`: clamp(1.75rem, 3vw, 2.5rem)
- `--text-h3`: clamp(1.35rem, 2vw, 1.75rem)
- `--text-body-lg`: clamp(1.0625rem, 1.2vw, 1.25rem)
- `--text-body`: clamp(1rem, 1.1vw, 1.125rem)
- `--text-small`: 0.875rem
- `--text-caption`: 0.8125rem
- `--text-micro`: 0.6875rem

## 2. Colors

The NYX palette is highly restrained, emphasizing product imagery through contrast.

- **Primary:** White (`#FFFFFF`) / Black (`#0A0A0A`)
- **Neutrals:** Grey 50 (`#FAFAFA`) to Grey 900 (`#141414`)
- **Accent:** Oxblood (`#6E1423`) - Used strictly for focus indicators, selection states, and limited emphasis.

## 3. Spacing (Base 8px)

A mathematical rhythm governs the spacing:
`8px, 16px, 24px, 32px, 40px, 48px, 56px, 64px, 72px, 80px, 96px, 120px, 160px, 192px`

## 4. Grid and Containers

- **Grid:** 12-column (Desktop), 8-column (Tablet), 4-column (Mobile).
- **Containers:** 
  - `default`: Max-width 1280px (Main commerce constraints).
  - `large`: Max-width 1440px (Hero and editorial canvases).
  - `full`: Edge-to-edge media.

## 5. Breakpoints

- `xs/sm`: 480px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1440px
- `xxl`: 1920px
- `4k`: 2560px

## 6. Primitives

The system relies on reusable UI primitives located in `/src/components/ui`:
- **Button:** Variants (`primary`, `secondary`, `outline`, `text`, `icon`).
- **Heading:** Translates fluid scales (`display`, `h1`, `h2`, `h3`, `eyebrow`).
- **Text:** Standardizes paragraph styling (`body`, `body-large`, `caption`, `small`).
- **Container:** Standard width constraints.
- **Section:** Vertical rhythm constraints (`compact`, `standard`, `editorial`).
- **MediaFrame:** Consistent aspect ratios (`1:1`, `4:5`, `3:4`, `16:9`, `21:9`) and visual overlays.
- **Input:** 52px height standard inputs with consistent focus rings.

## 7. Motion

GSAP & CSS Transition timing tokens:
- `--motion-fast`: 200ms
- `--motion-standard`: 350ms
- `--motion-slow`: 600ms
- `--motion-editorial`: 900ms
- `--motion-cinematic`: 1200ms
- `--default-transition-timing-function`: cubic-bezier(0.22, 1, 0.36, 1)

## 8. Anti-Patterns

- **DO NOT** use rounded corners (`border-radius`) exceeding 4px on structural elements.
- **DO NOT** introduce neon colors, generic gradients, or glassmorphism.
- **DO NOT** create unique typography scales or arbitrary hex colors on a per-component basis. All properties must route through these system tokens.

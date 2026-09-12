# NYX - Design Decisions Log

This document records the architectural and design decisions made throughout the NYX platform's development.

## 1. Architectural Reset (Prompt 01)
- **Decision:** Remove all 3D/WebGL/Orb implementations.
- **Reason:** To align with a "DOM-first, premium fashion e-commerce architecture" emphasizing editorial presentation and performance.
- **Trade-off:** Loss of a highly interactive 3D hero experience, favoring commerce conversion and SEO stability.

## 2. Typography Constraints (Prompt 02)
- **Decision:** Strict two-family constraint using Montserrat (functional) and Playfair Display (editorial).
- **Reason:** To emulate luxury fashion editorial standards while keeping UI elements highly legible and scannable for commerce (Gymshark + Armani principles).
- **Trade-off:** Reduces font diversity but enforces a clean, predictable hierarchy and reduces payload size.

## 3. Color Tokens (Prompt 02)
- **Decision:** Monochromatic core (White to Black scale) with a single Oxblood (`#6E1423`) accent.
- **Reason:** To ensure the product imagery acts as the sole source of color and visual hero.
- **Trade-off:** UI looks stark if unpopulated; necessitates excellent photography and grid spacing.

## 4. Spacing & Grid (Prompt 02)
- **Decision:** Base-8 scale, peaking at 192px, using a 1280px primary container width.
- **Reason:** Provides generous editorial whitespace on desktop while maintaining a constrained reading line for usability.
- **Trade-off:** Full-bleed imagery requires explicit opt-out (`Container size="full"`) rather than being default.

## 5. Responsive Behavior (Prompt 02)
- **Decision:** Fluid typography via `clamp` logic paired with fixed-tier breakpoints (`xs` to `4k`).
- **Reason:** Minimizes "jumpy" layouts where typography changes drastically at specific widths, maintaining a continuous premium feel.
- **Trade-off:** Complex fine-tuning is required at the extremes (sub-375px and ultra-wide).

## 6. Component Primitives (Prompt 02)
- **Decision:** Create atomic layout and UI primitives (`Container`, `Section`, `Heading`, `Text`, `Button`, `Input`, `MediaFrame`) using `class-variance-authority`.
- **Reason:** Prevents arbitrary classes scattered throughout the codebase. The token system becomes the sole source of truth.
- **Trade-off:** Small upfront engineering cost to map variants; slight abstraction over plain Tailwind.

## 7. Motion & Choreography (Prompt 04)
- **Decision:** Consolidate animations into , , and  GSAP components.
- **Reason:** Prevents arbitrary and disconnected motion behavior across the app, ensuring all animations follow the 'NYX easing' and respect accessibility ().
- **Trade-off:** Additional abstraction layer for GSAP logic, but yields high consistency.

## 7. Motion & Choreography (Prompt 04)
- **Decision:** Consolidate animations into `Reveal`, `Parallax`, and `PageTransition` GSAP components.
- **Reason:** Prevents arbitrary and disconnected motion behavior across the app, ensuring all animations follow the 'NYX easing' and respect accessibility (`prefers-reduced-motion`).
- **Trade-off:** Additional abstraction layer for GSAP logic, but yields high consistency.

## 8. First Release & Contact Structure (Prompt 04)
- **Decision:** Editorial layout emphasizing large-scale imagery and quiet space, rather than dense e-commerce grids. Contact page uses robust client-side simulation.
- **Reason:** Treat the First Release as a brand campaign rather than a typical product listing, preparing users for future commerce.
- **Trade-off:** Conversion paths require users to scroll through editorial content rather than seeing immediate "Buy" buttons.

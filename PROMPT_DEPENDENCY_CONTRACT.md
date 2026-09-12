# NYX - Prompt Dependency Contract

This document outlines the strict five-prompt dependency graph. No later prompt may contradict, undo, or redefine a locked decision from an earlier prompt.

---

## PROMPT 01 — ARCHITECTURE RESET
**Status:** COMPLETE
**Establishes:**
- Route map (`/`, `/about`, `/what-we-do`, `/motivation`, `/first-release`, `/contact`)
- Required sections and information architecture
- Code boundaries and repository structure
- Total legacy removal (No 3D/WebGL)
- Media naming conventions (`MEDIA_MANIFEST.md`)
- Technical architecture and client/server boundaries

---

## PROMPT 02 — DESIGN SYSTEM
**Status:** PENDING
**Establishes:**
- Global typography (`Montserrat`, `Playfair Display`)
- Color tokens (Monochrome + `#6E1423` accent)
- Spacing rules (8px base, 120-160px desktop vertical rhythm)
- 12-column grid system
- Tokenized breakpoints (375 to 2560+)
- Primitives (Container, Section, Button, Heading, Text, MediaFrame)

**Dependency Rule:** Cannot change the route map, reintroduce 3D, remove required pages, or invent a new brand direction.

---

## PROMPT 03 — GLOBAL SHELL + CORE PAGES
**Status:** PENDING
**Establishes:**
- Brand Loader (1.6s - 2.2s N-Y-X reveal)
- Global Header & Navigation (Mega Menu, Desktop & Mobile)
- Footer
- Static core page structures (`/`, `/about`, `/what-we-do`, `/motivation`)
- Search overlay & Cart drawer interfaces

**Dependency Rule:** Cannot change design tokens, invent a new navigation model without justification, or remove required sections.

---

## PROMPT 04 — FIRST RELEASE + CONTACT + MOTION
**Status:** PENDING
**Establishes:**
- First Release page (with exactly three placeholders)
- Contact Us UX and form architecture
- Editorial interactions and page transitions
- Scroll motion and parallax (using GSAP securely)
- Responsive choreography across all breakpoints

**Dependency Rule:** Cannot change architecture, introduce WebGL, introduce unrelated design languages, or remove the three First Release placeholders.

---

## PROMPT 05 — PRODUCTION QA + SEO + ACCESSIBILITY + PERFORMANCE
**Status:** PENDING
**Establishes:**
- Final hardening and bug fixing
- Core Web Vitals optimization
- Full Accessibility implementation (WCAG 2.2 AA)
- Technical SEO (Metadata, Open Graph, structured data)
- Error handling and empty states
- Launch readiness

**Dependency Rule:** Cannot redesign the website, change visual direction, or replace information architecture. QA is strictly for hardening.

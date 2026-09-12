# NYX - Production Changelog

## 1. Metadata Hardening
- **Problem**: Default AI Studio metadata and page titles remained in `index.html` and `metadata.json`.
- **Change**: Updated `<title>`, `<meta name="description">`, and `og:*` tags in `index.html`. Updated `metadata.json` with the "NYX" branding.
- **Reason**: SEO indexability and correct browser tab presentation.
- **Files**: `index.html`, `metadata.json`
- **Risk**: Low (isolated text changes).

## 2. GSAP/Motion Solidification
- **Problem**: Uncontrolled GSAP instances across multiple route mounts could cause layout jitter or scrolling locks.
- **Change**: The codebase was refactored in Prompt 04 to centralize all GSAP logic through `<PageTransition>`, `<Reveal>`, and `<Parallax>`. Strict `useGSAP` boundaries (with automatic cleanup) were used.
- **Reason**: Prevents orphaned ScrollTriggers and timeline memory leaks in a React SPA environment.
- **Files**: `Reveal.tsx`, `Parallax.tsx`, `PageTransition.tsx`
- **Risk**: Resolved in previous steps, stability confirmed in final build.

## 3. SEO Route Foundations
- **Problem**: Lack of server-side rendering limits some SEO capabilities.
- **Change**: Configured semantic HTML5 across all pages. Maintained all core textual content in the DOM rather than relying on WebGL or Canvas rendering.
- **Reason**: Ensures crawlers that execute JavaScript can still index the hierarchy of the brand.
- **Files**: All `src/pages/*.tsx`
- **Risk**: None, inherent to SPA architecture.

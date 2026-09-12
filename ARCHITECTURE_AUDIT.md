# NYX - Architecture Audit

## 1. Current Framework & Environment
- **Framework:** React + Vite (Note: The advanced prompt specifies Next.js, so migration to Next.js or a compatible App Router architecture is expected in the future, but currently it is a client-side Vite SPA).
- **Language:** TypeScript
- **Styling:** Tailwind CSS (configured via Vite plugin and `index.css`)
- **Animation:** GSAP (`gsap` and `gsap/ScrollTrigger`)
- **State:** Local component state (Zustand was previously used for the 3D scene but is now removed).
- **Routing:** No explicit router (`react-router` or Next.js App Router is missing); currently a single-page scrolling structure in `App.tsx`.

## 2. Current Directory Tree
```text
/
├── package.json
├── tsconfig.json
├── vite.config.ts
├── src/
│   ├── App.tsx
│   ├── main.tsx
│   ├── index.css
│   ├── components/
│   │   ├── brand/
│   │   │   ├── Loader.tsx
│   │   │   └── Nav.tsx
│   │   └── sections/
│   │       ├── Hero.tsx
│   │       ├── Showcase.tsx
│   │       ├── Story1.tsx
│   │       └── Story2.tsx
│   └── lib/
│       └── utils.ts
```

## 3. Current Routes
- `/` (Single scrolling page)

## 4. Current State Management
- No global state currently remains.

## 5. Current Animation Architecture
- GSAP and ScrollTrigger are installed.
- Loader uses basic GSAP timeline.
- No global animation tokens yet.

## 6. Current Asset Architecture
- No external assets (images, videos, fonts) currently exist in the repository.

## 7. Current Dependencies
- `react`, `react-dom`, `vite`, `tailwindcss`, `@tailwindcss/vite`, `gsap`, `clsx`, `tailwind-merge`

## 8. Current 3D/Orb-Related Files
- All removed.

## 9. Current Technical Debt & Risks
- **Route Architecture:** Needs transition from single-page scroll to distinct routes (`/about`, `/what-we-do`, `/motivation`, `/first-release`, `/contact`).
- **Framework Limitations:** Current setup is Vite (Client-Side Rendering). A production-grade e-commerce site with SEO requirements usually necessitates Next.js (Server-Side Rendering). This migration will need to be addressed in subsequent steps if full SEO compliance is strictly enforced.
- **Missing Global Context:** No global shell or context for cart/search.

## 10. Recommended Migration Sequence
1. Migrate from single-page scroll to a multi-route architecture.
2. Establish design tokens and global shell (Header/Footer).
3. Build out the required static pages.
4. Finalize media, animation, and responsive behavior.

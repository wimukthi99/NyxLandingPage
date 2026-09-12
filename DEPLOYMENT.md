# NYX - Deployment Guide

## Overview
NYX is built as a standard React Single Page Application (SPA) using Vite. It outputs static HTML, CSS, and JavaScript, making it compatible with any modern static hosting provider (Vercel, Netlify, Cloudflare Pages, Firebase Hosting, Cloud Run with an Nginx container).

## Build Instructions

1. **Install Dependencies:**
   ```bash
   npm install
   ```

2. **Run Development Server:**
   ```bash
   npm run dev
   ```

3. **Production Build:**
   ```bash
   npm run build
   ```
   This compiles the application into the `dist/` folder.

## Environment Variables
- Currently, NYX has no required client-side environment variables (`VITE_*`).
- **Future Integration**: When commerce or backend contact functionality is added, the API endpoints will need to be configured via `.env`. Do not expose secret keys (like Stripe Secret Keys) to the client.

## Deployment Recommendations
- **Routing**: Because this is an SPA, ensure your hosting provider redirects all unknown routes (404s) to `index.html` so React Router can handle them.
- **Caching**:
  - Cache `index.html` with a short TTL (e.g., `Cache-Control: no-cache`).
  - Cache the hashed assets in `dist/assets/` immutably (e.g., `Cache-Control: public, max-age=31536000, immutable`).

## Asset Requirements
- The image placeholders (e.g., `FIRST_RELEASE_IMAGE_01`) must be replaced with actual CDN URLs or local files in the `public/` directory prior to public launch. Refer to `MEDIA_MANIFEST.md` for sizing specifications.

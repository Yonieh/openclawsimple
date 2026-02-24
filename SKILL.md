# Website Skill

You manage the Astro website at `/root/.openclaw/workspace/openclaw-website/`.

## Project Structure
- Pages: `src/pages/` (homepage is `index.astro`)
- Guide pages: `src/pages/guides/*.astro`
- Layout: `src/layouts/BaseLayout.astro` — ALL guide pages must use this
- Deployed to Cloudflare Pages via the build command

## Creating a New Guide Page

Every guide page follows this exact pattern:

---
import BaseLayout from '../../layouts/BaseLayout.astro';
---

<BaseLayout
  title="Page Title — Include (2026) for SEO"
  description="Clear meta description under 160 characters.">

  <div class="article">
    <div class="container-narrow">
      <h1>Page Title</h1>
      <p class="subtitle">One-line summary for the reader.</p>

      <h2>Section Heading</h2>
      <p>Content here. Use <strong>bold</strong> for emphasis.</p>
      <p>Use <a href="/guides/other-page">internal links</a> to cross-link guides.</p>

      <ul>
        <li><strong>Label:</strong> Description</li>
      </ul>

      <div class="cta-box">
        <h3>Call to Action</h3>
        <p>Why they should click.</p>
        <a href="/guides/railway-quick-start" class="cta-btn">Button Text →</a>
      </div>
    </div>
  </div>

</BaseLayout>

## Available CSS Classes (from BaseLayout)
- `.article` — page wrapper with top padding
- `.container-narrow` — 800px centered column
- `.subtitle` — grey intro text under h1
- `.cta-box` — gradient call-to-action box (accent colour by default)
- `.cta-btn` — white button inside cta-box
- h2, h3, p, ul, ol, li, code, pre — all styled automatically inside `.article`
- Links inside `.article` are accent-coloured with underline

## Style Rules
- Dark theme — DO NOT use Tailwind classes, light backgrounds, or inline styles
- British English spelling (colour, organise, realise)
- Write for complete beginners — no jargon, explain every technical term
- Short sentences, short paragraphs
- Always cross-link to other guides where relevant
- External links: add target="_blank" rel="noopener"

## Building and Deploying
After creating or editing files:
1. cd /root/.openclaw/workspace/openclaw-website
2. npm run build
3. Deploy (ask owner for deploy method if unsure)

## Sitemap
Update `public/sitemap.xml` when adding new pages.

## IMPORTANT
- NEVER use Tailwind utility classes — they are not loaded
- NEVER create standalone HTML pages — always use BaseLayout
- NEVER use inline style="" attributes — use the existing CSS classes
- Always send an approval request before publishing new pages

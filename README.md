# Goldfin Group Website (Astro + Netlify)

This is your complete website. Five pages plus a blog (Insights), built to match the approved design, with all GEO requirements baked in (clean HTML, schema markup, AI-crawler access, sitemap).

You own this entirely. No monthly platform fee, no gatekeeper. Hosting is free on Netlify.

---

## BEFORE YOU DEPLOY: three things to fill in

1. **Your booking link — already done.** The OnceHub embed is live at `/book` and all "Book a 15-minute call" buttons across the site point there. No action needed.
2. **Your LinkedIn URL.** In `src/layouts/BaseLayout.astro`, the schema has a placeholder LinkedIn link. Update it.
3. **Compliance.** Cat reviews the live preview before the domain is connected. The footer disclosure is already in place.

---

## OPTION A — Deploy via GitHub (recommended, enables easy blog posting)

This is the path that lets you and Cat publish new articles from a web browser, with no software.

1. Create a free account at github.com
2. Create a new repository called `goldfin-group`
3. Upload this entire folder to it (GitHub lets you drag files in via "Add file > Upload files")
4. Create a free account at netlify.com
5. In Netlify: "Add new site" > "Import an existing project" > connect GitHub > pick your `goldfin-group` repo
6. Netlify auto-detects Astro. Confirm: build command `npm run build`, publish directory `dist`. Click Deploy.
7. Your site goes live at a netlify.app URL in ~2 minutes. Send that to Cat for compliance review.

## OPTION B — Quick preview without GitHub

If you just want to see it locally first:
1. Install Node.js (nodejs.org, version 20+)
2. In this folder, run: `npm install` then `npm run dev`
3. Open the localhost link it prints

To deploy this way: run `npm run build`, then drag the resulting `dist` folder to netlify.com/drop. (Note: with this method, every update means rebuilding and re-dragging. Option A is better long-term.)

---

## CONNECTING goldfingroup.com (after Cat approves)

1. In Netlify: Site settings > Domain management > Add custom domain > `goldfingroup.com`
2. Netlify shows you DNS records to add
3. Log into wherever the domain is registered, add those records
4. Wait a few hours, confirm the site loads at goldfingroup.com
5. Cancel ClickFunnels

SSL/HTTPS is automatic and free once the domain connects.

---

## HOW TO PUBLISH A NEW BLOG POST (the YouTube workflow)

Every blog post is a single text file in `src/pages/insights/posts/`. To add one:

1. Copy an existing post file (e.g. `quarterback-gap.md`) as a starting template
2. Rename it something URL-friendly, like `my-new-topic.md`
3. Edit the top section (between the `---` lines):
   - `title:` the article headline
   - `tag:` one of: Before / During / After / Mindset
   - `date:` today's date, format YYYY-MM-DD (newest posts show first)
   - `readTime:` e.g. "6 min read"
   - `excerpt:` one or two sentences for the listing page
   - `featured:` true on the one post you want highlighted at the top; false on the rest
   - `youtube:` the YouTube video ID (the part after `watch?v=` in the URL). Leave as `""` if none. When filled in, the video embeds automatically at the top of the article.
4. Below the second `---`, paste the article text. Use a blank line between paragraphs. For a heading, start a line with `## `. For bold, wrap text in `**like this**`.
5. Save. If using GitHub (Option A), commit the file in the browser and Netlify republishes in ~2 minutes automatically.

That's the whole job. The design, the schema markup, and the listing all happen automatically.

---

## WHERE THINGS LIVE

- Page copy: `src/pages/*.astro` (home is `index.astro`)
- Blog posts: `src/pages/insights/posts/*.md`
- Site-wide design (colors, fonts): `public/styles/global.css`
- Logo, photos, book image: `public/assets/`
- Nav, footer, schema: `src/layouts/BaseLayout.astro`
- AI crawler permissions: `public/robots.txt`

---

## GEO checklist (already done)

- [x] Clean static HTML, server-rendered, fully readable by AI crawlers
- [x] robots.txt explicitly allows GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot, Google-Extended, and more
- [x] Organization + FinancialService + Person schema on every page
- [x] Article schema (with dates) on every blog post
- [x] Automatic sitemap at /sitemap-index.xml
- [x] Fast-loading optimized images
- [x] Mobile responsive with working menu

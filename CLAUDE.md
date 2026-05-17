# CLAUDE.md — GA Consulting site

This file teaches Claude Code how to work on this site. Read it at the start of every session.

## What this site is

Static HTML consulting site for Guido Arazi, operating as **GA Consulting**.

- 4 pages: `index.html`, `about.html`, `articles.html`, `contact.html`
- No build step — open `index.html` in a browser, that's the site
- No framework, no dependencies, no `node_modules`
- Inline `<style>` at the top of each page (intentional — keeps each page self-contained)
- Inline `<script>` at the bottom for the mobile menu toggle
- Hosted on [REPLACE — Cloudflare Pages / Netlify / GitHub Pages / Vercel]

## Positioning (the wedge)

**Guido is a Notion + AI consultant for small and medium companies that want one connected operating system instead of tool chaos.**

Buyer: founder / Head of Ops / Office Manager at a 10-100 person company.

Buyer's pain: information lives in Slack, email, Drive, 4 spreadsheets, 2 project tools, and someone's head. Nothing connects. Onboarding new hires takes weeks. The founder can't get a clear status on the business without asking 6 people.

What Guido sells: a connected operating system in Notion — CRM, projects, knowledge, team, processes — with AI agents on top, integrated to where work actually happens (Slack, email, calendar, files, payments).

**What Guido does NOT sell:**
- Anaplan replacement, Pigment replacement, enterprise FP&A
- "Notion AI consultant" (too generic)
- Cheap Notion cleanups (€500 jobs)
- Templates without setup

**Credentials to lean on:** Solution Architect with 5 years in enterprise planning (Anaplan / EPM platform). Pivoting that systems-thinking discipline into Notion + AI for SMBs.

## Tone & voice rules

- **Speak to the buyer, not to other consultants.** Founder / Head of Ops at a 30-person company is the reader.
- **Lead with their problem in their language.** Tool chaos, lost leads, slow onboarding, "where is that file." Not technical Notion terminology.
- **First person singular ("I").** Not "we." Don't pretend to be a team that doesn't exist yet.
- **Confident, calm, direct.** Avoid hype words: "revolutionary," "game-changing," "unlock," "leverage," "supercharge," "AI-powered."
- **Specifics over abstractions.** "Onboarding new hires went from a week to two days" beats "improve operational efficiency."
- **No emojis. No purple gradients. No generic AI-aesthetic.** The site has a distinctive editorial feel — preserve it.
- **British/European English** ("recognise," "behaviour," "favourite") unless I tell you otherwise.

## Design system

### Colors (CSS variables, defined per page in `:root`)

```
--paper: #f7f3ec    ← main background (warm off-white)
--ink:   #18160f    ← primary text and dark backgrounds
--soft:  #e8e2d6    ← secondary background, soft accents
--rule:  #cdc7bc    ← borders and dividers
--red:   #9b2c1a    ← accent color, italic emphasis, hover states
--muted: #7c7872    ← secondary text
--white: #fffefb    ← buttons, photo border, "white" backgrounds
```

**Never introduce a new color without asking.** The palette is deliberate.

### Typography

Three fonts loaded from Google Fonts:

1. **Cormorant Garamond** (serif) — headlines, section titles, stat numbers, italic accents
   - Weights used: 300, 400, 600 (incl. italic)
2. **Karla** (sans-serif) — body copy, descriptions, paragraphs
   - Weights used: 300 (default), 400, 500
3. **Courier Prime** (monospace) — labels, nav links, buttons, tags, section numbers
   - Weights used: 400 (incl. italic)

Italics in `<em>` tags use Cormorant Garamond italic in `--red`. This is the signature visual touch — preserve it.

Letter-spacing matters: monospace elements use 1-3px tracking, uppercase, small font size (9-12px). Don't lowercase these.

### Layout patterns

- Section padding: `100px 48px` on desktop, less on mobile
- Section dividers: 1px or 2px `--rule` or `--ink` borders
- Grid columns separated by 1px or 2px borders (not gaps)
- Cards have hairline borders, hover → background lightens to `--white`
- Numbered sections: `<span class="section-num">01</span>` before section titles

## Content rules

### Hero headlines

Format: serif, large (52-88px), `font-weight: 300`, `line-height: 1.0`, with `<em>` italic accent in red on one word. Keep them 3-5 lines max.

Examples that work:
- "I build systems that replace *chaos* with clarity."
- "One place where your company actually *lives*."
- "Stop working *around* your tools."

### CTAs

Primary action: "Book a free call" (links to `contact.html`)
Secondary: "See what I do" / "Read more" / etc.

Discovery call is **free, 30 minutes, no pitch**. Always frame it that way.

### Services (Section 01)

Currently three cards:
- S·01 — Full Notion Setup
- S·02 — CRM & Sales System
- S·03 — Operations & Wiki

Keep this structure. When pricing is added later, anchor numbers:
- Full setup: €6-10k (pilot) → €10-15k (standard) after first 3 clients
- CRM-only: €3-5k
- Operations & Wiki: €3-5k
- Audit (smaller entry offer): €1,500 for 1 week
- Fractional retainer: €2,500-4,500/month, 3-month minimum (don't list publicly until month 9)

### Testimonials

Currently placeholders. Replace one at a time as real ones come in. Format: italic serif quote + small monospace attribution. **Never invent testimonials.**

### Blog (articles.html)

Current draft pipeline (write in this order, roughly one per 2 weeks):

1. Why most Notion setups fail — and how to fix yours
2. The five databases every small company needs
3. How I automate client onboarding with n8n and Notion
4. What enterprise consulting taught me about small companies
5. The case for one tool over five
6. Notion + AI: what actually works in 2026 (and what doesn't)
7. How to know when your company has outgrown spreadsheets
8. The weekly review ritual that runs my entire consulting practice

### Footer

`G.A Consulting` logo, footer links, year. KvK and BTW numbers go here once registered.

## Editing rules for Claude Code

1. **Match the existing style.** Open similar sections in other files before adding new ones. Reuse class names. Don't introduce new patterns unless asked.

2. **Cross-file consistency.** Nav menu appears in all 4 pages. Footer appears in all 4. When you change one, update all four.

3. **When adding a new blog post:**
   - Create the post content as a new section in `articles.html` (or, eventually, a new sub-page)
   - Add a teaser card in `index.html` under "From the blog" — replace the oldest of the 3 cards
   - Update dates: Cormorant Garamond, format "Month YYYY"
   - Use existing tag styles: `<span class="teaser-post-tag">Notion</span>` (or Operations, Automation, Business, AI)

4. **When adding a new service:**
   - Ask first — services should not exceed 3-4 cards
   - If replacing one, ensure the messaging ladders up to the wedge

5. **Mobile responsiveness:** existing media queries are minimal but functional. Don't add complex breakpoints unless asked. The site is read on desktop more than mobile for B2B.

6. **Don't add JavaScript** beyond what's there (mobile menu toggle). The site is intentionally static. If interactivity is needed, ask first.

7. **Don't add tracking, analytics, or external scripts** without explicit instruction.

8. **Don't change fonts.** Don't add Inter, Plus Jakarta, system fonts, or any default. The three-font system is the signature.

## Common edits

### "Update the blog teasers"
Open `index.html`, find `.articles-teaser` section, replace the three `.teaser-post` divs. Then check `articles.html` to ensure the linked posts exist.

### "Add a testimonial"
Open `index.html`, find `.trust` section, replace one of the `.trust-item` placeholders. Use real attribution. Match style: italic quote, monospace name.

### "Change the hero headline"
Open `index.html`, find `.hero-headline`. Preserve `<br>` line breaks and `<em>` red italic accent. Keep under 6 words per line.

### "Add a new service card"
Open `index.html`, find `.services-grid`. Match existing structure exactly: `service-num`, `service-name`, `service-desc`, `service-includes` (5 bullets max).

### "Publish a new article"
1. Add article card to `articles.html`
2. Add teaser to `index.html`
3. Write the article content (start as draft inside Notion, then drop the finished HTML into a new article page or section)
4. Update dates everywhere

## Deployment

[REPLACE WITH ACTUAL DEPLOY PROCESS — likely one of:]

- **If Cloudflare Pages:** Pushes to `main` branch auto-deploy. `wrangler pages deploy .` for manual.
- **If Netlify:** Drag-and-drop the folder, or connect to GitHub for auto-deploy on push.
- **If GitHub Pages:** Pushes to `main` auto-deploy via Actions.
- **If Vercel:** `vercel --prod` or auto-deploy on push.

## Things NOT to do

- Don't suggest migrating to Astro/Next.js/anything. We chose static HTML deliberately. Revisit at month 6+.
- Don't suggest a CMS. We chose Claude Code as the CMS.
- Don't add comment sections, social media embeds, chat widgets, or any third-party JS.
- Don't change "GA Consulting" branding without asking.
- Don't replace testimonial placeholders with invented testimonials. Mark as `[PLACEHOLDER]` until real ones exist.
- Don't add Anaplan-replacement framing. The wedge is "Company OS for SMBs," not "cheap alternative to enterprise EPM."

## Open questions / placeholders to resolve

- [ ] Domain name — currently linking to local files
- [ ] Hosting provider — see Deployment section
- [ ] Cal.com link for discovery call — currently `contact.html`, fine for now
- [ ] Real testimonials — 3 placeholders in `index.html`
- [ ] KvK + BTW numbers for footer — pending ZZP registration
- [ ] Newsletter signup — not yet on site, add when Beehiiv is set up
- [ ] Real photo at higher resolution — current is fine but embedded as base64 (large file)

## Session protocol

At the start of every session, after reading this file:
1. Confirm which page(s) we're editing
2. State the change in one sentence before making it
3. Make the change
4. Note any cross-page sync needed (nav, footer, blog cross-links)
5. Don't ask permission for small edits inside agreed scope; do ask for new sections, new patterns, or structural changes

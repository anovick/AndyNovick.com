# AndyNovick.com — Site Specification

**Owner:** Andy Novick
**Status:** Final v1 — ready to build
**Canonical domain:** AndyNovick.com
**Redirect domain:** AndrewNovick.com (301 redirects to AndyNovick.com)
**Platform:** WordPress with the Twenty Twenty-Five block theme
**Hosting:** GoDaddy Ultimate Managed Hosting for WordPress (added as a second site to existing plan, $4.99/mo extra)
**Target launch:** v1 = blog shell + About page; v2 = migrations from other properties

---

## 1. Goals & Context

AndyNovick.com will be Andy's personal hub: a blog, an About page, and a curated set of links to his other online resources. Andy is turning 70 in July 2026, has wound down his prior consulting work, and is using this freed-up time to explore AI and AI-assisted coding. The blog is the heart of the site; everything else supports it.

**Primary goals**
1. Publish a personal blog, dominated initially by an "AI Discoveries" theme.
2. Make it easy for visitors to find Andy's other resources (Blogger, SmugMug, GitHub, NovickSoftware.com, YouTube, social).
3. Build a foundation that can later absorb content from other sites (notably NovickSoftware.com, whose hosting expires February 2027).

**Non-goals for v1**
- No e-commerce, no membership, no paid content.
- No comments at launch (revisit later).
- No migration of NovickSoftware.com or SmugMug content (Phase 2).

---

## 2. Naming Decision

The canonical domain is **AndyNovick.com**. AndrewNovick.com is owned but 301-redirects to AndyNovick.com.

**Rationale:** Everyone calls Andy "Andy" — has since age 14. The personal blog voice ("AI discoveries & other curiosities") fits "Andy" better than the more formal "Andrew." His other properties already use the "Andy" brand (AndyNovick.smugmug.com, AndysGuyStuff.blogspot.com). Holding AndrewNovick.com as a redirect protects against people who search for or type the formal name.

**Wordmark in site header:** "Andy Novick"
**Byline on posts:** "Andy Novick" (consistent with the wordmark; can be customized per-post if needed)

---

## 3. Platform: WordPress

WordPress was chosen over Astro because:

- **Hosting alignment.** The site lives on the same GoDaddy Ultimate Managed Hosting plan as NovickSoftware.com — just added as a second site for $4.99/month.
- **Content workflow.** Andy writes in Word and wants to include photos, graphs, and small spreadsheets. WordPress's Gutenberg editor handles all of these natively.
- **Familiarity.** Andy already runs a WordPress site, no learning curve.
- **Maintenance.** GoDaddy handles WordPress core updates and daily backups automatically.
- **Staging environment.** The Ultimate tier includes a free staging site for each WordPress instance — useful for testing changes without breaking production.

---

## 4. Theme: Twenty Twenty-Five

WordPress's official 2025 default theme. A modern block theme with full-site editing support, 70+ block patterns, and 9 style variations. Selected because:

- Modern, accessibility-ready, mobile-first.
- Designed for personal blogs (among other use cases).
- Full-site editing means layout changes don't require code.
- No plugin lock-in or page builder bloat.
- WordPress core direction — future-proof.

Start from the **"Afternoon" style variation** as the closest baseline, then customize colors and typography (see §6).

---

## 5. Site Architecture

### 5.1 Pages

| Page | Purpose | Notes |
|---|---|---|
| **Home** | Blog feed (most recent posts), small header above, rich footer below | The face of the site |
| **About** | Andy's bio, photo, story | "Turning 70, exploring AI" framing |
| **Blog archive** | All posts, filterable by category | Standard WP archive |
| **Category pages** | Filtered views | One per category |
| **Resources** | Consolidated index of external sites | Same content as footer, but a full page with more detail |
| **Contact** | Simple form or email link | Optional for v1 |

### 5.2 Top navigation (in hamburger menu)

`Home | About | Blog | Resources | Contact`

The hamburger sits at the top right of the header on all viewports. The header is small (see §6.1), so navigation lives behind the menu rather than as a horizontal bar.

### 5.3 Categories at launch

1. **AI Discoveries** — primary theme
2. **Photography**
3. **Programming** (includes SQL)
4. **Thoughts and Events** — books, movies, current events, family

Posts can belong to multiple categories. Tags can be added freely.

### 5.4 Permalink structure

- Posts: `/blog/%postname%/`
- Pages: `/%pagename%/`
- Categories: `/category/%category%/`

**Note for Phase 2:** When NovickSoftware.com content is migrated, plan to use a separate prefix (e.g., `/sql/%postname%/` or `/resources/%postname%/`) to keep blog posts and legacy reference content visually distinct in URLs.

---

## 6. Layout & Visual Design

### 6.1 Header (all viewports)

A small, compact header bar containing:

- **Left:** Small circular portrait of Andy (roughly 56–80px diameter), with wordmark "Andy Novick" and tagline "AI discoveries & other curiosities" inline to the right.
- **Right:** Hamburger menu icon.

Total header height around 80–90px. No hero photo, no large image — content begins immediately below.

### 6.2 Main content (homepage)

Single-column, centered, max content width around 720px. Posts appear as a vertical feed, each showing:

- Category label (small caps, ochre accent)
- Title (serif, medium weight)
- Date + reading time (muted)
- Excerpt (first 2–3 sentences, optional)
- "Read more →" link

Featured image is optional per post — works fine with or without. The first post in the feed gets slightly more breathing room and an excerpt; subsequent posts can be more compact.

### 6.3 Footer

Rich, dark-toned footer (warm dark brown/charcoal, not pure black) containing the "Elsewhere" resource hub:

- **Primary links** in a two-column grid, each with name + one-line description:
  - GitHub — Public code repositories
  - SmugMug — Photo gallery
  - Novick Software — SQL resources
  - YouTube — Occasional videos
- **Secondary row** for social: LinkedIn, X, Facebook, Blogger (legacy)
- Standard copyright line at the very bottom

This is the primary navigation to other properties — the right-column sidebar from the original draft has been dropped.

### 6.4 Mobile (<768px)

Same single-column layout, just narrower. Header collapses naturally (the wordmark and tagline may stack below the portrait on very narrow screens). Footer grid becomes single-column.

### 6.5 Color palette

**Primary accent: muted ochre.** Approximately `#B07A3F` for most uses (category labels, links, "Read more →"). A slightly deeper variant (`#8A5A2B`) for body-text links and hover states.

**Base palette:**
- Background: warm off-white, around `#FBF8F3`
- Body text: dark charcoal, around `#2C2A26`
- Secondary text (dates, meta): muted warm gray, around `#8A847A`
- Footer background: warm dark brown, around `#2C2A26`
- Footer text: warm light gray, around `#C8C0B4`

Tune during build; these are starting values that worked well in the mockup.

### 6.6 Typography

Following the convention used by writing-focused sites (NYT, The Atlantic, Substack):

- **Body text and headlines:** Serif. Recommended: Source Serif 4 (free, from Google Fonts) or Lora. Georgia as the safe system fallback.
- **UI chrome:** Sans-serif. Recommended: Inter, or the system stack (`-apple-system, system-ui, sans-serif`). Used for category labels, dates, navigation, footer, buttons.
- **Code blocks:** Monospace, JetBrains Mono or system mono fallback.

This overrides Twenty Twenty-Five's default Manrope-everywhere pairing. The serif/sans contrast separates "what you read" from "what you click."

**Sizes (starting points):**
- Body: 16px, line-height 1.65
- Post title in feed: 19–22px, weight 500
- Post title on individual post page: 28–34px, weight 500
- Category label / small caps: 11px, letter-spacing 0.8px
- Footer link: 13px

---

## 7. Content Model

### 7.1 Blog posts

Each post has:
- Title
- Date (published, optionally updated)
- Author (always Andy, field exists for future)
- Category (1+, from the four launch categories)
- Tags (freeform)
- Featured image (optional)
- Body — paragraphs, headings, images, galleries, embedded video, tables, code blocks, file downloads (small spreadsheets, etc.)
- Excerpt (auto-generated unless overridden)

### 7.2 Pages

About, Resources, Contact — standard WordPress pages, edited in Gutenberg.

### 7.3 Resource entries

The footer and /resources page draw from the same source. Each resource has:
- Name
- URL
- Short description (1 line)
- Category (Primary or Social)

Implement as either a small custom post type, an ACF repeater on a settings page, or a reusable block — whichever is simplest in Twenty Twenty-Five.

**Initial resource entries:**

| Name | URL | Description | Tier |
|---|---|---|---|
| GitHub | https://github.com/anovick | Public code repositories | Primary |
| SmugMug | https://andynovick.smugmug.com | Photo gallery | Primary |
| Novick Software | https://www.novicksoftware.com | SQL resources | Primary |
| YouTube | (channel URL TBD) | Occasional videos | Primary |
| LinkedIn | (URL TBD) | Professional profile | Social |
| X / Twitter | (URL TBD) | Occasional posts | Social |
| Facebook | (URL TBD) | Occasional posts | Social |
| Andy's Guy Stuff | https://andysguystuff.blogspot.com | Older personal blog (legacy) | Social |

Andy to fill in the URLs marked TBD.

---

## 8. Hosting & Domain Setup

**Host:** GoDaddy Ultimate Managed Hosting for WordPress (existing plan, shared with NovickSoftware.com).

**Action:** Add AndyNovick.com as a second WordPress site to the existing plan via "Buy Sites" → $4.99/month, billed prorated against the February 2027 renewal date. Includes a free staging site.

**Domain registration:**
- AndyNovick.com — register (cost ~$50 for three years; verify exact price at checkout).
- AndrewNovick.com — already owned; configure 301 redirect to AndyNovick.com after the new site is live.

**SSL:** Free Let's Encrypt cert via GoDaddy, automatically configured.

---

## 9. Plugins

Keep the stack lean. For v1:

| Plugin | Purpose |
|---|---|
| **Rank Math** (or Yoast SEO) | SEO basics, sitemaps, meta tags |
| **UpdraftPlus** | Scheduled backups to cloud storage (in addition to GoDaddy's daily backups) |
| **Wordfence** | Security hardening (GoDaddy provides some, this layers on extra) |
| **Akismet** | Spam protection (in preparation for comments later) |
| **Site Kit by Google** | Easy analytics integration |

Skip page builders (Elementor, Divi, etc.). Gutenberg + Twenty Twenty-Five's pattern library is sufficient. Skip caching plugins — GoDaddy Managed Hosting handles server-level caching automatically.

---

## 10. Migration Plan (Phase 2)

Not in v1, but planned now so v1 doesn't paint into a corner:

| Source | Plan | Target Timing |
|---|---|---|
| **NovickSoftware.com** | Export posts/pages via WP's native export tool; import into AndyNovick.com under a `/sql/` or `/resources/` URL prefix. Set up 301 redirects from old URLs to new before NovickSoftware hosting expires. | Late fall 2026, before February 2027 renewal |
| **AndysGuyStuff.blogspot.com** | Export via Blogger's export, convert to WXR, import to WP. Low volume so could be done early. | Anytime |
| **SmugMug** | Bulk download originals; decide whether to host all photos on AndyNovick.com (storage/bandwidth implications) or move to a different gallery solution. | When SmugMug subscription comes due |
| **YouTube** | Don't migrate; embed videos in blog posts as relevant. | N/A |

**Implication for v1:** Storage on the Ultimate plan is generous, but verify available headroom before migrating NovickSoftware.com content and any SmugMug photos.

---

## 11. Analytics

Use **Google Site Kit** to wire up Google Analytics 4. Easiest WordPress-native option. Can swap in Plausible or Fathom later for privacy-friendly analytics if preferred.

---

## 12. SEO & Discoverability

- Rank Math (or Yoast) handles meta titles/descriptions, XML sitemap, schema.
- Add Open Graph and Twitter card images for social sharing.
- Submit sitemap to Google Search Console.
- Configure AndrewNovick.com → AndyNovick.com 301 redirect (preserves any inbound links to the formal name).

---

## 13. Performance & Reliability

- Caching: handled by GoDaddy server-level cache (no plugin needed).
- Images: WebP where possible; lazy-load below the fold (Twenty Twenty-Five does this by default).
- Backups: GoDaddy daily backups (30-day retention) + UpdraftPlus weekly offsite backup to Dropbox or Google Drive for belt-and-suspenders.
- SSL: required, GoDaddy provides free Let's Encrypt cert.
- Target page weight: under 1 MB for the homepage on first load (Twenty Twenty-Five is lean by default).

---

## 14. Accessibility

- Twenty Twenty-Five is accessibility-ready (WCAG 2.1 AA) out of the box.
- All images need alt text (Andy adds when posting).
- Heading hierarchy preserved (one H1 per page).
- Color contrast verified for the ochre accent against the warm off-white background.

---

## 15. Development Environment

**Primary tool: Claude in Chrome.** Most of the v1 build happens inside wp-admin (Site Editor, Gutenberg, plugin settings). Claude in Chrome can navigate and operate the WordPress UI alongside Andy.

**Secondary tools:**
- **Claude in the chat (claude.ai)** for drafting blog content, About page copy, CSS snippets, and troubleshooting.
- **Claude Code (in VS Code or gitbash terminal)** if and when file-level edits are needed (child theme files, `wp-config.php`, custom snippets via SFTP).

**Staging-first workflow:** Build experiments on the GoDaddy staging copy of the site before pushing to live. The staging URL is provided in the GoDaddy dashboard.

---

## 16. Phased Roadmap

### v1 (Launch) — target: within a few weeks
- Register AndyNovick.com, add as second site to GoDaddy Ultimate plan
- WordPress installed with Twenty Twenty-Five activated
- Custom style variation created: ochre accent, warm off-white background, dark footer, serif/sans typography pairing
- Header pattern customized: small portrait + wordmark "Andy Novick" + tagline + hamburger
- Footer pattern customized: dark "Elsewhere" hub with two-column resource grid and social row
- About page written
- First 2–3 blog posts written and published
- Resources page populated (mirrors the footer with more detail)
- Plugins installed: Rank Math, UpdraftPlus, Wordfence, Akismet, Site Kit
- AndrewNovick.com 301 redirect configured
- SSL active
- Sitemap submitted to Google Search Console

### v1.1 — first month after launch
- Refine layout based on how it feels with real content
- Add comments (Akismet already in place) if Andy wants them
- Decide on newsletter signup (Mailchimp, MailerLite, or Buttondown)
- Tune ochre tones and typography based on lived experience

### v2 — Phase 2 migrations
- Import Blogger content (anytime)
- Import NovickSoftware.com content with `/sql/` URL prefix; set up redirects (target: late fall 2026)
- Decide on SmugMug strategy
- Possibly revisit theme if content volume justifies a redesign

---

## 17. Open Items for Build Phase

Decisions deferred from spec to build, none blocking:

1. **Exact social URLs** — fill in YouTube channel, LinkedIn, X, Facebook URLs.
2. **Portrait photo** — small, well-lit, friendly head-and-shoulders, square crop.
3. **Final ochre values** — start with `#B07A3F` and tune in the WordPress Styles editor against real content.
4. **Final serif choice** — Source Serif 4 vs. Lora. Try both, pick what reads better.
5. **Contact form vs. email link** — preference.
6. **Newsletter signup** — yes/no for v1.1.
7. **Logo/wordmark styling** — typeset name as shown in mockup, or something more designed.

---

## Appendix A: Design Direction Summary

The site borrows the warmth and voice of personal blogs like AlFranken.com — small intentional design, real personality, a clear sense of who's writing — while staying current with modern minimal aesthetics: single-column layout, small header, generous whitespace, muted earth-tone accent, serif body text for readability, rich footer instead of sidebars.

**What we explicitly rejected:**
- The three-column layout from the original draft (too dated for a modern personal blog).
- A large hero photo (too dominant; eats screen real estate).
- A right-column sidebar with resource links (modern footers do the job better).
- Bright or corporate colors (ochre keeps it warm and personal).
- Twenty Twenty-Five's default Manrope-everywhere typography (serif body reads better for long-form writing).
- The formal "Andrew" framing (Andy is who he is).

**What we kept:**
- WordPress as the platform (familiarity, hosting alignment, content workflow).
- The four blog categories: AI Discoveries, Photography, Programming, Thoughts and Events.
- Phase 2 migration plan for NovickSoftware.com, SmugMug, and Blogger.
- The instinct that the blog is the heart of the site and everything else supports it.

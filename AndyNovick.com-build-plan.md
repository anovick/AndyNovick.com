# AndyNovick.com — Build Session Plan

A step-by-step plan for getting the site from "nothing" to "live with a couple of posts." Designed to be done across 3–5 working sessions, each 1–2 hours, with Claude in Chrome as the primary working environment.

The plan assumes you've read the spec (`AndyNovick.com-spec.md`).

---

## Before the first session — 15 minutes of prep

These are quick things best done outside of a session so we don't burn build time on them:

1. **Pick or take a portrait photo.** A square or near-square head-and-shoulders shot, well-lit, friendly expression. Doesn't need to be professional — a good phone photo works. Save it somewhere you can grab quickly (~500×500px or larger is plenty).
2. **Draft your About page in Word.** 200–400 words. The story we discussed: turning 70, wound down consulting, exploring AI as a curious enthusiast, what you used to do, what you're up to now. We'll polish it together but having a first draft saves time.
3. **Gather your exact social URLs:**
   - YouTube channel URL
   - LinkedIn profile URL
   - X/Twitter profile URL
   - Facebook profile URL
4. **Decide on your contact preference:** email link (simplest, just `mailto:you@example.com`) or a contact form. You can change later.

---

## Session 1 — Hosting and domain setup (about 45 min)

**Goal:** Get AndyNovick.com registered, attached to your GoDaddy plan, and resolving to a blank WordPress install.

### Steps

1. **Register AndyNovick.com.**
   - In GoDaddy, search for `andynovick.com`.
   - Add to cart, 3-year registration (~$50).
   - Skip all the upsells (privacy add-ons, email, etc. — you can add later if needed).
   - Complete checkout.

2. **Add a second site slot to your Managed Hosting for WordPress plan.**
   - Go to **My Products** → next to **Managed WordPress** click **Manage All**.
   - On the Ultimate Managed Hosting plan, find **Settings** → **Plan Details** → **Buy Sites**.
   - Buy **1 additional site** at $4.99/month, prorated. Complete checkout.

3. **Create the new WordPress site.**
   - Back on the Managed Hosting dashboard, click **Create WP Site**.
   - When asked how to build the site, choose **"Start with WordPress"** (skip the AI site builder — we don't want it generating content).
   - Assign the domain: **AndyNovick.com**.
   - Choose a strong admin username (not "admin") and password. Save them in a password manager.
   - Set the site title to **"Andy Novick"** and tagline to **"AI discoveries & other curiosities"** (you can change later).

4. **Verify the site is live.**
   - Visit https://andynovick.com — you should see a default WordPress site.
   - If you see a "site under construction" or temporary domain, wait 5–10 minutes for DNS to propagate, then refresh.

5. **Verify SSL is active.**
   - The URL should show `https://` with a padlock icon. GoDaddy auto-installs Let's Encrypt; if it's not active within 30 min, contact GoDaddy support.

6. **Bookmark the staging URL.**
   - In the GoDaddy dashboard for the new site, find the staging URL (usually something like `andynovick.com-staging.www.example.com`).
   - We'll do most experimental work here before pushing to live.

**End-of-session check:** You can log into wp-admin at `https://andynovick.com/wp-admin`, see the default WordPress dashboard, and load the homepage with HTTPS.

---

## Session 2 — Theme and style setup (60–90 min)

**Goal:** Twenty Twenty-Five activated, custom style variation created with ochre palette and serif/sans typography.

### Open Claude in Chrome and load wp-admin alongside it.

1. **Activate Twenty Twenty-Five.**
   - **Appearance → Themes.** Twenty Twenty-Five should be installed by default. If not, click **Add New** and search for it.
   - Activate it. (You can deactivate any other themes later.)

2. **Open the Site Editor.**
   - **Appearance → Editor.**
   - This is where Twenty Twenty-Five's customization happens.

3. **Apply the "Afternoon" style variation as a baseline.**
   - In the Site Editor, click the **Styles** icon (looks like a circle, half-shaded).
   - Click **Browse styles** at the top of the Styles panel.
   - Find **Afternoon** and click it. The site will preview the new style.
   - Click **Save** to apply.

4. **Customize the colors.**
   - In the Styles panel: **Colors** → edit the palette.
   - Replace the green primary with ochre `#B07A3F`.
   - Set background to `#FBF8F3`.
   - Set body text to `#2C2A26`.
   - Save.

5. **Customize typography.**
   - In the Styles panel: **Typography**.
   - **Body**: change to a serif. If Source Serif 4 isn't in the list by default, you can add a Google Font via the **Font Library** (Appearance → Font Library) — search for Source Serif 4 and install.
   - **Headings**: same serif (or a heavier weight of it).
   - **Buttons / UI**: keep sans-serif (Inter or system).
   - Save.

6. **Tune the footer color.**
   - Site Editor → **Templates** → find the footer template part.
   - Set background to `#2C2A26`, text to `#C8C0B4`.
   - Save.

**End-of-session check:** Refresh the homepage — it should now have a warm off-white background, ochre accents, serif body text, and a dark footer.

---

## Session 3 — Header and footer patterns (60–90 min)

**Goal:** Custom header with portrait + wordmark + tagline + hamburger; rich footer with resource grid.

### Header

1. **Open the Header template part in Site Editor.**
   - **Appearance → Editor → Patterns → Template Parts → Header.**

2. **Replace the default header with the layout from the mockup.**
   - Delete the default header content.
   - Insert a **Row** block with three columns of content:
     - Left: an **Image** block for the portrait (upload your photo, crop to circle via the block's "Style" → border-radius, or use a circular mask). Size to 64px.
     - Middle: a **Stack** block with two text blocks: "Andy Novick" (larger, weight 500) and "AI discoveries & other curiosities" (smaller, muted).
     - Right: a **Navigation** block (which on mobile/narrow viewports becomes the hamburger automatically).
   - Align items to center vertically.

3. **Configure the navigation menu.**
   - Add menu items: Home, About, Blog, Resources, Contact.
   - Some pages don't exist yet — leave the links as drafts and we'll connect them in the next session.

4. **Save and check on different screen sizes.**
   - Use Chrome DevTools (right-click → Inspect → toggle device toolbar) to verify the header looks good at 1440px, 768px, and 375px wide.

### Footer

1. **Open the Footer template part.**
2. **Build the "Elsewhere" pattern:**
   - **Heading**: "Elsewhere" (small caps, ochre, letter-spaced).
   - **Columns block**, 2 columns:
     - GitHub — Public code repositories
     - SmugMug — Photo gallery
     - Novick Software — SQL resources
     - YouTube — Occasional videos
   - Below the columns, a **horizontal row** with social text links: LinkedIn, X, Facebook, Blogger.
   - At the very bottom: `© 2026 Andy Novick`.
3. **Save.**

**End-of-session check:** The header and footer match the mockup we approved. Navigation works on desktop and collapses to a hamburger on mobile.

---

## Session 4 — Pages and plugins (60–90 min)

**Goal:** About, Resources, and Contact pages created. Essential plugins installed and configured.

### Pages

1. **About page.**
   - **Pages → Add New.** Title: "About."
   - Paste in your draft from Word. Format with Gutenberg paragraph blocks.
   - Insert your portrait at the top (larger size than in the header).
   - Publish.

2. **Resources page.**
   - **Pages → Add New.** Title: "Resources."
   - Create a list of all your external resources, each with a one-paragraph description.
   - Group by category: Code, Photography, Older Writing, Social.
   - Publish.

3. **Contact page (optional, simplest version).**
   - **Pages → Add New.** Title: "Contact."
   - Single paragraph: "Easiest way to reach me is [your email]." Or embed a simple form via a plugin like WPForms Lite if you prefer.
   - Publish.

4. **Update the menu to point to the new pages.**
   - **Appearance → Menus** (or via the Site Editor navigation block).
   - Replace the placeholder links with the real ones.

### Plugins

Install and activate, one at a time. For each, run through its setup wizard.

1. **Rank Math** — choose the "Personal Blog" preset. Connect to Google Search Console when prompted.
2. **UpdraftPlus** — schedule weekly backup to Dropbox or Google Drive. Test the first backup.
3. **Wordfence** — accept the defaults; skip the premium upsells.
4. **Akismet** — get a free API key from akismet.com and paste it in.
5. **Site Kit by Google** — connect to your Google account; enable Analytics and Search Console.

**End-of-session check:** Menus link to real pages. Plugins are installed and configured. A test backup ran successfully.

---

## Session 5 — First posts and going live (60–90 min)

**Goal:** Two or three real blog posts published. AndrewNovick.com redirecting. Site announced.

### Posts

1. **Write or paste in your first post.**
   - **Posts → Add New.**
   - Suggested first post: "Hello from AndyNovick.com" — short intro post explaining the new site, your interest in AI, what readers can expect. Categorize as **Thoughts and Events**.
   - Add a featured image if you have one.

2. **Second post: an AI Discoveries post.**
   - The Windows virtual desktop navigator project would be perfect.
   - Categorize as **AI Discoveries**. Tag with relevant terms.

3. **Third post (optional): a photography or programming post** to seed the other categories.

### Redirect AndrewNovick.com → AndyNovick.com

Since AndrewNovick.com is already on GoDaddy:

1. Go to **My Products → Domains → AndrewNovick.com**.
2. Click **Forwarding** (or **Manage DNS** → **Forwarding**).
3. Forward to `https://andynovick.com`, type **301 (Permanent)**, with **forwarding only** (don't enable masking).
4. Save. Test in an incognito tab — typing `andrewnovick.com` should redirect to `andynovick.com`.

### Final checks

- Visit the live site from a phone. Read a post. Click around. Make sure links work.
- Submit your sitemap to Google Search Console (Rank Math provides the URL).
- Send the link to a friend or two and ask them to look around.

### Announce (when you're ready)

- LinkedIn post.
- Email to people who'd care.
- Optionally update your Blogger and SmugMug profiles to link back to AndyNovick.com.

---

## What we're deliberately leaving for v1.1

- Comments (Akismet is installed, ready to enable when you want).
- Newsletter signup.
- Tuning the ochre and typography after seeing them with real content.

## What we're leaving for v2 (Phase 2)

- Migrating NovickSoftware.com content (target: late fall 2026, before February 2027 renewal).
- Migrating Blogger posts.
- SmugMug decision.

---

## Working tips for sessions with Claude in Chrome

- **Work on staging when you can.** Especially for theme/style changes. The GoDaddy dashboard has a one-click "push staging to live" button when you're happy.
- **Take screenshots as you go.** If something looks off, paste the screenshot into chat and I can suggest fixes.
- **Don't try to do too much in one session.** WordPress has a lot of small decisions; pacing keeps the work fun and the mistakes recoverable.
- **Save before walking away.** WordPress autosaves drafts but the Site Editor doesn't always. Hit Save every 10–15 minutes.

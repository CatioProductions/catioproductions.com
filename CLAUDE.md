# CLAUDE.md

## Project

Static website for catioproductions.com — a brand site for Catio Productions (indie Windows app business + cat rescue funding). Hosted on GitHub Pages.

## Apps

- **Virtual Monitor Manager** — Up to 9 virtual workspaces per physical monitor. Pricing: Free (2), Plus $13.99 (4), Pro $23.49 (9). Microsoft Store: https://apps.microsoft.com/store/detail/9NGZ2X05DZDT?cid=DevShareMCLPCS. Gumroad: https://catiodaddy.gumroad.com/l/ztips.
- **MagnaDesk** — Digital corkboard baked into the Windows wallpaper. Sticky notes, images, drawings, live widgets (Tasks, To-Do, Calendar, OneNote, Mail, plus global Radar + Weather). Microsoft account integration is live; Google account integration (Tasks/Calendar/Gmail) is temporarily switched off until production and labeled "coming soon" sitewide. Radar/Weather are worldwide (no account): data powered by LibreWXR (plain-text credit, no public link yet), forecasts + city search from Open-Meteo, radar basemap from Esri World Street Map, Italian radar tiles credited "Radar-DPC". Microsoft Store: https://apps.microsoft.com/store/detail/9N05BXFN6VRW?cid=DevShareMCLPCS. Pricing TBD.

## Contact

- All Catio Productions email going forward: `catio.productions@outlook.com`. The old `catio.productions.llc@gmail.com` is being dropped — replace it anywhere it still appears.

## Tech Constraints

- Plain HTML5 + CSS only. No frameworks, no build tools, no npm, no JS includes.
- Shared nav and footer are repeated HTML in each file (no templating).
- Must be GitHub Pages compatible — no server-side code.
- CSS lives in a single file: `css/style.css`.

## Voice & Tone

- First person ("I/my"), not corporate ("we/our").
- Honest about being a solo dev with AI co-pilots and cats.
- Warm, personal, authentic — not polished startup copy.

## File Layout

- `index.html` — landing page
- `about.html` — about page (placeholder copy — Reese will rework later)
- `apps/index.html` — app catalog
- `apps/virtual-monitor-manager.html` — full product page (built from user manual)
- `apps/magnadesk.html` — full product page (built from user manual + README + changelog)
- `rescue/index.html` — mission page (placeholder copy — Reese will rework later). Includes an "Affiliates & Partners" section: a `.card-grid` of `.card affiliate-card` placeholder cards plus a "Become an Affiliate" mailto CTA.
- `rescue/donate.html` — donation page
- `css/style.css` — all styles

## When Editing

- Nav and footer are duplicated across all 8 HTML files — update all files when changing nav/footer.
- Demo videos are hosted on YouTube and embedded as responsive `<iframe>`s (styled by the `.video-container iframe` rule in `css/style.css`). Remaining `<div class="video-placeholder">` blocks are sections still awaiting a video — replace each with an `<iframe>` embed when a clip is ready. MagnaDesk's Edit Mode, Quick Paste, and Quick Note Edit videos are already embedded.
- VMM Microsoft Store buttons are live (all three tiers point to the same listing — Free/Plus/Pro are unlocked via in-app purchase). VMM Gumroad link is live. MagnaDesk Microsoft Store link is live.
- VMM support is email-only (catio.productions@outlook.com). The GitHub issues link was dropped because public GitHub issues require a free account, which is friction customers shouldn't have to deal with.
- Reese prefers iterative work: pages will be updated many times before launch, so favor getting overall structure right over polishing every detail. Work one page at a time when asked to update from a manual or doc — don't bleed into other pages without permission.
- Affiliate cards (rescue page) use placeholder `<div class="affiliate-photo">` boxes, not `<img>`, because no image folder exists yet. When real partner logos/photos arrive, create `img/affiliates/` and swap each div for `<img src="../img/affiliates/name.jpg" alt="..." class="affiliate-photo">` (the `.affiliate-photo` CSS class works for both div and img). Affiliate purchase-tracking links are a later marketing stage — see the affiliate-strategy memory.
- Section headlines (`.section h2`) and intro/supporting paragraphs (`.section .container > p`) are centered site-wide. Card body text stays left-aligned for readability.
- Site is tiny (~110 KB of served HTML/CSS) vs the 1 GB GitHub Pages cap — effectively unlimited headroom. Demo videos live on YouTube, so only future images count against it. `.vs/` is gitignored (not published).

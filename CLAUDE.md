# CLAUDE.md

## Project

Static website for catioproductions.com — a brand site for Catio Productions (indie Windows app business + cat rescue funding). Hosted on GitHub Pages.

## Apps

- **Virtual Monitor Manager** — Up to 9 virtual workspaces per physical monitor. Pricing: Free (2), Plus $14.99 (4), Pro $23.49 (9) — confirmed by Reese against Partner Center. The VMM source comments (`LicenseService.cs`, `ILicenseService.cs`) say Pro is $23.99; that's stale, the live price is $23.49. Note: the shipping build has `AppConstants.EnforceWorkspaceTierLimit = false`, so tier limits are unenforced and every user currently gets all 9 workspaces until the 7-day Premium trial ships — the page says so plainly. Microsoft Store: https://apps.microsoft.com/store/detail/9NGZ2X05DZDT?cid=DevShareMCLPCS. Gumroad: https://catiodaddy.gumroad.com/l/ztips.
- **MagnaDesk** — Digital corkboard baked into the Windows wallpaper. Sticky notes, images, documents, drawings, live widgets (Tasks, To-Do, Calendar, OneNote, Mail, plus Local To-Do and global Radar + Weather), and multiple boards. Microsoft account integration is live; Google account integration is temporarily switched off pending Google's review of the requested permissions, labeled "coming soon" sitewide. **The July 2026 OAuth submission requests only `calendar.readonly`, `tasks.readonly`, `userinfo.email`, and `userinfo.profile`** — Keep and Gmail were dropped from it, which keeps MagnaDesk in Google's *sensitive* scope tier rather than *restricted* (`gmail.readonly` is restricted and would trigger a heavier review). Don't reintroduce Keep or Gmail to the privacy policy, the terms, or the product page unless Reese says a new submission includes them; the policy's declared scopes and the site's public claims have to match what's actually requested. In-app wallpaper search (Unsplash/Pexels/Wallhaven APIs) was removed for TOS reasons — the Sources panel now just links out to those sites. Radar/Weather are worldwide (no account): data powered by LibreWXR (plain-text credit, no public link yet), forecasts + city search from Open-Meteo, radar basemap from Esri World Street Map, Italian radar tiles credited "Radar-DPC". Microsoft Store: https://apps.microsoft.com/store/detail/9N05BXFN6VRW?cid=DevShareMCLPCS. Pricing: free download, everything unlocked for 30 days, then a Limited state unless the user buys the one-time Store unlock — **$14.99**, no subscription. The full version restores Quick Paste, Quick Note Edit, the Radar widget, the 11 widget color themes, per-monitor slideshow folders, more than one connected account, and creating new boards. This replaced an older Free/Pro tier model — `USERMANUAL.md`'s "Free vs Pro" section is stale; `CHANGELOG.md` and `CURRENTFEATURESLIST.md` are the accurate sources.

## Mission Framing (pet trust)

The long-term goal — funding and eventually establishing a legal pet trust so the sanctuary cats are provided for permanently — appears on the Rescue page ("The Endgame: A Permanent Sanctuary"), the About page, and the Home hero. Rules for any copy that touches it:

- **It's a goal in progress, not a fact.** Always "working toward establishing," never "we have" or "we operate." No dates, no dollar targets.
- **Lead with what the trust does for the cats**, never what it would contain. Do NOT mention that a pet trust would encompass the house, property, or a vehicle — "your purchase pays for the founder's house" is the optics failure this prevents. (Note: the MagnaDesk and VMM user manuals in the app repos *do* mention the house — do not copy that wording onto the site.)
- **Donation purity is airtight.** Donate page promises 100% to TNR and community cat care; trust costs come from app revenue, never donations. Nothing may imply otherwise, and don't edit the 100% claim.

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
- State limitations plainly on product pages, including awkward or temporary ones — VMM's grid occluding what's under it, multi-monitor still being in active development, workspace tier limits currently unenforced. Reese consistently picks candor over marketing gloss; when a feature is gated or unfinished, say so rather than omitting it.

## File Layout

- `index.html` — landing page
- `about.html` — about page (placeholder copy — Reese will rework later, except the pet-trust paragraph, which is deliberate)
- `apps/index.html` — app catalog
- `apps/virtual-monitor-manager.html` — full product page (built from user manual + changelog)
- `apps/magnadesk.html` — full product page (built from user manual + CURRENTFEATURESLIST + changelog). Has a `#pricing` section that inline tier caveats link to.
- `rescue/index.html` — mission page (placeholder copy — Reese will rework later). Includes "The Endgame: A Permanent Sanctuary" (pet trust — see Mission Framing), a "Fundraisers I Host" section (see below), and an "Affiliates & Partners" section: a `.card-grid` of `.card affiliate-card` placeholder cards plus a "Become an Affiliate" mailto CTA.
- `rescue/donate.html` — donation page
- `privacy/magnadesk.html` — MagnaDesk privacy policy. Required for Google OAuth production verification, which wants the policy on the same domain as the app's homepage. Content is ported from `github.com/CatioProductions/Privacy` (`magnadesk.html`). **Both copies stay live and must be kept in sync** — the old URL `https://catioproductions.github.io/Privacy/magnadesk.html` is still referenced from places we haven't tracked down (Store listing, OAuth consent screen, in-app links), so it can't be retired yet. When the policy text changes, update this file *and* the Privacy repo. Uses the `.legal` styles in `css/style.css` (left-aligned headings/paragraphs, overriding the site-wide centering).
- `terms/magnadesk.html` — MagnaDesk terms of service. Also required for Google OAuth verification (the consent screen has a Terms of Service field separate from the privacy policy one) and also wants to be on-domain. **Single copy — unlike the privacy policy, do NOT mirror it to the Privacy repo**: it's new, so no legacy URL points at it and there's nothing to keep in sync. Same `.legal` styles, same header/footer as `privacy/magnadesk.html`. It links to the privacy policy; the privacy policy deliberately does not link back, since that would mean editing both privacy copies. Legal register ("we/our", "Catio Productions"), not the site's first-person voice — and no mission/rescue copy in it at all, to keep it clear of the Donate page's 100% claim.
- `css/style.css` — all styles

## When Editing

- Nav and footer are duplicated across all 9 HTML files (verified count as of July 2026: `ls *.html */*.html`) — update all files when changing nav/footer. One deliberate exception: `apps/magnadesk.html`'s footer carries extra "MagnaDesk Privacy Policy" and "MagnaDesk Terms" links that the other pages don't have. The legal pages themselves use the standard footer with no self-link.
- Demo videos are hosted on YouTube and embedded as responsive `<iframe>`s (styled by the `.video-container iframe` rule in `css/style.css`). Remaining `<div class="video-placeholder">` blocks are sections still awaiting a video — replace each with an `<iframe>` embed when a clip is ready, and don't add new placeholders for new sections (a placeholder promises a video that's coming). MagnaDesk has four embedded (Overview, Edit Mode, Quick Paste, Quick Note Edit) and three placeholders left; VMM has ten placeholders and no videos yet. The Overview embed also carries a plain "Can't see the video?" text link, since iframe blockers leave an unexplained blank gap.
- **Section backgrounds alternate** down each page: default, then `style="background: var(--color-white);"`, and so on. Inserting a single new `<section class="section">` inverts the parity of everything below it — either insert an even number, fold the content into an existing section as an `<h3>` block, or flip the tail. Verify after editing; two adjacent same-background sections read as a rendering bug.
- VMM Microsoft Store buttons are live (all three tiers point to the same listing — Free/Plus/Pro are unlocked via in-app purchase). VMM Gumroad link is live. MagnaDesk Microsoft Store link is live.
- VMM support is email-only (catio.productions@outlook.com). The GitHub issues link was dropped because public GitHub issues require a free account, which is friction customers shouldn't have to deal with.
- Reese prefers iterative work: pages will be updated many times before launch, so favor getting overall structure right over polishing every detail. Work one page at a time when asked to update from a manual or doc — don't bleed into other pages without permission.
- Affiliate cards (rescue page) use placeholder `<div class="affiliate-photo">` boxes, not `<img>`, because no image folder exists yet. When real partner logos/photos arrive, create `img/affiliates/` and swap each div for `<img src="../img/affiliates/name.jpg" alt="..." class="affiliate-photo">` (the `.affiliate-photo` CSS class works for both div and img). Affiliate purchase-tracking links are a later marketing stage — see the affiliate-strategy memory.
- **"Fundraisers I Host" (rescue page)** is a separate marketing model from affiliates, and the one Reese expects to use more: he hosts a fundraiser for a specific outside rescue and gives a share of app revenue during that campaign. Rules for it:
  - **Funding source must stay stated.** The standalone paragraph under the intro ("That money comes out of app revenue. It's separate from anything you send through my donate page, which still goes 100% to TNR and community cat care.") is load-bearing — without it a dollar figure beside an outside org implies donations were rerouted. Don't fold it back into the intro paragraph or trim it; it's short and separate on purpose so it survives a skim.
  - **Every tally carries an "as of [Month YYYY]"** in the markup (`.fundraiser-tally` — `<strong>` for the amount, `<span>` for the date). A hand-maintained number on a static site goes stale silently, and a stale number without a date is a false claim.
  - **The `[Active now]` badge stays bracketed** until a campaign is genuinely live. Same reasoning as video placeholders: the badge promises a fundraiser running *right now*, which is a stronger claim than a placeholder.
  - Markup reuses `.card`, `.card-grid`, `.affiliate-photo`, and `.affiliate-links`. Only `.fundraiser-featured` (the wide highlighted card), `.fundraiser-badge`, and `.fundraiser-tally` are new. `.fundraiser-featured` is *not* a `.card`, so it's been added to the `.card h3` / `.card p` selectors to keep its colors matching the grid cards beside it.
  - Its responsive override lives in a **trailing** `@media (max-width: 768px)` block at the end of `css/style.css`, not the main one at ~line 569 — the affiliate/fundraiser rules sit after that query, so an override inside it would lose to the base rule on source order.
- Section headlines (`.section h2`) and intro/supporting paragraphs (`.section .container > p`) are centered site-wide. Card body text stays left-aligned for readability.
- App source repos (user manuals, changelogs, feature lists) live outside this repo, under `Desktop\Catio Productions\` — MagnaDesk in `MagnaDesk\`, VMM in `MultiMonitor\` (legacy working title). When updating a product page "from the manual," check the changelog and any feature list too: manuals go stale, and the changelog has repeatedly been the accurate source. Verify prices against Reese, not source comments.
- Site is tiny (~92 KB of served HTML/CSS) vs the 1 GB GitHub Pages cap — effectively unlimited headroom. Demo videos live on YouTube, so only future images count against it. `.vs/` is gitignored (not published).

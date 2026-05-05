# CLAUDE.md

## Project

Static website for catioproductions.com — a brand site for Catio Productions (indie Windows app business + cat rescue funding). Hosted on GitHub Pages.

## Apps

- **Virtual Screen Manager** — Up to 9 virtual workspaces per physical monitor. Pricing: Free (2), Plus $13.99 (4), Pro $23.49 (9). Available on Microsoft Store and Gumroad.
- **MagnaDesk** — Digital corkboard baked into the Windows wallpaper. Sticky notes, images, drawings, live widgets (Tasks, To-Do, Calendar, OneNote, Mail) with Microsoft + Google account integration. Pricing TBD.

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
- `apps/virtual-screen-manager.html` — full product page (built from user manual)
- `apps/magnadesk.html` — full product page (built from user manual + README + changelog)
- `rescue/index.html` — mission page (placeholder copy — Reese will rework later)
- `rescue/donate.html` — donation page
- `css/style.css` — all styles

## When Editing

- Nav and footer are duplicated across all 8 HTML files — update all files when changing nav/footer.
- Video placeholders use `<div class="video-placeholder">` — replace with `<video>` tags when mp4 files are provided.
- Pricing/store/download links are `#` placeholders until real URLs are provided.
- VSM support links are live: GitHub issues (github.com/ReeseDear/MultiMonitor/issues) and email (catio.productions.llc@gmail.com).

# catioproductions.com

Brand site for Catio Productions — an indie Windows app business that funds cat rescue and TNR work.

## About

One person, a few AI co-pilots, and a house full of cats. I build Windows apps and use the proceeds to support trap-neuter-return (TNR) programs for community cats.

## Tech Stack

- Plain HTML5 and CSS — no frameworks, no build tools, no npm
- Mobile responsive using CSS Grid/Flexbox
- Hosted on GitHub Pages (no server-side anything)

## Site Structure

```
index.html                          — Home / landing page
about.html                          — About the person behind it
css/style.css                       — Single shared stylesheet
apps/
  index.html                        — App catalog
  virtual-screen-manager.html       — Product page (full details from user manual)
  magnadesk.html                    — Product page (full details from user manual + docs)
rescue/
  index.html                        — Cat rescue mission + TNR info
  donate.html                       — Donation page (Zeffy/GoFundMe links)
```

## Apps

- **Virtual Screen Manager** — Up to 9 virtual workspaces per physical monitor. Free/Plus ($13.99)/Pro ($23.49) tiers.
- **MagnaDesk** — Digital corkboard baked into the Windows wallpaper. Sticky notes, images, drawings, and live widgets (Tasks, To-Do, Calendar, OneNote, Mail) with Microsoft + Google accounts.

## Local Preview

Open `index.html` directly, or for working nav links:

```
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## TODO

- [ ] Add screen recording videos (mp4) for Virtual Screen Manager
- [ ] Add screen recording videos (mp4) for MagnaDesk
- [ ] Add MagnaDesk pricing and download/store links
- [ ] Replace VSM placeholder store links with real Microsoft Store/Gumroad URLs
- [ ] Replace placeholder donation links with real Zeffy/GoFundMe URLs
- [ ] Rework rescue and about pages with real personal content
- [ ] Add real images/screenshots throughout

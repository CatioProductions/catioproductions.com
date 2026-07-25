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
  virtual-monitor-manager.html      — Product page (full details from user manual)
  magnadesk.html                    — Product page (full details from user manual + docs)
rescue/
  index.html                        — Cat rescue mission + TNR info
  donate.html                       — Donation page (PayPal/GoFundMe links)
```

## Apps

- **Virtual Monitor Manager** — Up to 9 virtual workspaces per physical monitor. Free/Plus ($14.99)/Pro ($23.49) tiers.
- **MagnaDesk** — Digital corkboard baked into the Windows wallpaper. Sticky notes, images, documents, drawings, multiple boards, and live widgets (Tasks, To-Do, Calendar, OneNote, Mail, Local To-Do, Weather, Radar). Microsoft accounts supported; Google coming soon. Free download, everything unlocked for 30 days, then a one-time $14.99 unlock.

## Local Preview

Open `index.html` directly, or for working nav links:

```
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## TODO

- [ ] Add demo videos (YouTube embeds) for Virtual Monitor Manager — ten placeholders, none recorded yet
- [ ] Finish MagnaDesk demo videos — Overview, Edit Mode, Quick Paste, and Quick Note Edit are embedded; canvas items, widgets, and wallpaper engine still use placeholders
- [x] Add MagnaDesk pricing (Store link is live)
- [x] Microsoft Store links live for VMM and MagnaDesk (Partner Center listings)
- [x] Real donation links (PayPal + GoFundMe)
- [ ] Rework rescue and about pages with real personal content — the pet-trust copy is final; the rest is still placeholder
- [ ] Add real images/screenshots throughout
- [ ] Check all pages at ~380px width — several sections have been added without a mobile render check

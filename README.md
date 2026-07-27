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
privacy/
  magnadesk.html                    — MagnaDesk privacy policy (Google OAuth requirement)
terms/
  magnadesk.html                    — MagnaDesk terms of service (Google OAuth requirement)
```

## Privacy Policy

The MagnaDesk privacy policy is hosted in two places, and both must be kept in sync:

- `privacy/magnadesk.html` here → https://catioproductions.com/privacy/magnadesk.html
- `magnadesk.html` in [CatioProductions/Privacy](https://github.com/CatioProductions/Privacy) → https://catioproductions.github.io/Privacy/magnadesk.html

The on-domain copy is the one submitted to Google, since OAuth verification wants the policy on the same domain as the app's homepage. The github.io copy stays live because other places (Store listing, OAuth consent screen, in-app links) still point at it.

## Terms of Service

`terms/magnadesk.html` → https://catioproductions.com/terms/magnadesk.html

Google's OAuth consent screen has a Terms of Service field separate from the privacy policy one, and wants it on the app's own domain. **Unlike the privacy policy, this exists in one place only** — there is no copy in the Privacy repo and no legacy URL pointing anywhere else, so there is nothing to keep in sync. Don't add a second copy.

The terms link to the privacy policy, but not the reverse: adding a link into `privacy/magnadesk.html` would mean editing both privacy copies for no real gain.

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
- [x] Host the MagnaDesk privacy policy on catioproductions.com for Google OAuth verification
- [x] Host the MagnaDesk terms of service on catioproductions.com for Google OAuth verification
- [ ] Paste the terms URL into the Google OAuth consent screen's Terms of Service field (and the Store listing, if it has one)
- [x] Trim the privacy policy's Google scope table to the scopes actually being submitted — Calendar, Tasks, and the two userinfo scopes. Gmail and Keep rows removed, and the "Experimental status" paragraph (which was entirely about Gmail/restricted-scope review) deleted. Done in **both** copies, July 26 2026.
- [ ] Once Google verification passes, update Section 7 of the terms of service — it currently says Google integration is not available.
- [ ] **The two privacy copies have drifted:** the Privacy repo's Section 8 is still "Weather Widget" while the site's is "Weather and Radar Widgets" (commit `fbab611` never propagated). The scope tables now match; the radar text does not.
- [ ] **In-app privacy link is dead.** `MagnaDesk/Views/UserManualWindow.xaml` line 600 points at `https://reesedear.github.io/Privacy/magnadesk.html`, which 404s — the repo is under `CatioProductions`, not `reesedear`. Fix in the MagnaDesk repo.
- [ ] `MagnaDesk/PRIVACY_POLICY.html` in the app repo is a stale third copy (June 2026, no Google scope table). Nothing links to it — delete it or refresh it.

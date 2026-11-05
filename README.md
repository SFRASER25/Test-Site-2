# iTxRe — Website · Option F "Classic"

A traditional professional-firm direction in the spirit of stancilcpa.com and bsktaxadvisors.com: a deep hunter-green header with antique-gold accents (with Navy & Orange, Charcoal & Teal, and Burgundy & Gold as alternates), Source Serif headlines with Lato body text, a full-width Atlanta skyline photo hero with an overlapping stats panel, white service cards with "Learn more" links, audience cards, an offset photo layout, an industries grid, and a "Visit our Roswell office" map card.

**Photos** (in `assets/img/`) are from Unsplash under the free Unsplash License, which allows commercial use without attribution: `hero-atlanta.jpg` (unsplash.com/photos/9fxD3UW_C1I), `atlanta-autumn.jpg` (unsplash.com/photos/9Ij_NNfP2io), and `client-meeting.jpg` (unsplash.com/photos/M5k978V3qBc). Swap in the firm's own photography when it's available; real team and office photos will make the biggest difference.

Marketing site for **iTxRe**, an income tax consulting, planning, and compliance firm at 120 Bulloch Avenue, Roswell, GA.

It's plain HTML, CSS, and JavaScript, so there's no build step, framework, or `npm install`. It runs on any static host, including GitHub Pages, Netlify, Cloudflare Pages, and Vercel.

## Pages

| File | Purpose |
| --- | --- |
| `index.html` | Home: photo hero with stats panel, about split with photo, eight service cards, who-we-serve cards, process band, industries grid, why-iTxRe checklist, team, FAQ, office map card, CTA |
| `services.html` | Solutions for business owners and individuals, with a sticky jump nav |
| `industries.html` | Industries hub with 12 industry sections (problem → solution) |
| `about.html` | Firm story, approach, filterable team grid, security |
| `staffing.html` | Staffing & Recruiting practice |
| `client-center.html` | Portal, upload, and payment links, plus auto-updating federal tax deadlines and a document checklist |
| `contact.html` | Consultation form, contact cards, map |
| `privacy.html` | Privacy policy (template, to be reviewed by counsel) |
| `404.html` | Not-found page |

```
assets/
  css/styles.css   Design system and all components
  js/site.js       Shared header, mega menus, footer, and interactions
  img/favicon.svg
```

## Editing the site

**Firm details, menus, and industries are set in one place.** Open `assets/js/site.js`:

- `SITE` holds the phone, email, address, hours, and the **client portal, upload, and payment URLs**.
- `MENU` holds the content of the mega menus (Solutions, Our Firm, Client Center).
- `INDUSTRIES` holds the 12 industries that feed the Industries mega menu, the homepage grid, and the footer.

The header and footer render from these on every page, so a change there updates the whole site.

**Color palettes** are defined at the bottom of `assets/css/styles.css`. Hunter & Gold (green `#1f3d33`, gold `#9c6b25`) is the default; Navy & Orange, Charcoal & Teal, and Burgundy & Gold are alternates. A floating "Colors" switcher in the bottom-left corner lets you preview them live. The choice is remembered, and `?palette=navy` (or `charcoal`, `burgundy`) in the URL also works. To lock in a palette for launch, set `showPalettePicker: false` in `SITE` (`assets/js/site.js`) and copy that palette's values into the plain `:root` palette block. The fonts are Source Serif 4 (headlines) and Lato (body), both from Google Fonts.

**Team headshots:** add the photos to `assets/img/team/`. In `about.html` (and the preview on `index.html`), replace the monogram, for example:

```html
<div class="person__photo"><img src="assets/img/team/seth-peabody.jpg" alt="T. Seth Peabody"></div>
```

## Preview locally

From this folder, run either command:

```bash
python3 -m http.server 8000
```

```bash
ruby -run -e httpd . -p 8000
```

Then open http://localhost:8000.

## Deploy with GitHub Pages

1. Create a repository and push these files to the `main` branch, with `index.html` at the root.
2. In the repo, go to **Settings → Pages → Build and deployment**, set **Source: Deploy from a branch**, then choose **Branch: main** and **/ (root)**.
3. For a custom domain, add a file named `CNAME` containing `www.itxre.com` and point DNS at GitHub Pages.

`.nojekyll` is included so GitHub serves the files as-is.

## Before launch

- [ ] Set the real **Client Portal**, **Upload Files**, and **Pay Online** URLs in `SITE` (they are `#` placeholders now)
- [ ] Create a free form at formspree.io and replace `YOUR_FORM_ID` in `contact.html`. Until then, the form only shows its success message and sends nothing.
- [ ] Pick the final color palette, then set `showPalettePicker: false` in `SITE`
- [ ] Confirm **office hours** in `SITE.hours`. The current value is a placeholder.
- [ ] Add the real **LinkedIn** URL in `SITE.linkedin`
- [ ] Confirm the expanded service lines (entity strategy, multi-state, equity compensation, and so on) and the 12 industries match what the firm wants to promote
- [ ] Add team headshots and confirm every name and title
- [ ] Have counsel review `privacy.html` and the Circular 230 footer text
- [ ] Update `sitemap.xml` if the domain is not `www.itxre.com`

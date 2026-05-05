# Morning Crumbs — Website

A simple, free, brand-matched website for your sourdough + linen business. Single page that scrolls through Home, About, What I Make, and Order sections.

---

## What's in this folder

```
index.html      ← the website
styles.css      ← all the styling (brand colors, fonts, layout)
README.md       ← you are here
assets/         ← put your logo + product photos in here
  morning-crumbs-logo-blue.png   (the blue version of your logo)
```

You can preview the site right now by **double-clicking `index.html`** — it'll open in your browser.

---

## Quick personalization checklist (5 things to change)

Open `index.html` in any text editor (TextEdit on Mac, Notepad on PC, or VS Code) and find/replace:

1. **`YOUR_HANDLE`** → your Instagram username (search appears twice)
2. **`YOUR_PAGE`** → your Facebook page URL slug
3. **`hello@morningcrumbs.com`** → your real email (search appears twice)
4. **`YOUR_FORM_ID`** → your Formspree form ID (see step below)
5. **Drop your logo** into a folder called `assets/` named `morning-crumbs-logo-blue.png`

That's it — the site will work with all your real info.

---

## Add your logo (1 minute)

1. Make a folder named `assets` next to `index.html`.
2. Save your blue logo as `morning-crumbs-logo-blue.png` inside that folder.

Until you do this, the hero section automatically falls back to a styled text version of your logo using the matching script font, so the site still looks complete.

---

## Add product photos later (2 minutes)

The placeholder boxes in "What I Make" are sized 1:1 (square) and the About photo is 4:5 (portrait). When you have photos:

1. Save them in the `assets/` folder.
2. Recommended names: `loaf.jpg`, `bread-bag.jpg`, `banneton.jpg`, `jar-cover.jpg`, `about-photo.jpg`.
3. In `index.html`, replace each `<div class="photo-placeholder">...</div>` block with `<img src="assets/loaf.jpg" alt="Sourdough loaf" />`.

Photo sizing tips: aim for ~1200px on the longest side, JPG format, under 300 KB each (use [squoosh.app](https://squoosh.app) for free compression).

---

## Wire up the contact form (5 minutes — uses Formspree free tier)

The form needs a backend service to actually email you submissions. **Formspree** is free for up to 50 submissions/month — plenty to start.

1. Go to **[formspree.io](https://formspree.io)** and sign up with your email.
2. Click **"+ New Form"**, give it a name like "Morning Crumbs Orders", and use your real email.
3. Formspree will give you an endpoint URL like `https://formspree.io/f/abcd1234`.
4. In `index.html`, find `YOUR_FORM_ID` and replace with the part after `/f/` (e.g. `abcd1234`).

Submissions will land in your inbox. First time someone fills out the form, Formspree will email you to verify it's really you.

---

## Host it for free on GitHub Pages

1. Make a [GitHub account](https://github.com) if you don't have one.
2. Create a new **public** repository named `morning-crumbs` (or whatever — name doesn't matter much).
3. Upload `index.html`, `styles.css`, and your `assets/` folder using the "Add file → Upload files" button.
4. Go to the repo's **Settings → Pages**.
5. Under "Source", choose **Deploy from a branch**, pick `main` branch + `/ (root)` folder, and click **Save**.
6. Wait ~1 minute, then refresh. Your site will be live at `https://YOUR-USERNAME.github.io/morning-crumbs/`.

### Want a custom domain like `morningcrumbs.com`?

You can buy one from Namecheap or Porkbun (~$10/yr) and point it at GitHub Pages — totally free hosting, just the domain cost. GitHub has a [step-by-step guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

---

## Even easier alternative: Netlify

If GitHub feels intimidating, **[Netlify](https://app.netlify.com/drop)** is a one-step option:

1. Zip up this whole folder (`index.html`, `styles.css`, `assets/`).
2. Drag the zip onto **netlify.com/drop** — it goes live instantly at a free `*.netlify.app` URL.
3. Bonus: Netlify has **built-in form handling** (100 submissions/month free), so you can skip Formspree. To use it, change the form opening tag in `index.html` to:
   ```html
   <form class="contact-form" name="orders" method="POST" data-netlify="true">
     <input type="hidden" name="form-name" value="orders" />
   ```
   ...and remove the `action="https://formspree.io/..."` part.

Form submissions show up in your Netlify dashboard, and you'll get an email when one comes in.

---

## Brand notes

- **Colors used:** `#d2b48c` (tan), `#668498` (blue), `#f2eadf` (cream)
- **Script font:** [Sacramento](https://fonts.google.com/specimen/Sacramento) — closest free match to Canva's "Vintage Goods". If you'd like a different vibe, [Pinyon Script](https://fonts.google.com/specimen/Pinyon+Script) and [Allura](https://fonts.google.com/specimen/Allura) are also lovely alternatives — swap the font name in `styles.css` (`--font-script` variable).
- **Body fonts:** Cormorant Garamond (serif headings) + Lato (clean body text).

Both are loaded for free from Google Fonts — no licensing fees, no install needed.

---

## Updating the site later

Open `index.html` and edit the text directly — anything between `<p>...</p>` or `<h2>...</h2>` tags is plain content. Save the file, refresh GitHub/Netlify, and you're live again in under a minute.

If anything ever breaks or you want to add a section (gallery, testimonials, a real shop), just ask!

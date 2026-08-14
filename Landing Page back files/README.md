# Puppy Shopping List — deploy guide

This is a static site: `index.html` plus an `images/` folder (your actual cover photo and heart logo, pulled from the guide and optimised for the web). No build step, no dependencies. That makes it the easiest possible thing to host on GitHub + Vercel.

**Keep the folder structure exactly as it is** — `index.html` sits next to an `images/` folder containing `hero-schnauzer.webp` and `heart-logo.webp`. If those move, the images on the page will break.

## 1. Create the GitHub repo

1. Go to https://github.com/new
2. Repository name: `puppy-shopping-list` (or whatever you like — it'll become part of your default Vercel URL)
3. Keep it **Public**, don't add a README/gitignore/license (we already have the file)
4. Click **Create repository**
5. On the next page, use the "uploading an existing file" link → drag in **the whole folder** (`index.html` and the `images` folder together) → **Commit changes**
   - GitHub's web uploader accepts drag-and-drop of a folder — drop the `puppy-shopping-list` folder in one go so the `images/` subfolder comes with it.

## 2. Connect it to Vercel

1. Go to https://vercel.com/new
2. Choose **Import Git Repository**, sign in with the same GitHub account, and select `puppy-shopping-list`
3. Vercel will auto-detect it as a static site — leave all settings as default
4. Click **Deploy**

That's it — Vercel gives you a live URL like `puppy-shopping-list.vercel.app` within about 30 seconds.

## 3. (Optional) Use your own domain / a nicer path

In the Vercel project → **Settings → Domains**, you can either:
- Add a subdomain of sedgysminime.com (e.g. `shop.sedgysminime.com`) if you want it to feel like part of your main site, or
- Just keep the free `*.vercel.app` link and use that in your PDF/QR code.

## 4. Updating it later

Any time you want to change an item, price, or add a new one: edit the `ITEMS` object near the bottom of `index.html` (either directly on github.com in the browser, or re-upload the file) — Vercel redeploys automatically on every commit.

## What's inside

- Pure HTML/CSS/JS, no framework, no build tools
- Fonts loaded from Google Fonts (Fraunces + Public Sans, matching your other SedgysMiniMe materials)
- A "tick off as you shop" checkbox on each item (saved locally in the visitor's own browser — nothing is sent anywhere or shared between visitors)
- Every product card is tagged **Amazon** or **Other retailer** and carries the correct `rel="sponsored"` attribute on Amazon links, plus an Associates disclosure in the footer (required by Amazon's operating agreement)

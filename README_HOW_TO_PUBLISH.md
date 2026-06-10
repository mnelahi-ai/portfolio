# Mashuk Elahi — Personal Portfolio (24/7 Digital Résumé)

A single self-contained website that acts as your always-on digital résumé. You link it
from your **LinkedIn → Contact info → Website** field, and anyone can open it any time.

## What's in this folder

```
Portfolio/
├── index.html                     ← the whole website (HTML + CSS + JS in one file)
├── assets/
│   └── Mashuk_Elahi_Resume.pdf    ← the "Download Résumé" button points here
└── README_HOW_TO_PUBLISH.md       ← this guide
```

Everything is built from your own source files in the Development folder — your
Rev2 résumé, cover letter, LinkedIn profile copy, and the four LinkedIn article topics.
No company-confidential drawings or client assets are included; it is 100% your own
professional record.

## Preview it now (no internet needed)

Double-click `index.html`. It opens in your browser straight from your computer.
That is fine for checking it — but a `file:///...` link is **only on your machine**, so
nobody else can see it. To make it a real 24/7 link, publish it free with GitHub Pages.

---

## Publish free, 24/7 — GitHub Pages (recommended)

GitHub Pages hosts static sites for free with no server to maintain. Your address will be
`https://<your-username>.github.io/portfolio/`.

### Option A — Easiest (GitHub website, no tools to install)

1. Create a free account at https://github.com (skip if you already have one).
2. Click **New repository**. Name it `portfolio`. Set it **Public**. Click **Create**.
3. On the repo page click **Add file → Upload files**.
4. Drag in `index.html` **and** the whole `assets` folder (keep the structure). Click **Commit changes**.
5. Go to **Settings → Pages**. Under *Build and deployment → Source* choose **Deploy from a branch**,
   pick branch **main** and folder **/ (root)**, click **Save**.
6. Wait ~1 minute, refresh. GitHub shows: *"Your site is live at https://<username>.github.io/portfolio/"*.
7. Copy that URL.

### Option B — Using VS Code + Git (better for future edits)

1. Install **Visual Studio Code** (https://code.visualstudio.com) and **Git** (https://git-scm.com).
2. In VS Code: **File → Open Folder →** select this `Portfolio` folder.
3. Open the terminal (**Terminal → New Terminal**) and run:
   ```bash
   git init
   git add .
   git commit -m "Personal portfolio site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/portfolio.git
   git push -u origin main
   ```
4. Turn on Pages exactly as in Option A, steps 5–7.
5. To update later: edit `index.html` in VS Code, then run
   `git add . && git commit -m "update" && git push`. The live site refreshes automatically.

> Tip: the VS Code extension **Live Server** (by Ritwick Dey) lets you preview edits instantly
> in the browser while you work.

---

## Link it from LinkedIn

1. LinkedIn → **Me → View Profile → Edit (pencil on the intro card) → Contact info**.
2. Under **Website**, add your Pages URL, type **Portfolio**, **Save**.
3. Optional: also drop the link in your **About** section and **Featured** section so it's
   visible without opening contact info.

---

## Want a cleaner address?

- `https://<username>.github.io` (no `/portfolio`): name the repo exactly
  `<username>.github.io` instead of `portfolio`.
- Custom domain (e.g. `mashukelahi.com`): buy a domain, then **Settings → Pages → Custom domain**.
  Other free hosts that work the same way: **Netlify** and **Cloudflare Pages**
  (drag-and-drop this folder, get an instant URL).

---

## How this was built

- **Source material**: your `Mashuk_Elahi_Resume_Rev2`, `_Cover_Letter_Rev2`,
  `_LinkedIn_Profile_Rev2` documents and the `Article for Linkdn` topics.
- **Design**: reuses the visual language of your Marine_Projects banner (dark navy,
  blue→amber gradient, particle network background, animated counters, glass cards) so
  your résumé site and LinkedIn banner look like one brand.
- **Tooling**: written as plain **HTML / CSS / JavaScript** (no build step, no frameworks),
  authored with **AI-assisted engineering (Claude)**. You edit it in **VS Code** and host it on
  **GitHub Pages** — all free.

## Updating content

Open `index.html` in VS Code. The page is organised in clearly commented sections
(`HERO`, `ABOUT`, `ACHIEVEMENTS`, `EXPERIENCE`, `EXPERTISE`, `EMERGING`, `EDUCATION`,
`INSIGHTS`, `CONTACT`). Change the text in the matching block, save, and re-publish.

To swap the downloadable résumé, replace `assets/Mashuk_Elahi_Resume.pdf` with a new file
of the same name.

> **Before going live, set your real links:** the LinkedIn URL is set to
> `https://www.linkedin.com/in/mashukelahi` and the four article cards point to your LinkedIn
> articles page. If your handle differs, search the file for `mashukelahi` and update it.

# Build A Website That Makes You Money

A free, plain-English, dyslexia-friendly walkthrough of every step to get a website live and earning. Brought to you by **WRENTECH** ([wrentech.net](https://wrentech.net)) — Erwin, Tennessee.

> No ads. No affiliate links. No upsells. Every tool was picked because it's the best, not because it pays us.

This repo is a **single HTML file**. You can deploy it to the live internet in about 10 minutes, even if you've never touched code. Below is the exact, dumbed-down path.

---

## What's in this folder

- `index.html` — the whole guide. Self-contained. CSS, JS, fonts, all baked in. No build step.
- `README.md` — this file. How to put it on the internet.

You don't need anything else. No Node, no npm, no nothing.

---

## Launch it free in 10 minutes (Cursor → GitHub → Vercel)

This is the easiest path. You'll end up with a live URL you can share with anyone, on the world's best free hosting, with auto-deploys every time you make a change.

### Step 1 — Open the folder in Cursor

If you don't have Cursor yet:
- Download from [cursor.com](https://cursor.com) (free)
- Install like any other app
- Open it and sign up (free tier is plenty)

Then:
- **Cursor → File → Open Folder**
- Pick this folder (the one with `index.html` and this `README.md` inside)

You should now see both files in the left sidebar.

### Step 2 — Preview it locally first

Right-click `index.html` in Cursor's sidebar → **"Reveal in Finder"** (Mac) or **"Reveal in File Explorer"** (Windows). Double-click the file. It opens in your browser. That's the guide running on your computer.

If anything looks broken, fix it in Cursor before pushing it to the world.

### Step 3 — Make it a Git repository

In Cursor's terminal (open with **Ctrl+\`** on Windows or **Cmd+\`** on Mac), run:

```bash
git init
git add .
git commit -m "first commit: WRENTECH guide v1"
```

What this did:
- `git init` → tells your folder "you are now a Git project"
- `git add .` → stages every file in the folder for the next save-point
- `git commit -m "..."` → takes the snapshot

### Step 4 — Push it to GitHub

Go to [github.com/new](https://github.com/new) and create a new repository:
- **Repository name:** `wrentech-guide` (or whatever you want)
- **Public** (so people can see and fork it)
- **DO NOT** check "Add a README" or "Add .gitignore" — you already have your files
- Click **Create repository**

GitHub will show you a page with commands. Copy the **"…or push an existing repository from the command line"** block. It looks like this (replace `YOU` with your actual username):

```bash
git remote add origin https://github.com/YOU/wrentech-guide.git
git branch -M main
git push -u origin main
```

Paste that into Cursor's terminal. Hit enter. GitHub may ask you to log in — follow the prompts.

Your code is now on GitHub. Refresh github.com/YOU/wrentech-guide to see it.

### Step 5 — Deploy to Vercel (FREE, instant, auto-deploy)

- Go to [vercel.com/new](https://vercel.com/new)
- Sign in with your **GitHub account** (no separate password)
- It'll show your repos — click **Import** next to `wrentech-guide`
- Leave every setting on default
- Click **Deploy**

Wait about 60 seconds. Vercel gives you a URL like `wrentech-guide-abc123.vercel.app`. Click it. Your guide is live.

**Auto-deploys:** From now on, every time you save a change in Cursor and run:

```bash
git add .
git commit -m "what I changed"
git push
```

…Vercel rebuilds your live site in about 30 seconds. No upload, no FTP, no nothing.

---

## Alternative: deploy to Railway

[Railway](https://railway.app) also works and you said you have an account. Vercel is easier for a static HTML site like this one (it's free forever, no usage caps for a single file). Railway is better when you have a real backend (a database, an API, code that runs server-side).

If you still want to use Railway:

- Go to [railway.app/new](https://railway.app/new)
- Click **"Deploy from GitHub repo"**
- Pick your `wrentech-guide` repo
- Railway will auto-detect that it's a static site
- Add a **Static site** service if it doesn't auto-pick one
- Set the public root to `/` (the folder with `index.html`)
- Deploy

Railway gives you a free $5/month of usage. For a static HTML file that's almost never hitting compute, you'll likely stay well under that. But Vercel is genuinely free for this kind of site, so unless you specifically need Railway, use Vercel.

**Quick comparison:**

| | Vercel | Railway |
|---|---|---|
| Best for | Static sites, simple apps | Apps with backends, databases |
| Free tier | Generous, forever | $5/mo of free credit |
| Speed | Fastest globally | Fast |
| Auto-deploy from Git | Yes | Yes |
| Custom domain | Free, easy | Free, easy |

For THIS guide → **use Vercel**.

---

## Add your own domain (optional, ~$10/year)

Once it's deployed:

1. Buy a domain at [Porkbun](https://porkbun.com) or [Cloudflare](https://cloudflare.com) (~$10/year). **Skip GoDaddy**, the upsells are aggressive.
2. In Vercel: **Project → Settings → Domains → Add**
3. Type your domain. Vercel shows you DNS records to add (looks like `A 76.76.21.21` and `CNAME cname.vercel-dns.com`).
4. In Porkbun/Cloudflare: **DNS Records → Add Record** for each one
5. Wait 5 minutes to 24 hours. Vercel emails you when it's verified.
6. Done. Your guide is at `yourdomain.com`.

---

## Customize the guide for your own brand

This guide is built so you can fork it and rebrand it. The whole thing is one HTML file with all the styles in a `<style>` block at the top. To rebrand:

### Change colors

Search `index.html` for `--wt-coral` to find the WRENTECH coral. Near the top of the `<style>` block you'll see:

```css
--wt-deep:    #0E2419;       /* forest bg */
--wt-coral:   #E89870;       /* primary accent */
--wt-cream:   #F5E6D8;       /* text on dark */
```

Change those hex codes to your brand colors and the whole guide updates.

### Change fonts

Near the top of the `<head>`, find:

```html
<link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible..." rel="stylesheet">
```

Replace with any Google Fonts link. Then update the `font-family` references in the CSS to match.

### Change the WRENTECH branding to yours

Search `index.html` for `WRENTECH` and replace with your brand name. Search for `wrentech.net` and replace with your URL. That's it — you've got a co-branded version.

### Change the words

Every section is wrapped in `<section class="module" id="...">`. Find the section you want to edit, change the text, save. If you've got the auto-deploy setup, your live site updates in 30 seconds.

**Pro tip:** Open the file in Cursor and hit **Cmd/Ctrl+L**. Ask the AI: *"Change all instances of 'Carrd' to 'Webflow' and update the recommendations accordingly."* It'll do bulk rewrites in seconds.

---

## What makes this work / why it's free forever

- **Single HTML file** → no build step, no Node version drift, no npm vulnerabilities. It'll work in 2035.
- **Google Fonts hosted by Google** → free, fast, cached globally.
- **No tracking, no analytics, no JS frameworks** → loads in under a second, works on slow phones.
- **Vercel free tier** → covers up to 100GB bandwidth/month. You'd need ~50,000 visitors before paying anything.
- **GitHub free** → unlimited public repos.
- **Domain is the only paid piece** → ~$10/year if you want a custom URL. Optional.

Total cost to run this for a year: **$0–$10**.

---

## Sharing it

If you want to fork-and-share:
- Each person clones the repo
- Each person deploys their own Vercel
- Each person owns their own copy
- Updates to the original can be pulled in with `git pull`

If you want one URL that thousands of people read:
- Just deploy once
- Share the Vercel URL or your custom domain
- All traffic hits one site

---

## License

Released free for anyone to use, fork, modify, or share — commercially or personally. Just don't remove the WRENTECH credit in the footer if you're republishing it more or less as-is.

If you significantly rebuild it as your own thing, no attribution needed. Make it yours.

---

## Credit / source

Built by **Jennifer Leigh West** — WRENTECH LLC, Erwin TN.
[wrentech.net](https://wrentech.net) · the West Method™

If this guide helped you ship a site, the best thank-you is sending it to one other person who needs it.

---

## Troubleshooting

**"git: command not found"** in Cursor's terminal
→ Install Git: [git-scm.com/downloads](https://git-scm.com/downloads). Restart Cursor after install.

**"Permission denied (publickey)"** when pushing to GitHub
→ You need to log in. In Cursor's terminal, run `gh auth login` (if you have the GitHub CLI), OR use the **GitHub Desktop** app at [desktop.github.com](https://desktop.github.com) to push instead.

**Vercel showing the wrong page / 404**
→ Make sure `index.html` is in the root of the repo, not in a subfolder. Vercel looks for `index.html` at the top level.

**The site loads but fonts look wrong / generic**
→ Your browser blocked the Google Fonts request. Check your ad blocker. The page still works, it just falls back to system fonts.

**I want to edit but I'm scared of breaking it**
→ Before any change, run `git commit -m "before I touched it"`. You can always roll back with `git reset --hard HEAD~1`.

---

*Ship the imperfect thing now. Refine in public. — the West Method™*

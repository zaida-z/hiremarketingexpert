# Deploying The Margin Notes

## Contents
- index.html   — the entire site (already renamed, OG tags + favicon added)
- CNAME        — hiremarketingexpert.com (DELETE this file if deploying to a different domain or to username.github.io)

## Before you push — 3 placeholders
1. LinkedIn URL: search index.html for `https://www.linkedin.com` and paste your profile URL.
2. Act 6 stats: search for `data-count` (3 places) and set your real numbers.
3. OG image (optional, recommended): add `og-image.png` (1200x630) to the repo and add
   `<meta property="og:image" content="https://hiremarketingexpert.com/og-image.png">` in <head>.

## Deploy — new repo
git init margin-notes && cd margin-notes
# copy index.html and CNAME here
git add . && git commit -m "The Margin Notes v1"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/margin-notes.git
git push -u origin main
# GitHub → repo → Settings → Pages → Source: main / root → Save

## Deploy — replacing the existing site
If hiremarketingexpert.com already serves your v3 repo, just replace that repo's
index.html with this one, keep the existing CNAME, commit, push. Done.
(Tip: keep v3 on a branch — `git checkout -b v3-brand-lab` before overwriting.)

## Domain (already configured from your previous deploy — verify only)
- GitHub → Settings → Pages → Custom domain: hiremarketingexpert.com → Save
- Tick "Enforce HTTPS" once the cert issues (can take ~15 min)
- DNS should already have: 4 A records → 185.199.108/109/110/111.153,
  and www CNAME → YOUR-USERNAME.github.io

## What needs NO setup
No build step, no npm, no framework. GSAP + fonts load from public CDNs.
The site is one file; hosting it anywhere that serves HTML works.

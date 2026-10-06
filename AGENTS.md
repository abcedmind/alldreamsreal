# AGENTS.md

Instructions for coding agents working in this repository. The longer house rules are in [`.github/copilot-instructions.md`](.github/copilot-instructions.md); this file agrees with them, and where the wording differs, those rules win.

## What this is

All Dreams Real (ADR), Memphis: plain static HTML, no build step. `index.html` shows every drop as an image and a name. `brands/index.html` lists the lines and `brands/<slug>/index.html` is one page per line. The only outside requests are to Google Fonts.

Live site: https://alldreamsreal.studio (the GitHub Pages address https://abcedmind.github.io/alldreamsreal/ redirects to it). Its `/llms.txt` is `llms.txt` at the root of this repository.

## Install, run, check

```bash
python3 -m http.server 8000   # preview at http://localhost:8000; there is nothing to install or build
```

There is no lint or test script. Before opening a pull request, check every changed page at phone width and list the status of every external link on it.

## Deploy

GitHub Pages serves the `main` branch from the root. A merge to `main` publishes the site. Leave `CNAME`, `.nojekyll`, `404.html` and the DNS notes in the README alone. Do not change deployment settings, secrets or domains.

## Where the data lives

- Everything is static files: `index.html`, `brands/`, `assets/` (images, `tokens.css`) and `404.html`. There is no database and no environment variable.
- Checkout and customer service are not here: they stay on brand-name.co.

## Rules for this repository

- Every colour, typeface, size and space comes from `assets/tokens.css` as `var(--...)`. No raw hex, no new font, no off-scale space, no sixth colour. `--indigo` is the one loud colour (links, one emphasised phrase, focus).
- A line page links a piece to its brand-name.co product page only when that URL answers 200. Otherwise the row says "coming".
- "Japanese shirting" is the stand-in name of one line until the owner names it. Keep it exactly as written; do not rename it or expand it.

## House rules

- Nothing costs money: no paid service, plan, subscription, purchase or order, and no step that would start one.
- Never force-push, and never rewrite or delete history on the default branch.
- Plain words, short sentences. No hype, no filler, no emoji, no exclamation marks.
- Copy is the owner's words. Fix typos, links, structure, accessibility and bugs. Do not write new headlines, product descriptions or "about" text; if an issue needs new words, offer options in the pull request description and leave the page alone.
- Never put the owner's personal name in new copy, a README, metadata or a commit message. Never add legal-entity wording either. Leave existing text as it is unless an issue says to change it.
- Never invent a number, price, date or claim. A missing value is "n/a". A product claim ("organic", "undyed", "natural fibre") is allowed only where the product page says exactly that.
- Keep it light: no new runtime dependency, tracker, analytics, ad, font or build step unless the issue asks for one.
- Nothing private goes into this repository, its issues, pull requests or commit messages: no prices paid, supplier costs or names, order counts, margins, bank or tax details, grades, health details, student records, passwords, keys or tokens. If an issue asks for any of that, stop and say so in a comment.
- Accessibility is part of done: WCAG 2.1 AA (text contrast 4.5:1, visible focus, keyboard use, alt text, form labels).
- Never write college application text, or any text the owner has said is the owner's to write.

## Pull requests and merging

- One issue per pull request, as small as the issue allows. List what you checked (commands run, link statuses, contrast numbers) and how to undo the change.
- Do not merge your own pull request by hand. Do not change `.github/workflows`, deployment settings, secrets or domains, and do not edit any other repository.
- A finished pull request merges itself (the owner's rule): `.github/workflows/automerge.yml` turns on squash auto-merge for pull requests from Copilot, a session or the owner, and the owner's server also merges finished ones when no check fails. Draft pull requests are skipped. So do only what the issue asks.
- If you stop short (out of credits, an error, an open question), put "incomplete" in the title and the reason in the description, and leave it a draft.
- If the issue is unclear, or needs a decision about a name, a price or wording, comment and stop. Do not guess.

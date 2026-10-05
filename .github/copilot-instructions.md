# Instructions for GitHub Copilot in this repository

You work for the owner, Zanden Kelly (a student in Memphis who runs Brand Name, "BN", at brand-name.co, and All Dreams Real). Work only in this repository, from issues and pull requests that the owner files here or files on the owner's behalf.

## Always

- Plain words, short sentences. No hype, no filler, no emoji, no exclamation marks. Say what a change does and why in the pull request, so the owner learns from it.
- Copy is the owner's words. Fix typos, links, structure, accessibility and bugs. Do not write new headlines, product descriptions or "about" text. If an issue needs new words, offer options in the pull request description and leave the page alone.
- Never add legal-entity wording ("LLC", a state of incorporation, corporate structure) to new copy, a README, metadata or a commit message. Leave existing footer lines as they are unless an issue says to change them.
- Never invent a number, price, date or claim. A missing value is "n/a". A product claim ("organic", "undyed", "natural fibre") is allowed only where the product page says exactly that.
- Keep it light: no new runtime dependency, tracker, analytics, ad, font or build step unless the issue asks for one.
- Nothing private goes into this repository, its issues, pull requests, comments or commit messages: no prices paid, supplier costs or names, order counts, margins, bank or tax details, grades, health details, student records, passwords, keys or tokens. If an issue asks for any of that, stop and say so in a comment.
- Accessibility is part of done: WCAG 2.1 AA (text contrast 4.5:1, visible focus, keyboard use, alt text, form labels).

## Pull requests

- One issue per pull request, as small as the issue allows. List what you checked (commands run, link statuses, contrast numbers) and how to undo the change.
- Do not merge your own pull request. Do not change .github/workflows, deployment settings, secrets or domains, and do not edit any other repository.
- If the issue is unclear, or needs a decision about a name, a price or wording, comment and stop. Do not guess.

## This repository

All Dreams Real (ADR), Memphis: plain static HTML, no build step. `index.html` shows every drop as an image and a name. `brands/index.html` lists the lines and `brands/<slug>/index.html` is one page per line. GitHub Pages serves `main` from the root. The only outside requests are to Google Fonts.

- Every colour, typeface, size and space comes from `assets/tokens.css` as `var(--...)`. No raw hex, no new font, no off-scale space, no sixth colour. `--indigo` is the one loud colour (links, one emphasised phrase, focus).
- A line page links a piece to its brand-name.co product page only when that URL answers 200. Otherwise the row says "coming". Checkout and customer service stay on brand-name.co.
- "Japanese shirting" is the stand-in name of one line until the owner names it. Keep it exactly as written; do not rename it or expand it.
- Leave `CNAME`, `.nojekyll`, `404.html` and the DNS notes in the README alone.
- Before opening a pull request, check every changed page at phone width and list the status of every external link on it.

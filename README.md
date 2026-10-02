# alldreamsreal

This is the website of All Dreams Real, LLC, in Memphis, Tennessee. It is plain static HTML. It has no build step, and its only outside requests are to Google Fonts.

- `index.html` is the page: every drop, shown as its image and its name.
- `404.html` is the PAGE UNAVAILABLE page. GitHub Pages serves it at any address that does not exist.
- `brands/` holds one page per line (`brands/<slug>/index.html`) and an index of the lines (`brands/index.html`). Each page links its pieces to brand-name.co, where checkout runs; customer service is brand-name.co's contact form.
- `assets/` holds the images. Each work's tile uses that work's own preview image. The instrumental (`assets/adr-instrumental.mp3`) is optional: the page shows its sound button only when the file is present.

It is served by GitHub Pages from `main`, at the root.

## Pointing alldreamsreal.studio here (Name.com)

0. Do this first. On GitHub, open account Settings → Pages → Add a domain, and enter `alldreamsreal.studio`. Add the TXT record GitHub shows (host `_github-pages-challenge-abcedmind`) at Name.com, then press Verify. A verified domain cannot be claimed by another account while its DNS points at GitHub.
1. Go to Name.com: MY DOMAINS → alldreamsreal.studio → Manage DNS Records. Delete the parking records and any default `*` or `www` record. Do not add a `*` (wildcard) record: GitHub warns that wildcards put the domain at risk of takeover.
2. Add these records. At Name.com the root domain's **Host field is left blank** (the `@` below means "blank"). TTL stays at the default, 300.

| Type | Host | Answer |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | abcedmind.github.io |

3. Check that it resolves: `dig +short alldreamsreal.studio` should list the four 185.199.x.153 addresses.
4. Only then add a `CNAME` file with the line `alldreamsreal.studio`, push it, and set the domain:
   `gh api -X PUT repos/abcedmind/alldreamsreal/pages -f cname=alldreamsreal.studio`
   The order matters. Once the domain is set, the github.io address redirects to it, so setting it before DNS resolves takes the site offline.
5. When the certificate has been issued, enforce HTTPS:
   `gh api -X PUT repos/abcedmind/alldreamsreal/pages -F https_enforced=true`

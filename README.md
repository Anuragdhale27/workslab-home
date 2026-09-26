# Works Lab homepage (workslab.in)

The company homepage for Works Lab. It is plain HTML, CSS and JavaScript with no build step,
so GitHub Pages can serve it directly. The resume builder stays in its own repo at
`resume.workslab.in` and is not touched by this site; the homepage only links to it.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole homepage (styles and script are inside the file) |
| `404.html` | Page shown for broken links |
| `CNAME` | Tells GitHub Pages this site lives at `workslab.in` |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `og-image.png` | Preview image shown when the link is shared on WhatsApp, LinkedIn, etc. |
| `robots.txt`, `sitemap.xml` | For Google indexing |
| favicons, `site.webmanifest` | Same W logo as the resume site |

## Deploy on GitHub Pages

GitHub Pages allows one custom domain per repository. `resume.workslab.in` already belongs to the
`works-lab` repo, so the homepage needs a **new, separate repository**.

1. On GitHub, create a new public repo, for example `workslab-home`.
2. Upload every file from this folder to the root of the repo (including `CNAME` and `.nojekyll`).
3. In the repo, go to **Settings → Pages**.
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**, then Save.
   - Custom domain: `workslab.in` (should already be filled in from the `CNAME` file), then Save.
4. Add the DNS records below at your domain registrar.
5. When the DNS check turns green (can take from a few minutes up to 24 hours), tick
   **Enforce HTTPS**.

## DNS records

Keep the existing `resume` record exactly as it is. Add these:

| Type | Name / Host | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| AAAA (optional) | `@` | `2606:50c0:8000::153` |
| AAAA (optional) | `@` | `2606:50c0:8001::153` |
| AAAA (optional) | `@` | `2606:50c0:8002::153` |
| AAAA (optional) | `@` | `2606:50c0:8003::153` |
| CNAME | `www` | `anuragdhale27.github.io` |
| CNAME | `resume` | `anuragdhale27.github.io` (already exists, leave it) |

Remove any other A records on `@` (for example a registrar "parking" page), or they will conflict.

Recommended: in your GitHub account go to **Settings → Pages → Verified domains** and verify
`workslab.in`. This stops anyone else from claiming your domain on GitHub Pages.

## Editing the content

Everything is in `index.html`:

- **Email address**: search for `adwork895@gmail.com` (it appears in the contact section,
  the JSON-LD block near the top and the `EMAIL` constant in the script at the bottom).
- **Services**: each service is a `<div class="svc">` block in the `#services` section. Copy one
  block to add a service, and give its panel a new unique `id`.
- **Resume product facts** (price, template count): in the `#resume` section.
- **Colours**: the CSS variables at the top of the `<style>` block (`--green` is the brand green
  shared with the resume site).

The contact form has no server. It opens the visitor's email app with a prefilled message to
your address. If you later want submissions to arrive without the email app (for example via
Formspree, Web3Forms or a Google Form), replace the form's submit handler.

## Preview locally

Open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit
http://localhost:8000.

## Tracker offer (v2)

- **Price**: search `₹100` in `index.html` to change the launch price everywhere (announcement bar,
  hero, offer card, FAQ, final CTA, meta description).
- **Tracker links** point to `https://tracker.workslab.in`. If you add a payment link, replace those
  `href` values with it.
- **CNAME**: this copy has no `CNAME` file so it can be tested on `anuragdhale27.github.io/<repo>/`.
  Add a `CNAME` file containing `workslab.in` when you move to the real domain.

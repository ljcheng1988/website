# WAXSAM official website

A static, responsive one-page website for WAXSAM Trading Co., Ltd. — a Shantou-based OEM/ODM manufacturer and exporter of cartoon novelty fans, portable and desktop fans, mini lamps and night lights since 2008.

## Structure

```
index.html              Main page (all sections)
styles.css              Design system and responsive layout
script.js               Navigation, product filters, scroll reveal, contact form
assets/product-art.svg  SVG illustrations used throughout the site
assets/favicon.svg      Site icon
```

No build step or dependencies. Product artwork is intentionally made with inline SVG placeholders so the site works immediately; replace the `<use href="assets/product-art.svg#…">` references with real product photos when available.

## Local preview

Open `index.html` in a browser, or serve the folder locally (recommended, as external SVG references may be blocked on `file://`):

```bash
npx serve .
# or
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## Deploy

GitHub holds the source code. The live test site is served by a Cloudflare Worker with static assets:

```bash
npx wrangler deploy
```

`wrangler.jsonc` names the Worker `website` and serves the repository root as static assets; `.assetsignore` lists repository files that should not be published when deploying with Wrangler.

The live test domain is `https://thrivingelephant.xyz` (apex), served through Cloudflare. The `www` subdomain is not configured yet; add a Cloudflare redirect rule from `www.thrivingelephant.xyz/*` to `https://thrivingelephant.xyz/$1` if both forms are needed.

GitHub Pages is kept only as a secondary preview at `https://ljcheng1988.github.io/website/`; its custom domain setting has been removed to avoid conflicts with Cloudflare.

## Contact details shown on the site

- Email: waxsam@outlook.com
- Tel: +86 754 87216469
- WhatsApp / Mobile: +86 15815304222
- Address: Wenguan Road, Chenghai, Shantou City, Guangdong Province, China 515800

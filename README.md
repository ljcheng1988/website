# WAXSAM official website

A static, responsive one-page website for WAXSAM Trading Co., Ltd. — a Shantou-based OEM/ODM manufacturer and exporter of cartoon novelty fans, portable and desktop fans, mini lamps and night lights since 2008.

## Structure

```
index.html                  Main page
about/index.html            About hub / photo gallery index
about/tradeshows/           Trade shows & fairs gallery
about/factory/              Factory gallery
about/office/               Privacy-conscious office gallery
about/production/           Production & quality control gallery
styles.css                  Design system and responsive layout
script.js                   Navigation, product filters, scroll reveal, contact form
assets/products/            Optimized WebP product photos
assets/gallery/             Optimized WebP gallery photos
assets/logo.jpg             WAXSAM logo used in the styled header mark
assets/favicon.svg          Site icon
```

No build step or dependencies. Product cards use optimized real photos from `assets/products/`; the gallery pages live under `about/` and are kept off the homepage.

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

## Version history

- `v1.0` — archived first version (static site before photo galleries).
- `v1.0A` — adds three photo gallery anchors inside About: `#tradeshows`, `#factory`, `#production`. Product/trade-show/factory/production photos are optimised WebP files in `assets/gallery/`; the original uploads remain untouched in `assets/`.
- `v1.0B` — replaces product illustrations with real optimized WebP photos, moves all photo galleries out of the homepage into `about/` subpages, styles the WAXSAM logo into the header, and replaces the office gallery with small, softened, privacy-conscious images.
- `v1.0C` — current published version: adds the latest trade-show, factory and office photos, reduces office blur to a very light touch, rewrites the office introduction, puts `Our office` last in the About grid, and hardens Cloudflare publishing so raw uploads and Wrangler local files are never served.

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

## Deploy to GitHub Pages

1. Push this folder to the target GitHub repository.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, choose `main` / `/ (root)`, and save.
4. Your site will be available at `https://<username>.github.io/<repository>/`.

## Contact details shown on the site

- Email: waxsam@outlook.com
- Tel: +86 754 87216469
- WhatsApp / Mobile: +86 15815304222
- Address: Wenguan Road, Chenghai, Shantou City, Guangdong Province, China 515800

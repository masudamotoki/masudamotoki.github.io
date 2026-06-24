# CLAUDE.md

## Project Overview

This is a static personal website hosted on **GitHub Pages** at `masudamotoki.github.io`. It is a Progate-style landing page clone built with plain HTML and CSS (no build tools, no JavaScript frameworks).

## Repository Structure

```
.
├── index.html       # Main (and only) HTML page
├── stylesheet.css   # All styles for the site
├── top.png          # Hero background image (~680KB)
└── README.md        # Repo description
```

## Tech Stack

- **HTML5** — single-page static site
- **CSS3** — custom stylesheet with responsive media queries
- **Font Awesome 4.7** — icon font loaded via CDN
- **GitHub Pages** — hosting (serves from the `main` branch root)

No build step, no package manager, no JavaScript.

## Development Workflow

1. Edit `index.html` or `stylesheet.css` directly
2. Open `index.html` in a browser to preview changes
3. Commit and push to `main` — GitHub Pages deploys automatically

There are no tests, linters, or CI pipelines configured.

## Key Conventions

- **Language**: Page content is in Japanese; code comments (if any) and structural labels are in English
- **CSS class naming**: Lowercase with hyphens (e.g., `.top-wrapper`, `.btn-wrapper`, `.lesson-icon`)
- **Layout**: Uses `float`-based layout with a `.clear` utility class, not flexbox/grid
- **Responsive design**: Three breakpoints via `@media` queries at 1000px, 750px, and 670px
- **External assets**: Logo and lesson icons are loaded from `prog-8.com` CDN URLs; only `top.png` is local

## File Details

### `index.html`
- Standard HTML5 document with `<header>`, hero section (`.top-wrapper`), lessons grid (`.lesson-wrapper`), CTA section (`.message-wrapper`), and `<footer>`
- Links Font Awesome 4.7 from MaxCDN and the local `stylesheet.css`

### `stylesheet.css`
- Uses `box-sizing: border-box` globally
- Fixed-position header with semi-transparent dark background
- Hero section with `top.png` as `background-image: cover`
- Four-column lesson grid that collapses to 2-column at 1000px and single-column at 670px
- Button hover/active states with opacity transitions and box-shadow effects

## Things to Watch Out For

- External image URLs (`prog-8.com`) may break if that CDN changes; consider hosting images locally if longevity matters
- `top.png` is large (~680KB); compress it if page load speed becomes a concern
- The site uses `float` layout — be careful when adding new sections to maintain the float/clear pattern, or consider migrating to flexbox
- Font Awesome 4.7 is loaded over MaxCDN which has been sunset; the integrity hash keeps it working for now but this CDN link may eventually break

# Aerojini Solutions Website

Corporate website for [Aerojini Solutions](https://www.aerojini.com), built with [Hugo](https://gohugo.io/) and the [hugo-fresh](https://github.com/StefMa/hugo-fresh) theme, deployed on Netlify.

## Tech Stack

- **Static Site Generator:** Hugo `0.170.1`
- **Runtime:** Node.js `24` (pinned in `.nvmrc` and `netlify.toml`)
- **CSS Compilation:** Dart Sass via `sass-embedded`
- **Theme:** `hugo-fresh` (Git submodule in `themes/hugo-fresh`)
- **Hosting & Forms:** Netlify

## Prerequisites

- [Hugo](https://gohugo.io/installation/) `0.170.1` or higher
- [Node.js](https://nodejs.org/) `24` or higher (includes `npm`)

## Local Development

1. Clone the repository including the theme submodule:

   ```bash
   git clone --recurse-submodules <repo-url>
   cd aj-websitev2
   ```

   If already cloned without submodules:

   ```bash
   git submodule update --init --recursive
   ```

2. Install dependencies (`sass-embedded` for Sass compilation):

   ```bash
   npm install
   ```

3. Start the local development server:

   ```bash
   npm run dev
   ```

4. Build the production site into `public/`:

   ```bash
   npm run build
   ```

## Project Structure

- `config.yaml` — Site configuration, navigation, homepage sections, and footer links
- `content/blog/` — Content pages (`about`, `contact`, `memberjini`, `tradejini`, `privacy`, `tnc`)
- `layouts/` — Local template overrides (`css.html`, `meta.html`, `gtm.html`, `hero-footer.html`, `section5.html`)
- `themes/hugo-fresh/` — Upstream theme submodule
- `netlify.toml` & `.nvmrc` — Netlify build, Node.js, and Hugo environment configuration

## Deployment

Deployments are managed automatically by Netlify using `netlify.toml`:

- **Build command:** `npm run build` (`hugo --gc --minify`)
- **Publish directory:** `public`
- **Environment:** `NODE_VERSION = "24"`, `HUGO_VERSION = "0.170.1"`

# Moyai website

A static rebuild of [moyai.com.au](https://moyai.com.au), built with [Astro](https://astro.build) and deployed to GitHub Pages.

## Develop

```sh
npm install
npm run dev      # local dev server at http://localhost:4321/moyai-website
npm run build    # static build into ./dist
npm run preview  # preview the production build
```

## Deploy

Pushing to `main` triggers the [`Deploy to GitHub Pages`](.github/workflows/deploy.yml)
workflow, which builds the site with `withastro/action` and publishes it to GitHub Pages.

The site is configured for the default Pages URL (`https://<username>.github.io/moyai-website`)
via `base: '/moyai-website'` in [`astro.config.mjs`](astro.config.mjs). To serve from a custom
domain later, drop the `base` value and add a `CNAME` file to `public/`.

## Notes

- The "Book a demo" buttons link to `mailto:hello@moyai.com.au` as a placeholder — the
  original booking flow was intentionally left out of this rebuild.
- Content, copy and brand assets mirror the original site.

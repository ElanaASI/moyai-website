# CLAUDE.md

Project context for Claude Code and Cowork. Both tools read this file, so keep it accurate.

## What this is

Moyai marketing website, a static rebuild of moyai.com.au.

- Repo: ElanaASI/moyai-website
- Live: https://elanaasi.github.io/moyai-website/
- Framework: Astro with static output, deployed to GitHub Pages via the withastro/action workflow.

## Commands

- `npm install` installs dependencies.
- `npm run dev` runs the local dev server at http://localhost:4321/moyai-website
- `npm run build` produces the static site in `./dist`
- `npm run preview` previews the production build.

## Deploy

Pushing to `main` triggers the "Deploy to GitHub Pages" workflow, which builds and publishes the site. The site uses `base: '/moyai-website'` in `astro.config.mjs` for the default Pages URL. To move to a custom domain later, drop the base value and add a CNAME file to `public/`.

## Structure

- `src/pages/` holds the routes: `index.astro`, `about.astro`, `privacy.astro`.
- `src/layouts/Layout.astro` is the shared shell: header with the primary nav and "Let's talk" CTA, plus the footer.
- `src/styles/global.css` holds global styles. Per-page styles are inline `<style>` blocks.
- `public/` holds images, logos, and the favicon.

## Booking call to action (important)

The "Let's talk" buttons drive bookings through Microsoft Bookings. Calendly is not used.

- There are three: the nav CTA in `Layout.astro`, plus the hero and final-section CTAs in `index.astro` (the last two share the `bookDemo` constant).
- All three link to: `https://outlook.office.com/book/Moyai1@moyai.com.au/`
- All open in a new tab with `target="_blank" rel="noopener noreferrer"`, and each carries a screen-reader cue `<span class="sr-only"> (opens in a new tab)</span>`.
- The footer "Contact" link `mailto:hello@moyai.com.au` is a genuine contact link and stays as is. Do not repoint it to Bookings.

## Conventions

- Language is Australian English, set on `<html lang="en-AU">`.
- Never use em dashes or en dashes in copy. Use commas, "to" for ranges, or restructure the sentence.
- Accessibility target is WCAG 2.2 AA. Keep screen-reader cues for new-tab links and meaningful alt text on images.
- The header and footer logo is the Moyai wordmark only, with no tagline.
- Content, copy, and brand assets mirror the original moyai.com.au.

## Operational context

Wider project context, including the Microsoft Bookings configuration and the working-folder and security setup, lives in `MOYAI-CONTEXT.md` one level up, in the Claude Dispatch folder. That file is intentionally kept out of this repo. Do not copy its contents into this committed file.

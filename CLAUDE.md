# szlmagyariskola.ca

Static Astro site for the Szent László Magyar Iskola (Hungarian school in Vancouver).
No database, no API, no client-side framework. Site language is Hungarian.

## Commands

- `npm run dev` – dev server at http://localhost:4321
- `npm run build` – static build to `dist/` (run this to verify changes)

## Structure

- One page = one `.astro` file in `src/pages/`. Routes are English, nested to
  express hierarchy, and live under a language prefix: `src/pages/hu/` (Hungarian)
  and `src/pages/en/` (English) mirror each other 1:1 — e.g.
  `/hu/education/teachers` ↔ `/en/education/teachers`. Keep them in sync: a new
  page must be added to both trees, or the header's flag switcher (which swaps the
  `/hu`/`/en` prefix) will 404. Section landing pages are `<section>/index.astro`.
  Pages pass `lang="en"` to the `Base` layout on the English side; nav labels and
  footer strings live in `Base.astro`. `/` redirects to `/hu`. All earlier URL
  generations (Hungarian originals, flat English, un-prefixed nested) redirect via
  the `redirects` map in `astro.config.mjs` — keep that map in sync if routes change.
- News posts live in `src/content/news/hu/*.md` and `src/content/news/en/*.md`
  (one collection defined in `src/content.config.ts`; the news pages filter by id
  prefix). Adding a news item = adding a markdown file with `title` and `date`
  frontmatter to each language folder. The `/hu/news` and `/en/news` pages list
  them newest-first.
- The homepage poem (Szonett az anyanyelvről) intentionally stays in Hungarian on
  the English page too.
- Shared layout/nav/footer: `src/layouts/Base.astro`. The nav menu is the `nav`
  array at the top of that file.
- All styling: `src/styles/global.css`. Fonts: EB Garamond (headings),
  Open Sans (body), Alegreya Sans SC (nav) via Google Fonts.
- Images: `public/images/` with descriptive Hungarian names
  (`tabor2022-01.jpg`, `tanterem-03.jpg`, `tanar-*.jpg`).
- Downloadable documents: `public/docs/`.

## Content conventions

- Write user-facing text in Hungarian, matching the tone of existing pages.
- School facts: founded 1960, address 1810 East 7th Avenue, Vancouver B.C. V5N 1S2,
  email szlmagyariskola@gmail.com.

# Szent László Magyar Iskola – szlmagyariskola.ca

A vancouveri Szent László Magyar Iskola honlapja, [Astro](https://astro.build)-val építve.
A tartalom a korábbi website.com-os oldalról lett átmentve 2026 júliusában.

## Fejlesztés

```bash
npm install
npm run dev      # fejlesztői szerver: http://localhost:4321
npm run build    # statikus build a dist/ mappába
```

## Szerkezet

- `src/pages/` – az oldalak (egy `.astro` fájl = egy oldal, a fájlnév az URL;
  a magyar oldalak a `hu/`, az angol oldalak az `en/` mappában, tükrözve egymást)
- `src/content/news/hu/` és `src/content/news/en/` – hírek markdown fájlokban;
  új hír = új `.md` fájl mindkét nyelvi mappába
- `src/layouts/Base.astro` – közös keret: fejléc, menü, lábléc
- `src/styles/global.css` – minden stílus
- `public/images/` – képek
- `public/docs/` – letölthető dokumentumok (pl. jelentkezési lap)

## Új hír közzététele

Hozz létre egy új fájlt a `src/content/news/` mappában, pl. `2026-09-01-tanevnyito.md`:

```markdown
---
title: Tanévnyitó
date: 2026-09-01
---

A tanévnyitó szöveges tartalma ide kerül, markdown formátumban.
```

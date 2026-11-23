# Le Index — A building full of stories

A snowy, illustrated newsstand for **Le Index by Anna Noelle Rinke**. Every illuminated apartment window opens an article on Substack.

**[Visit the newsstand](https://le-index-substack.vercel.app/)** · **[Read Le Index on Substack](https://annanoellerinke.substack.com/)**

![Le Index newsstand](site/assets/social-preview.jpg)

## Explore

- 78 articles, newest upstairs and oldest just above street level.
- Five windows per row, with varied warm light and dark apartments between articles.
- Visible filters for All articles, Entrepreneur Edit, The Build w/ AI, and BODY & MIND.
- Original text-over-photo article covers; hover or focus a window for a closer look.
- Falling snow with a pause control and reduced-motion support.
- A centered, open entrance: click the welcome door and the waving host walks inside before opening the Substack homepage.
- Responsive layout with a different grey neighboring building on either side.

## Run locally

The site uses plain HTML, CSS, JavaScript, and local image assets. There are no package dependencies, API keys, or account requirements.

With Node.js 20+ and Python 3 installed:

```sh
npm run build
npm run preview
```

Open [localhost:4173](http://localhost:4173/). Any static HTTP server can serve the `site` directory instead of Python.

## Update articles

The archive is a snapshot of the publication as of November 22, 2026; it does not automatically sync with Substack.

1. Add an entry to `source/articles.json` using the same fields as the existing entries: `id`, `postId`, `title`, `date`, `url`, `tags`, and `cover`.
2. Save the article's text-over-photo cover in `site/assets/covers/` and use its `/assets/covers/...` path in `cover`.
3. Use the existing category names in `tags` and an ISO date in `date`.
4. Run `npm run build`. Articles are sorted by date, and category counts and the window arrangement are rebuilt.

## Project map

| File | Purpose |
| --- | --- |
| `scripts/build-building.mjs` | Generates the homepage and `/building/` preview from the article data |
| `site/building/layout.mjs` | Places articles into the illustrated window rows |
| `site/building/styles.css` | Street layout, category controls, and welcome animation |
| `site/building/app.mjs` | Filtering, cover previews, snow, and the door interaction |
| `site/building/assets/` | Building, neighboring facades, entrance, and host sprite artwork |
| `source/articles.json` | Article titles, dates, categories, covers, and links |
| `source/entrance-image-prompts.json` | Prompts used for the generated entrance and animation artwork |

## Deploy

Import this repository into Vercel with the **Other** framework preset. `vercel.json` defines the build command and the `site` output directory. No environment variables are required.

The building is served at `/`; `/building/` is also available. Category selections can be shared using `?category=entrepreneur`, `?category=ai`, or `?category=body`. The entrance can be linked directly with `/#welcome`.

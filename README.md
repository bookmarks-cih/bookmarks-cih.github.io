# Bookmarks Admin Panel

Minimal, fast, clean **copy-paste admin panel** for [`bookmarks.love`](https://bookmarks.love/).

Live site: <https://bookmarks-cih.github.io/>

This tool never edits the production site directly. It only generates source-compatible blocks that you manually copy and paste into the correct file.

## What you can generate

### Site / resource link

For:

- `data/bookmarks-data.js` / `window.BOOKMARKS_DATA`
- `docs.html` / `const docsData`
- `files.html` / `const docsData`
- `jobs.html` / `const docsData`
- any same-format custom page

Format:

```js
{ name: "Site", link: "https://example.com", desc: "Description.", cat: "Category" },
```

### Creator card

For `creators.html` / `const CREATORS_DATA`.

### Creator profile header

For pages based on `creators/profiletemplate.html`.

### Creator profile resource

For profile `collectionData` sections.

### Hub tile

For `hub.html` / `const featuredData`.

### News / update block

A clean standalone HTML section for `news.html` content.

## Workflow

1. Select the block type.
2. Fill only the visible fields/selectors.
3. Click **Add to drafts**.
4. Repeat for anything else you want to add.
5. Copy the generated output.
6. Paste it manually into the matching source file.

## Safety

- No GitHub token.
- No GitHub write API.
- No Neocities sync.
- No production modification.
- Drafts are stored locally in browser `localStorage`.
- You can export/import the workspace as JSON.

## Files

```text
index.html
styles.css
app.js
```

## Extra generators added

The panel now also supports:

- **News changelog post**: matches `news.html` Project Changelog `.glass-card` blocks.
- **News source card**: matches `news.html` Curated News Directory cards inside `.news-grid`.
- **Generic page section**: reusable section/card block for `about.html`, `privacy.html`, `terms.html`, `join.html`, `edit.html`, `news.html`, `hub.html`, or any custom page.
- **Navigation / menu item**: small hamburger/header menu item block.

## Compact UI

The UI uses a denser layout, roughly a 20% visual zoom-out effect:

- smaller controls;
- reduced spacing;
- wider workspace;
- larger visible code area;
- faster one-screen editing.

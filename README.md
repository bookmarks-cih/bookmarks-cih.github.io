# Bookmarks Admin Studio

Static **copy-paste admin interface** for [`bookmarks.love`](https://bookmarks.love/).

This repository is independent from the production source repository [`bookmarks-cih/Bookmarks`](https://github.com/bookmarks-cih/Bookmarks). It does **not** push changes to the main site and it does **not** sync with Neocities.

The final workflow is always manual and safe:

1. manage data in the admin UI;
2. validate and preview locally;
3. generate source-compatible code blocks;
4. copy the final block;
5. paste it into the real source file yourself.

## Live site

<https://bookmarks-cih.github.io/>

## What it manages

### 1. Bookmarks

Compatible with `data/bookmarks-data.js`:

```js
window.BOOKMARKS_DATA = [
  { name: "Site", link: "https://example.com", desc: "Description.", cat: "Category" },
];
```

Paste generated bookmark blocks inside:

```js
window.BOOKMARKS_DATA = [
  // paste generated block here
];
```

### 2. Creator cards

Compatible with the `CREATORS_DATA` array in `creators.html`:

```js
const CREATORS_DATA = [
  {
    id: 1,
    name: "Creator",
    handle: "@creator",
    initials: "CR",
    avatar: "/creators/img/avatar.jpg",
    verified: true,
    category: "Security",
    bio: "Short creator bio.",
    links: 10,
    url: "/creators/creator.html",
    socials: {
      x: "#",
      youtube: "#",
      github: "#",
      website: "#",
      spotify: "#",
      apple_podcast: "#"
    }
  },
];
```

### 3. Creator profile resources

Generates profile-page blocks compatible with pages based on:

```text
creators/profiletemplate.html
```

Recommended workflow:

1. duplicate `creators/profiletemplate.html`;
2. rename it, for example `creators/newcreator.html`;
3. paste the generated profile section;
4. paste the generated `collectionData` block;
5. test before publishing.

## Safety model

This tool is deliberately non-destructive.

- No GitHub token is stored.
- No GitHub API write is performed.
- No automatic commit is created in the main project.
- No Neocities deployment is triggered.
- Draft data is stored in browser `localStorage`.
- Workspace backups can be exported/imported as JSON.
- The final action is always **copy-paste**.

## Features

- English UI.
- Fast live code generation.
- Local autosave.
- JSON workspace export/import.
- Bookmark category grouping and sorting.
- Creator card editor.
- Creator profile section/resource builder.
- Import from pasted JavaScript snippets.
- Duplicate URL warnings.
- Missing field and URL-shape validation.
- Local copy history.
- Snippet download.

## Suggested production workflow

In the main `bookmarks-cih/Bookmarks` repository:

```bash
git checkout -b add-curated-data
```

Then use the Admin Studio:

1. enter or import data;
2. fix warnings;
3. choose the output mode;
4. click **Copy final block**;
5. paste into the correct source file;
6. preview/test the site;
7. commit only if everything is correct.

Example commit:

```bash
git add data/bookmarks-data.js creators.html creators/newcreator.html
git commit -m "Add curated bookmarks and creator resources"
```

To undo, remove the pasted block or revert the commit.

## Local development

This is a plain static site. No build step is required.

Files:

```text
index.html
styles.css
app.js
```

Open `index.html` directly or serve the folder with any static server.

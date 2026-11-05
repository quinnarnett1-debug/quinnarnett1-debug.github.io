# Flag Drill

A flag quiz with 573 flags in nine decks: countries, territories, U.S. states, Canadian provinces and territories, Australian states, Mexican states, Brazilian states, European regions, and former countries.

## Try it on your computer

Double-click `index.html`. It opens in your browser and works offline, except Minnesota and Utah, whose current (2024) flags load from Wikimedia Commons.

## What's in the folder

| Path | What it is |
| --- | --- |
| `index.html` | The whole quiz: layout, styles, and game logic |
| `data/decks.js` | Every flag, one per line, grouped into decks |
| `flags/` | The flag images (SVG) |
| `CREDITS.md` | Where the flags and facts came from |

## Editing the flags

Open `data/decks.js` in a text editor. Each line is one flag:

```js
{"name": "Texas", "group": "United States", "img": "flags/US-TX.svg", "fact": "...", "source": "..."},
```

- **name** is the answer.
- **group** decides the wrong answers: they come from the same group first. In Countries it's the continent; in Europe's Regions it's the country.
- **img** is the image file in `flags/`, or a full web address.
- **fact** is shown after you answer. **source** is the "More about this flag" link. Both can be `""`.

To remove a flag, delete its line. To add one, copy a line, change it, and drop the image into `flags/`. To add a whole deck, copy a block from `{ id: ...` down to its closing `]},` and give it a new `id` and `name`.

## Putting it online for free

**Easiest: Netlify Drop.** Go to app.netlify.com/drop, sign up, and drag the whole `flag-drill` folder onto the page. You get a link right away.

**GitHub Pages:**
1. Make a free account at github.com and install GitHub Desktop.
2. In GitHub Desktop: File → New repository, name it `flag-drill`, and choose the folder that contains this one.
3. Click **Publish repository** and uncheck "Keep this code private".
4. On github.com, open the repository → Settings → Pages. Under "Branch", pick `main` and `/ (root)`, then Save.
5. After a minute your quiz is at `https://YOUR-USERNAME.github.io/flag-drill/`.

GitHub's website only uploads 100 files at a time, and the `flags/` folder has over 500, which is why GitHub Desktop is the easier route.

When you change files later, GitHub Desktop shows the changes. Click **Commit**, then **Push**, and the site updates in about a minute.

Add `#us-states`, `#former`, or any deck id to the end of the address to open straight to that deck.

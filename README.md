# School Dinners

A tiny offline-capable web app showing the school dinner menu, opened on the right day automatically. Built from the South West Norse Spring/Summer 2026 primary menu — a three-week rotation running to Friday 23 October 2026.

## Files

```
index.html              the whole app (HTML, CSS and JS in one file)
manifest.webmanifest    makes it installable
sw.js                   service worker, caches it for offline use
icons/                  app icons (192, 512, maskable, apple-touch)
```

## Put it on GitHub Pages

1. Create a new public repo, e.g. `school-lunch`.
2. Upload every file here, keeping the `icons` folder intact. Nothing goes in a subfolder except the icons.
3. Repo → **Settings** → **Pages** → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)`. Save.
4. After a minute it's live at `https://YOUR-NAME.github.io/school-lunch/`.

All paths are relative, so it works from a repo subfolder without any changes.

## Install it on a phone

- **Android / Chrome:** open the link, menu → *Add to Home screen*.
- **iPhone / Safari:** open the link, Share → *Add to Home Screen*.

It opens full screen, without browser chrome, and works with no signal.

## Updating the menu

Everything lives in `index.html`:

- `MENUS` — weeks 1, 2 and 3, five days each. Edit the text, keep the structure.
- `MONDAYS` — the Mondays each week runs from, copied from under each table on the printed menu. When school issues the Autumn/Winter menu, replace these dates and the dishes.
- Tags: `tag:"v"` for vegetarian, `tag:"ve"` for vegan, or leave it out.

Any Monday not listed in `MONDAYS` shows as closed, so half-terms and the summer break look after themselves. `CLOSED` names the ones worth naming — currently May half term (25 May) and October half term (26 to 30 October). Add a Monday there to have the app say why the hatch is shut.

After any edit, bump `CACHE = "lunch-v5"` in `sw.js` to `lunch-v6` so installed phones pick up the new version.

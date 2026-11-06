# Markdown Reader

A single-file markdown viewer that runs entirely in your browser. No server, no build step, no network requests.

- Drag and drop a `.md` file, paste markdown, or browse for a file
- GitHub Flavored Markdown: tables, task lists, strikethrough
- Syntax-highlighted code blocks
- Read / source toggle, light / dark theme
- Installable as a desktop app (PWA), works offline once loaded

Your files never leave your browser.

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `md-reader`).
2. Upload everything in this folder to the root of the repo (everything except the optional `.nojekyll`, which GitHub's web uploader refuses; you can add it with *Add file → Create new file*).
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, then **Save**.
5. After a minute or so, the site is live at `https://<your-username>.github.io/<repo-name>/`.

Or from the command line:

```bash
git init
git add .
git commit -m "Add markdown reader"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages as in step 3 above.

## Install as a desktop app

Once the site is live on GitHub Pages (it must be served over https):

- **Chrome / Edge:** open the site, then click the install icon in the address bar (or menu → *Install Markdown Reader*).
- **Safari (macOS):** File → *Add to Dock*.
- It then runs in its own window and works offline.

On Chrome and Edge, the installed app can also be set as the handler for `.md` files: right-click a `.md` file → *Open with* → *Markdown Reader*.

## Updating

Edit `index.html`, then bump the `CACHE` name in `sw.js` (e.g. `md-reader-v2`) so installed copies pick up the change.

## Files

- `index.html`: the app
- `manifest.webmanifest`: install metadata and `.md` file association
- `sw.js`: service worker for offline use
- `icon-*.png`, `apple-touch-icon.png`: app icons
- `.nojekyll`: optional, tells Pages to skip Jekyll

## Bundled libraries

All inlined into `index.html`:

- [marked](https://github.com/markedjs/marked) (MIT)
- [DOMPurify](https://github.com/cure53/DOMPurify) (Apache-2.0 / MPL-2.0)
- [highlight.js](https://github.com/highlightjs/highlight.js) (BSD-3-Clause)

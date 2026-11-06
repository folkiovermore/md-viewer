# Markdown Reader

A single-file markdown viewer that runs entirely in your browser. No server, no build step, no network requests.

- Drag and drop a `.md` file, paste markdown, or browse for a file
- GitHub Flavored Markdown: tables, task lists, strikethrough
- Syntax-highlighted code blocks
- Read / source toggle, light / dark theme

Your files never leave your browser.

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `md-reader`).
2. Upload everything in this folder to the root of the repo (`index.html`, `README.md`, `.nojekyll`).
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

## Bundled libraries

All inlined into `index.html`:

- [marked](https://github.com/markedjs/marked) (MIT)
- [DOMPurify](https://github.com/cure53/DOMPurify) (Apache-2.0 / MPL-2.0)
- [highlight.js](https://github.com/highlightjs/highlight.js) (BSD-3-Clause)

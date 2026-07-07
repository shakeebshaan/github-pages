# github-pages

Central static host for public-facing pages from any of my repos.

**Live:** https://shakeebshaan.github.io/github-pages/

## Structure

```
/                 landing hub (index.html) — lists all hosted pages
/<project>/       one folder per project, each with its own index.html
.nojekyll         serve files raw (no Jekyll processing)
```

## Add a page for another repo

1. Make a folder named after the project: `mkdir my-project`
2. Drop static files in it, with an `index.html` entry point.
3. Add a card for it in root `index.html` (the `PAGES` array).
4. Commit + push to `main`. Pages auto-deploys.

Live at `https://shakeebshaan.github.io/github-pages/my-project/`.

### Options for getting a repo's page here

- **Copy** built static output into a folder (simple, manual).
- **Git subtree** to pull a repo's `dist`/`public` in:
  `git subtree add --prefix my-project https://github.com/shakeebshaan/my-project.git gh-pages --squash`
- **CI push** from the source repo into a folder here.

## Notes

- Project Pages base path is `/github-pages/`. Use relative asset paths
  (`./style.css`) or set `<base href>` so links resolve under the subpath.
- `.nojekyll` is required — without it GitHub ignores files/folders starting
  with `_`.

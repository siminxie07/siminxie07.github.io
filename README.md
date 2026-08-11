# siminxie07.github.io

Single-page academic site. Plain HTML + one CSS file, no build step, no JavaScript.

## Files

```
index.html      the whole site
style.css       all styling
.nojekyll       tells GitHub Pages to serve files as-is
assets/
  photo.svg     placeholder headshot — replace
  cv.pdf        ← you add this
```

## Deploy

1. Rename the repo to `siminxie07.github.io` (Settings → Repository name → Rename).
2. Upload `index.html`, `style.css`, `.nojekyll`, and the whole `assets` folder.
   The `assets` folder must stay a folder — don't flatten `photo.svg` into the root.
3. Settings → Pages → Source: Deploy from a branch → `main` + `/ (root)` → Save.
4. Open https://siminxie07.github.io

## Still to fill in

- Temple email (I guessed `simin.xie@temple.edu` — check it)
- SSRN and Google Scholar IDs, or delete those lines
- LinkedIn handle, or delete that line
- Your own abstract for the SBA paper, replacing my summary
- Second paper / works in progress / teaching, or delete those blocks
- `assets/cv.pdf`
- Real headshot replacing `assets/photo.svg` (if you save it as `photo.jpg`, update the `src` in index.html)
- Footer date

## Adding a paper

Copy one `<article class="paper">` block and edit it. Order by how good the
paper is, not by date.

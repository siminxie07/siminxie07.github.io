# Personal academic website

A three-page static site for a finance PhD student. No build step, no
dependencies, no framework — plain HTML and one stylesheet. Edit the HTML,
commit, done.

```
├── index.html        About, research at a glance, news
├── research.html     Job market paper, working papers, publications, WIP
├── teaching.html     Teaching, service, references
├── style.css         All styling for all three pages
├── .nojekyll         Tells GitHub Pages to serve the files as-is
└── assets/
    ├── photo.svg     Placeholder headshot — replace
    ├── cv.pdf        ← you add this
    └── jmp.pdf       ← you add this
```

---

## Deploy to GitHub Pages

### Option A — the clean URL (`yourname.github.io`)

1. On GitHub, create a **new public repository** named exactly
   `your-username.github.io`, substituting your actual GitHub username.
   Leave "Add a README" unchecked.
2. On the empty repo page, click **uploading an existing file**.
3. Drag in `index.html`, `research.html`, `teaching.html`, `style.css`,
   `.nojekyll`, and the `assets` folder. Commit to `main`.
4. Wait about a minute, then open `https://your-username.github.io`.

Pages turns itself on automatically for repos named this way. You only get one
per account, and it lives at the root URL, which is what you want on a CV.

### Option B — any repo name (`yourname.github.io/website`)

Same as above but name the repo whatever you like, then go to
**Settings → Pages → Build and deployment**, set Source to *Deploy from a
branch*, pick `main` and `/ (root)`, and Save. Every link in this site is
relative, so it works fine in a subfolder.

### Using git instead of the web uploader

```bash
cd personal-website
git init -b main
git add .
git commit -m "Initial site"
git remote add origin https://github.com/your-username/your-username.github.io.git
git push -u origin main
```

### Custom domain (optional)

Buy a domain, then create a file named `CNAME` in the repo root containing
just `www.yourname.com`. At your registrar, add a CNAME record pointing `www`
to `your-username.github.io`. Then tick **Enforce HTTPS** in Settings → Pages.
Worth doing — a personal domain outlives your university email.

---

## Edit checklist

Search each file for `EDIT ▸` for inline notes. Then replace:

| Placeholder | Where |
|---|---|
| `Your Name` | all three files, plus `<title>`, meta tags, JSON-LD, footer |
| `Your University` | all three files |
| `you@university.edu` | rail on all three files |
| `your-username` | rail links, canonical URL, JSON-LD |
| `XXXX` | Google Scholar and SSRN author IDs |
| `YN` | favicon initials, in the `<link rel="icon">` data URI |
| Sample papers | `research.html` and the "at a glance" block on `index.html` |
| Sample courses | `teaching.html` |
| `Last updated August 2026` | footer on all three files |

Drop `cv.pdf` and `jmp.pdf` into `assets/`. Replace `assets/photo.svg` with a
real headshot — if you save it as `photo.jpg`, update the three `src` attributes.

### Adding a paper

Copy one `<div class="table__row">` block in `research.html` and edit it. Order
the list by how good the paper is, not by date. The `<span class="star">***</span>`
marker and the `<b>***</b>` label flag the job market paper; there should be
exactly one.

---

## Design notes

The layout borrows the grammar of a results table from a finance paper: a heavy
top rule, hairlines between rows, a heavy bottom rule, and a `Notes:` line
underneath. The job market paper is flagged with `***`, defined in that note the
way a significance level would be. Palette is columnar ledger paper — pale green
rules on near-white stock, deep green-black ink. Type is Newsreader for display,
IBM Plex Sans for body, IBM Plex Mono for the table furniture.

Abstracts use native `<details>` elements, so they expand without JavaScript and
print expanded. There is no JavaScript anywhere in the site.

---

## Things worth doing after launch

- Put the URL in your email signature, on SSRN, and on your CV header.
- Keep the JMP PDF at a stable path. People bookmark it and link to it; a
  changing filename breaks those links.
- Update the footer date whenever you touch the site. A visible stale date is
  the fastest way to look inactive.
- Delete sections you can't keep current. An empty "News" heading is worse than
  no news at all.

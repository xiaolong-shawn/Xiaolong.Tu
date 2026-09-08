# Xiaolong Tu — personal website

Source for [xiaolong-shawn.github.io/Xiaolong.Tu](https://xiaolong-shawn.github.io/Xiaolong.Tu/), the
personal page of Xiaolong Tu, Ph.D. candidate in Computer Science at Georgia State University
([AMAI Lab](https://www.amai-gsu.us/)).

## How it works

The site is a single static page. `index.html` contains all the markup, styles, and scripts, so
there is no build step, no dependencies, and nothing to install. Push to `main` and GitHub Pages
publishes it.

Only two things load from outside the repository: Inter Tight and Newsreader from Google Fonts, and
the Google Analytics tag.

## Layout

```
index.html                      the whole site
assets/
  img/                          portrait, favicon
  documents/
    CV_xiaolong.pdf             linked from the header button
    publications/               paper PDFs linked from the publication list
```

## Editing

Everything is plain HTML in one file. The parts most likely to need updating:

- **Publications** — copy an existing `<article class="pub">` block and change the fields. The `.yr`
  column holds the year; `<span class="badge">` renders an award tag next to a title; the
  `<details>` element holds the BibTeX entry.
- **News** — a `<li>` inside `<ul class="news">`, newest first.
- **Honors and service** — the two `<ul class="plain">` lists.
- **Colours** — the `:root` and `html[data-theme="dark"]` blocks at the top of the stylesheet. Every
  colour on the page comes from those variables, so changing one value updates the whole site.

To replace the CV, upload a file named exactly `CV_xiaolong.pdf` to `assets/documents/`. Matching the
name overwrites the old file and keeps the link working.

## Local preview

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Opening `index.html` directly from the file system also works, but
serving it matches how GitHub Pages resolves paths.

## Credits

The repository began as a fork of [Nicolás Meseguer's academic portfolio](https://github.com/NicolasMeseguer/nicolasmeseguer.github.io),
licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/). The current page was
rewritten from scratch and no longer uses that template.

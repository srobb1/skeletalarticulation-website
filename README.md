# skeletalarticulation.com

The Skeletal Articulation website: plain HTML pages and one stylesheet, hosted on GitHub Pages.
To preview it, open `index.html` in a browser.

## Pages

- `index.html`: home
- `gallery.html`: the gallery
- `how-it-works.html`: what we make, the steps, what to expect
- `shipping.html`: if your pet has just passed (freezing, packing, shipping)
- `about.html`, `contact.html`
- `404.html`: shown for any address that doesn't exist

The folders `about-us/`, `services/`, `product/` and so on only hold forwarding pages,
so links to the old WordPress site still lead somewhere.

## Updating the gallery

The gallery is built from the folder `SKAR/gallery-photos/`, which lives outside this repo,
so the full-size originals never go online. One folder per section; each file's name is its caption:

    gallery-photos/2 Skulls/03 Ram (Ovis aries) - A ram skull with curled horns.jpg

Then double-click `SKAR/Update gallery.command` (or run `python3 tools/gallery.py` from `SKAR`).
It resizes the photos, strips their GPS and other metadata, writes them to `images/gallery/`,
and rewrites the gallery section of `gallery.html`. Don't hand-edit between the
`<!-- gallery -->` markers; it gets replaced.

The photo row on the home page works the same way, from `SKAR/home-page-photos/`
(no section folders), into `images/home/` and the `<!-- home-strip -->` part of `index.html`.

## Editing

- Every page has the same header and footer. If you change one, change it on every page.
- Images go in `images/`. Keep them around 1200px wide or smaller.
- Photos on a pure black background get `class="float"`, which fades their edges into the page.

## Icons

`favicon.ico`, `images/favicon.png`, `images/apple-touch-icon.png`, `images/mark.png` (the star in
the header) and `images/share.jpg` (the picture shown when someone shares a link) are all made
from the greyscale skull star by `SKAR/tools/brand.py`.

## Never commit

The WordPress export (`.wpress`) or anything pulled from it (`database.sql`, `db.json`).
It holds the whole old WordPress database. `.gitignore` blocks these.

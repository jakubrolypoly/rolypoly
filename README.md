# Rolypoly

Small internal tools for the Rolypoly creative agency.

This repository is served with GitHub Pages. The site is published from the repository root by `.github/workflows/pages.yml` on every push to `main`, and it can also be published by hand from the Actions tab.

The Review app is at `/review/`. It is a single static page for timestamped video notes. Open a video, mark it up, then copy the notes and paste them to whoever needs them.

A link can open a video directly: `/review/?v=<video>&title=<optional name>`. `v` is a Google Drive file id, a Drive share link (`https://drive.google.com/file/d/<id>/view`), or a direct video URL. Example: `https://jakubrolypoly.github.io/rolypoly/review/?v=1aBcDeFgHiJkLmNoPqRsTuVwXyZ012345&title=Rough%20cut`. A Drive file has to be shared as "Anyone with the link".

* Site: https://jakubrolypoly.github.io/rolypoly/
* Review: https://jakubrolypoly.github.io/rolypoly/review/

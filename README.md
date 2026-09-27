# leonarduschen.github.io

My personal website, served by GitHub Pages at
**[leonarduschen.github.io](https://leonarduschen.github.io)**.

Plain HTML and CSS generated from a content file by a small Python script —
no dependencies beyond the standard library.

```
content.toml     ← everything you edit: bio, links, projects, PRs, jobs
build.py            renders content.toml + template.html → index.html
template.html       the page shell; touch only to change the design
index.html       ← GENERATED, do not edit by hand
style.css           design tokens on :root, then sections in page order
.nojekyll           tells GitHub Pages to serve the files as-is
```

## Editing

Edit `content.toml`, then:

```bash
python3 build.py
```

Adding a job is a `[[experience]]` block; a project is `[[projects]]`; an
upstream repo is `[[oss.repos]]`, where PR URLs are derived from the repo name
and number so you only write the number. Backticks in any prose become inline
`<code>` on the page.

Commit both `content.toml` and the regenerated `index.html` — GitHub Pages
serves `index.html` directly and does not run the build.

## Previewing locally

```bash
python3 build.py && python3 -m http.server 8000
# open http://localhost:8000
```

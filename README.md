# antonioaurel.github.io

Personal portfolio — a single scrolling page: hero, experience, selected work,
case studies, skills, beyond the resume, and contact. Dark by default, with a
light theme; the choice is remembered.

All content lives in [`portfolio.json`](portfolio.json) — the page reads it and
builds every section. To change the site, edit the JSON, not the HTML.

```json
{
  "site":       { "name": "…", "about": "…", "cv": "cv/…pdf", "social": [] },
  "experience": [ { "id": "…", "company": "…", "period": "…", "role": "…",
                    "summary": "…", "responsibilities": [], "tech": [] } ],
  "work":       [ { "title": "…", "img": "image/…", "desc": "…",
                    "problem": "…", "tech": [], "links": [] } ],
  "cases":      [ { "title": "…", "problem": "…", "approach": "…",
                    "outcome": "…", "tech": [], "link": "…" } ],
  "skills":     [ { "group": "…", "items": [] } ],
  "beyond":     [ { "title": "…", "desc": "…", "img": "image/…" } ],
  "education":  [],
  "certs":      [],
  "research":   null
}
```

Notes on the data:

- **`education`, `certs` and `research`** render only when non-empty, so the page
  currently omits them. Fill them in and their sections appear — no code change.
- **`work[].img`** is optional. Without it the card falls back to a striped
  placeholder captioned with `shot`.
- **`cases[].link`** is optional; omit it and the card shows no "read more" link.
- Images and the CV are served from this repo (`image/`, `cv/`), so paths are
  relative.

## Run locally

```bash
python3 -m http.server 8000
```
Then open http://localhost:8000 (a server is needed because the page loads
`portfolio.json` via `fetch()`).

## Publish

This repo is a GitHub Pages user site: pushing to `main` publishes it at
`https://antonioaurel.github.io`.

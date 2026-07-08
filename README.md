# antonioaurel.github.io

Personal portfolio — projects grouped by section (Data, AI, Carnaval, Coding and more),
with global filters and per-project platform links (GitHub, Instagram, YouTube, site).

Everything is driven by [`projects.json`](projects.json): the page reads it and builds the
filter bar and section cards. To add a project, add an entry under the right section.

```json
{
  "title": "Project name",
  "type": "What it is",
  "status": "live",            // "live" | "wip" | ""  (empty = no badge)
  "summary": "One sentence.",
  "tags": ["data", "live"],    // matched by the filter chips
  "links": [                    // only the platforms it actually has
    { "platform": "github",    "href": "https://github.com/..." },
    { "platform": "instagram", "href": "https://instagram.com/..." },
    { "platform": "youtube",   "href": "https://youtube.com/..." }
  ]
}
```

Supported link platforms: `github`, `instagram`, `youtube`, `linkedin`, `web`.

## Run locally

```bash
python3 -m http.server 8000
```
Then open http://localhost:8000 (a server is needed because the page loads `projects.json`
via `fetch()`).

## Publish

This repo is a GitHub Pages user site: pushing to `main` publishes it at
`https://antonioaurel.github.io`.

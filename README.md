# nkocica-lab

Small interactive demos by @NKocica, served by GitHub Pages.

- `index.html`: the gallery. It reads `demos.json`.
- `demos/<slug>/`: one self-contained demo per folder. It needs `index.html` and `poster.png` (or a short `preview.mp4`).
- `demos.json`: `[{"slug", "title", "line", "date", "preview"}]`, newest first on the page.

Rules: static files only. No server code, no tracking, no secrets, and no API keys in any page.
Libraries are loaded from a CDN with an exact version, or vendored into the demo folder.

Publishing from nejc-home: `~/founder-studio/publish-demo.sh <folder> --title "…" --line "…"`.

# Karan Kansal — Portfolio

Personal portfolio website.

Software Engineer. Agentic AI and retrieval on top of Java and Python backends — LangChain,
LangGraph, Qdrant, Spring Boot, FastAPI. Previously Yamaha Motor Solutions, building backend
modules and REST APIs across a layered full-stack architecture.

## Built with

Plain HTML, CSS and JavaScript in a single file — no framework, no build step, no dependencies.
Project cover art is generated in-page as SVG, so the site ships with one photo and a PDF and
nothing else.

**Dark and light themes.** Dark is black through deep indigo; light is white through pale
lavender. The toggle sits in the nav (and in the mobile menu). A first visit follows the OS
setting; after that the visitor's choice is remembered in `localStorage`, and an inline
`<head>` script applies it before paint so there's no flash.

The hero runs a canvas code animation behind the whole section, repainting in the active
theme's palette. It pauses when off-screen or when the tab is hidden, and falls back to a
single static frame under `prefers-reduced-motion`.

- Responsive down to 360px, no horizontal overflow
- Keyboard accessible — project cards are buttons, `Esc` closes the expanded view
- Custom floating scrollbar; native scrolling untouched
- Circular portrait with a conic gradient ring
- Fonts: Fraunces, Inter, JetBrains Mono, with system fallbacks

## Projects featured

| Project | What it is |
|---|---|
| [PaperMind](https://github.com/iamkarankansal/Papermind) | Multi-tenant RAG application with citations — Java, Spring Boot, Spring AI, pgvector, React |
| [PDF RAG](https://github.com/iamkarankansal/PDF_RAG) | Semantic search and grounded Q&A over PDFs — Python, LangChain, OpenAI, Qdrant, FastAPI |
| [Vibe Coding Agent](https://github.com/iamkarankansal/Vibe_Coding_Agent) | Terminal AI coding agent on LangGraph — ReAct reasoning, resumable sessions |

## Contact

[Email](mailto:kkansal171@gmail.com) · [LinkedIn](https://www.linkedin.com/in/karan-kansal-866353252/) · [LeetCode](https://leetcode.com/u/kkansal171/) · [GitHub](https://github.com/iamkarankansal)

---

<details>
<summary><b>Maintenance notes</b></summary>

### Structure

```
index.html    everything — markup, styles, scripts, generated cover art
assets/       profile photo + résumé PDF
```

### Editing

- **Page text** — edit the HTML. Sections are commented and numbered.
- **Projects** — edit the `PROJECTS` array in the `<script>` block. Cards and expanded views
  both build from it, so each project is defined once. The grid is three columns on desktop,
  two on tablet, one on phone.
- **Live demo buttons** — set `demo: 'https://...'` on a project; `''` hides the button.
- **Cover art** — `ART_SETS.dark` and `ART_SETS.light` hold two gradient stops, an accent and
  a motif per project. Motifs available: `chat` (a grounded answer with its citation),
  `vectors` (a document embedded into a searched point cloud) and `terminal` (a terminal
  window above a reasoning loop).
- **Colors** — CSS variables in the `:root` block at the top; `:root[data-theme="light"]`
  right below overrides the same names. Translucent accents read from `--accent-rgb` /
  `--glow-rgb` / `--blue-rgb`, so changing the brand hue is a one-line edit.
- **Animation** — `DENSITY` (how busy) and `SPEED_MS` (how fast) in the hero animation block.

### Media

The hero photo is `assets/profile.*` — `.jpeg`, `.jpg`, `.png` and `.webp` all work, tried in
order, falling back to a drawn `KK` monogram if none is found. The frame is circular, so a
square headshot works best.

To use a real image for a project instead of the generated art, set `cover: 'assets/x.png'`
on that project; `video: 'assets/x.mp4'` overrides both.

### Deploying (GitHub Pages)

Create a **public** repo named exactly `iamkarankansal.github.io`, then:

```bash
cd <this folder>
git init -b main
git add -A
git commit -m "Portfolio site"
git remote add origin https://github.com/iamkarankansal/iamkarankansal.github.io.git
git push -u origin main
```

Repo → **Settings → Pages**, source `main` / `/ (root)`. Live at
`https://iamkarankansal.github.io` in a minute or two.

Later edits: `git add -A && git commit -m "update" && git push`.

</details>

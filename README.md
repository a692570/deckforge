# DeckForge

An AI presentation skill that generates production-quality HTML slide decks. Your agent reads the workflow, builds the slides, and exports to PPTX or PDF. You review and ship.

Requires an AI coding agent with file system access: Claude Code, Cursor, Codex CLI, Windsurf, Aider, or any agent that can read files and run scripts.

## What it does

DeckForge is a structured, multi-phase workflow. It's not a prompt template you paste into a chat window. Your agent reads `SKILL.md`, follows the phases (brief, structure, outline, HTML, images, polish, export), and writes real files to disk.

The output is a self-contained HTML file with animated slide transitions, keyboard and touch navigation, speaker notes overlay, and responsive layout. Optionally exports to PowerPoint (two paths) or PDF.

## Installation

**Claude Code, Cursor, Codex CLI, Windsurf, Aider:**

```bash
git clone https://github.com/a692570/deckforge.git
```

Point your agent at `SKILL.md` when you ask it to build a deck.

**OpenClaw / OpenCode:**

```bash
cd ~/.openclaw/skills   # or your agent's skill directory
git clone https://github.com/a692570/deckforge.git
```

## Requirements

- An AI coding agent with file system and terminal access
- Any capable LLM backend
- Python 3 + `python-pptx` for PPTX export path A (`pip3 install python-pptx`)
- Node.js + `pptxgenjs` for PPTX export path B (`npm install pptxgenjs`)
- Modern browser (Chrome/Edge/Firefox/Safari)

No additional API keys. Everything runs locally.

## Example prompts

```
"Build a 12-slide pitch deck for an AI customer support startup. Audience: Series A investors."
```

```
"Convert these notes into a technical presentation on Kubernetes autoscaling: [paste notes]"
```

```
"15-slide conference talk on the future of AI agents. Visionary tone, deep space theme."
```

```
"Create a presentation using the brand from company-deck.pptx"
"Match the style of https://linear.app for this pitch deck"
"Use our brand-guidelines.pdf to style a 10-slide launch deck"
```

## Themes

31 curated styles (11 original + 20 extended), plus Kami Warm Editorial (full CSS spec), plus custom brand import.

**Original 11:**

| Theme | Best for |
|-------|----------|
| **Modern SaaS** (default) | Pitch decks, product demos |
| Neon Cyber | Tech talks, gaming |
| Midnight Executive | Board meetings, enterprise |
| Deep Space | Keynotes, vision talks |
| Terminal Green | Engineering presentations |
| Paper & Ink | Education, storytelling |
| Swiss Modern | Design presentations |
| Soft Pastel | Marketing, community |
| Warm Editorial | Brand storytelling |
| Brutalist | Creative pitches |
| Gradient Wave | Startup pitches |

**Extended 20:** Bold Signal, Electric Studio, Creative Voltage, Dark Botanical, Notebook Tabs, Pastel Geometry, Split Pastel, Vintage Editorial, Liquid Glass Bento, Engineering Blueprint, Watercolor Map, Golden Serif Quote, Chalkboard Lesson, Exploded Layer Stack, Hyperreal Product, Summary Infographic, Cobalt Grid, 8-Bit Orbit, Raw Grid, Broadside.

**Kami Warm Editorial:** Full editorial CSS spec for print-quality, paper-like decks. Complete with CSS tokens, slide-scale rules, section header and code card components, and deck recipe rules for long decks.

Full CSS and font details in `STYLE_PRESETS.md`.

## Brand import

You can also extract a theme from existing assets instead of picking a preset:

- **From a PPTX**: The agent unzips the file, reads `theme1.xml`, and pulls out colors, fonts, and backgrounds.
- **From a website URL**: Fetches the page, extracts CSS colors and font families, builds a matching preset.
- **From a brand guidelines PDF**: Parses hex codes, typography rules, and spacing from the document.

## What's in the workflow

The SKILL.md covers the full pipeline:

1. **Pre-Flight Scoping** — 4 questions (aesthetic direction, page count, text density, motion) before writing any slide
2. **Phase 0: Brief** — audience, arc, ask, success definition
3. **Phase 1: Structure** — Pyramid Principle, assertion-evidence headings, thesis, contrast beats, Product Design Layers
4. **Phase 2: Outline** — Page Type Taxonomy, 10 Editorial Layout Types, slide count scaling
5. **Phase 3: HTML Generation** — Canvas Scale Architecture (1920x1080 fixed + letterbox), Viewport Fitting Rules, Vertical Budget Math, One Idea Per Slide, Agent Authoring Discipline
6. **Phase 4: Images & Charts** — 7 named image roles, image type taxonomy, Slide Background Image System, Image Slides Mode, Chart Anti-Patterns
7. **Phase 5: Polish & Review** — Page Rhythm Rules, Font Hierarchy (3-level rule), Color Discipline, Design Anti-Patterns ("AI Tells"), Industry Theme Constraints, Voice Guidance by Deck Type, Designer's Eye 5-Dimension Critique, Narrative Spine
8. **Phase 6: Export** — PPTX (python-pptx or pptxgenjs), PDF, Vercel deploy

Plus specialized modes: Cinematic Slide Mode, Swiss International Strict Mode, Editorial Web Deck Mode, HTML Slide Template Library (32 templates), Theme Variation Protocol, Design Philosophy School System, Speaker Notes Overlay.

## Output

- `presentation.html` - Self-contained, works offline, full animations, speaker notes (press N)
- `presentation.pptx` - Editable PowerPoint via export script
- `presentation.pdf` - Print from browser or headless Chrome
- `presentation-assets/` - Generated images, charts, diagrams

```bash
python3 scripts/pptx_export.py presentation.html --output presentation.pptx
```

## What's in the repo

```
deckforge/
├── SKILL.md              # The workflow your agent follows
├── STYLE_PRESETS.md      # 31 themes + Kami spec with full CSS
├── README.md
├── MAINTAINER.md         # How to sync from the canonical skill
├── LICENSE               # MIT
└── scripts/
    └── pptx_export.py    # PowerPoint export (Path A: python-pptx)
```

## Design principles

- Clean typography with intentional font pairings
- Plenty of whitespace
- No two consecutive slides share the same visual weight
- Content first, decoration second
- No filler copy, no generic gradients, no AI slop
- One idea per slide (hard rule, not a guideline)
- Every slide must work as a still frame (PDF/PPTX exports are static)

## Contributing

New themes, better export scripts, workflow improvements. PRs welcome.

## License

MIT. Free for personal and commercial use.

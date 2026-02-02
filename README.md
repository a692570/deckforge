# DeckForge

An AI presentation skill that generates production-quality HTML slide decks. Your agent reads the workflow, builds the slides, and exports to PPTX. You review and ship.

Requires an AI coding agent with file system access: Claude Code, Cursor, Codex CLI, Windsurf, Aider, or OpenClaw.

## What it does

DeckForge is a structured, multi-phase workflow. It's not a prompt template you paste into a chat window. Your agent reads `SKILL.md`, follows the phases (outline, content, code, polish, export), and writes real files to disk.

The output is a self-contained HTML file with animated slide transitions, keyboard and touch navigation, and responsive layout. Optionally exports to PowerPoint.

## Installation

**Claude Code, Cursor, Codex CLI, Windsurf, Aider:**

```bash
git clone https://github.com/a692570/deckforge.git
```

Point your agent at `SKILL.md` when you ask it to build a deck.

**OpenClaw:**

```bash
cd ~/.openclaw/skills
git clone https://github.com/a692570/deckforge.git presentation-maker
```

## Requirements

- An AI coding agent with file system and terminal access
- Any capable LLM backend (Claude Opus 4.5, Sonnet 4.5, GPT-5.2, Gemini 3 Pro, etc.)
- Python 3 + `python-pptx` if you want PowerPoint export (`pip3 install python-pptx`)

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

## Themes

11 built-in presets, plus custom brand import.

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

Full CSS and font details in `STYLE_PRESETS.md`.

## Brand import

You can also extract a theme from existing assets instead of picking a preset:

- **From a PPTX**: The agent unzips the file, reads `theme1.xml`, and pulls out colors, fonts, and backgrounds.
- **From a website URL**: Fetches the page, extracts CSS colors and font families, builds a matching preset.
- **From a brand guidelines PDF**: Parses hex codes, typography rules, and spacing from the document.

```
"Create a presentation using the brand from company-deck.pptx"
"Match the style of https://linear.app for this pitch deck"
"Use our brand-guidelines.pdf to style a 10-slide launch deck"
```

## Output

- `presentation.html` - Self-contained, works offline, full animations
- `presentation.pptx` - Editable PowerPoint via export script
- `presentation.pdf` - Print from browser

```bash
python3 scripts/pptx_export.py presentation.html --output presentation.pptx
```

## How the workflow runs

1. Agent reads `SKILL.md` and learns the 5-phase process
2. You describe what you need (topic, audience, tone)
3. Agent generates an outline for your review
4. Agent writes the full HTML with your chosen theme
5. Export to PPTX or PDF if needed

## What's in the repo

```
deckforge/
├── SKILL.md              # The workflow your agent follows
├── STYLE_PRESETS.md      # 11 themes with full CSS
├── README.md
├── LICENSE               # MIT
└── scripts/
    └── pptx_export.py    # PowerPoint export
```

## Design principles

- Clean typography with intentional font pairings
- Plenty of whitespace
- No two consecutive slides share the same layout
- Content first, decoration second
- No filler copy, no generic gradients

## Contributing

New themes, better export scripts, workflow improvements. PRs welcome.

## License

MIT. Free for personal and commercial use.

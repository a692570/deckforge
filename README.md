<!--
Name suggestions:
1. DeckForge — Memorable, implies crafting/creating with strength
2. SlideCraft — Artisanal, professional feel  
3. PitchKit — Modern, startup-friendly

Selected: DeckForge
-->

# DeckForge

AI presentation workflow for generating polished, production-quality HTML slide decks. Built for AI coding agents with file system access — Claude Code, Cursor, Codex CLI, Windsurf, Aider, and OpenClaw.

> **Not a prompt template.** DeckForge is a structured multi-phase workflow that reads files, generates code, runs export scripts, and writes output. It requires an AI agent with terminal and file system access.

## ✨ What You Get

- **🎨 11 Curated Themes** — From SaaS modern to cyberpunk neon to editorial elegance
- **🏢 Brand Import** — Extract styles from existing PPTXs, websites, or brand guidelines PDFs
- **📱 HTML Slides** — Full animations, keyboard navigation, responsive design
- **📊 PPTX Export** — Convert to PowerPoint with styling preserved
- **🖼️ Image Integration** — AI-generated illustrations + stock photo guidance
- **⌨️ Interactive Navigation** — Arrow keys, touch swipes, scroll wheel support
- **📝 Speaker Notes** — Hidden presenter notes (exported to PowerPoint too)
- **🎯 No "AI Slop"** — Clean, professional designs without generic gradients or filler copy

## 🚀 Installation

### Claude Code / Cursor / Codex CLI / Windsurf / Aider

Clone into your project or workspace:
```bash
git clone https://github.com/a692570/deckforge.git
```
Reference `SKILL.md` when prompting your agent. It reads the workflow, generates an outline, writes the HTML, and runs export scripts automatically.

### OpenClaw

Install as a skill:
```bash
cd ~/.openclaw/skills
git clone https://github.com/a692570/deckforge.git presentation-maker
```
The skill auto-loads. Just ask your agent to create a presentation.

## 💡 Example Prompts

```
"Create a 12-slide pitch deck for my AI customer support startup targeting Series A investors"
```

```
"Turn these notes into a technical presentation about Kubernetes autoscaling: [paste notes]"
```

```
"Make a conference talk about the future of AI agents, 15 slides, visionary tone"
```

## 📋 Requirements

**Required:**
- An AI coding agent with file system and terminal access (Claude Code, Cursor, Codex CLI, Windsurf, Aider, or OpenClaw)
- Any capable LLM backend (Claude Opus 4.5 / Sonnet 4.5, GPT-5.2, Gemini 3 Pro, etc.)

**Optional:** Python 3 with `python-pptx` for PowerPoint export:
```bash
pip3 install python-pptx
```

No external API keys beyond your LLM. The agent does all the work locally.

## 🎨 Theme Presets

| Theme | Vibe | Best For |
|-------|------|----------|
| **Modern SaaS** (default) | Clean, confident, developer-friendly | Pitch decks, product demos |
| Neon Cyber | Futuristic, techy, cutting-edge | Tech talks, gaming, crypto |
| Midnight Executive | Premium, sophisticated, corporate | Board meetings, enterprise |
| Deep Space | Inspiring, vast, visionary | Keynotes, vision presentations |
| Terminal Green | Developer-focused, hacker aesthetic | Engineering talks |
| Paper & Ink | Editorial, literary, refined | Storytelling, education |
| Swiss Modern | Precise, Bauhaus-inspired, geometric | Design presentations |
| Soft Pastel | Friendly, approachable, creative | Marketing, community talks |
| Warm Editorial | Human, photographic, magazine | Brand storytelling |
| Brutalist | Raw, bold, unconventional | Creative pitches, art talks |
| Gradient Wave | Modern SaaS, energetic | Startup pitches |
| **Custom Brand** | Your company's exact colors/fonts | Any branded presentation |

See `STYLE_PRESETS.md` for full CSS, fonts, and color codes for each theme.

### 🏢 Brand Import

Match your company's existing visual identity by importing from:

- **Existing PPTX files** — Extract colors, fonts, and backgrounds from PowerPoint themes
- **Company websites** — Pull CSS colors and typography from any URL
- **Brand guidelines PDFs** — Parse official design tokens from brand documents

**Example prompts:**
```
"Create a presentation using the brand from attached company-deck.pptx"
"Match the brand style of https://linear.app for this pitch deck"
"Use our brand-guidelines.pdf to style a 10-slide product launch deck"
```

Works with any AI that can read files or fetch URLs. No special API keys needed.

## 📤 Output Formats

Every presentation generates:

- **`presentation.html`** — Full-featured HTML with animations, works offline
- **`presentation.pptx`** — Editable PowerPoint (via export script)
- **`presentation.pdf`** — Print-ready (export from browser)

### Exporting to PowerPoint

```bash
python3 scripts/pptx_export.py presentation.html --output presentation.pptx
```

## 📁 What's Inside

```
deckforge/
├── SKILL.md              # The main workflow (give this to your AI)
├── STYLE_PRESETS.md      # 11 visual themes with CSS
├── README.md             # This file
├── LICENSE               # MIT License
└── scripts/
    └── pptx_export.py    # PowerPoint conversion utility
```

## 🎯 How It Works

1. **AI reads SKILL.md** — It learns the 5-phase workflow
2. **You describe your presentation** — Topic, audience, key messages
3. **AI generates an outline** — You approve or adjust
4. **AI writes the HTML** — Complete with your chosen theme
5. **Export to any format** — HTML, PPTX, or PDF

## 🎨 Design Philosophy

Every slide should feel like it belongs on a top-tier SaaS marketing page:

- Clean typography with intentional font pairings
- Generous whitespace — content needs room to breathe
- Varied layouts — no two consecutive slides look identical
- Content-first, minimal decoration
- No generic filler copy or "purple gradient" AI slop

## 🤝 Contributing

This is a community resource. Improvements welcome:

- New themes for `STYLE_PRESETS.md`
- Better export scripts
- Workflow improvements to `SKILL.md`

## 📄 License

MIT License — free for personal and commercial use.

---

**Made for the AI coding community** | [Report Issues](https://github.com/a692570/deckforge/issues)

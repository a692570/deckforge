<!--
Name suggestions:
1. DeckForge — Memorable, implies crafting/creating with strength
2. SlideCraft — Artisanal, professional feel  
3. PitchKit — Modern, startup-friendly

Selected: DeckForge
-->

# DeckForge

AI prompt kit for generating polished, professional HTML presentations. Works with any AI coding assistant—Claude Code, Cursor, Codex CLI, Windsurf, Aider, or just paste into ChatGPT/Claude web.

## ✨ What You Get

- **🎨 11 Curated Themes** — From SaaS modern to cyberpunk neon to editorial elegance
- **📱 HTML Slides** — Full animations, keyboard navigation, responsive design
- **📊 PPTX Export** — Convert to PowerPoint with styling preserved
- **🖼️ Image Integration** — AI-generated illustrations + stock photo guidance
- **⌨️ Interactive Navigation** — Arrow keys, touch swipes, scroll wheel support
- **📝 Speaker Notes** — Hidden presenter notes (exported to PowerPoint too)
- **🎯 No "AI Slop"** — Clean, professional designs without generic gradients or filler copy

## 🚀 Quick Start (Pick Your Path)

### Option 1: With Claude Code / Cursor / Any AI IDE

Just drop these files in your project folder and ask:
```
"Create a pitch deck about [your topic] following the workflow in SKILL.md"
```

The AI will read `SKILL.md` and `STYLE_PRESETS.md` and generate everything.

### Option 2: Standalone (ChatGPT, Claude Web, etc.)

1. Open `SKILL.md`
2. Copy the entire contents
3. Paste into your AI chat as a system prompt
4. Ask: "Create a presentation about [your topic]"

### Option 3: With OpenClaw

```bash
cd ~/.openclaw/skills  # or your OpenClaw skills path
git clone https://github.com/a692570/deckforge.git presentation-maker
```

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

**You need:** Access to any LLM (Claude, GPT-4, Gemini, etc.)

**Optional:** For PowerPoint export, install Python dependencies:
```bash
pip3 install python-pptx
```

That's it. No API keys. No complex setup.

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

See `STYLE_PRESETS.md` for full CSS, fonts, and color codes for each theme.

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

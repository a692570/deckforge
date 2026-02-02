<!--
Name suggestions:
1. DeckForge — Memorable, implies crafting/creating with strength
2. SlideCraft — Artisanal, professional feel
3. PitchKit — Modern, startup-friendly

Selected: DeckForge
-->

# DeckForge

AI-powered presentation creation for OpenClaw. Generate polished, professional slide decks from a simple topic idea with Gamma-quality output and modern design standards.

## ✨ Features

- **🤖 AI Content Planning** — Generates slide outlines tailored to your audience and goals
- **🎨 11 Curated Themes** — Professional presets from SaaS modern to cyberpunk neon
- **📱 HTML Slides** — Full animations, keyboard navigation, responsive design
- **📊 PPTX Export** — Editable PowerPoint files with preserved styling
- **🖼️ Image Integration** — AI-generated illustrations + stock photo support
- **⌨️ Interactive Navigation** — Arrow keys, touch swipes, scroll wheel support
- **📝 Speaker Notes** — Hidden presenter notes extracted to PowerPoint
- **🎯 No "AI Slop"** — Clean, professional designs without generic gradients or filler copy

## 📋 Prerequisites

### OpenClaw Setup

This is an **OpenClaw skill** that uses AI models to generate presentations. You need:

1. **OpenClaw installed** — See [OpenClaw documentation](https://github.com/openclaw) for setup
2. **AI model configured** — Claude, GPT-4, Gemini, or any model supported by OpenClaw
3. **No additional API keys** — DeckForge uses your existing OpenClaw model configuration

### PPTX Export (Optional)

To export presentations to PowerPoint format, you'll need Python 3 and the `python-pptx` library:

```bash
pip3 install python-pptx
```

The HTML output works in any modern browser with no dependencies.

## 🚀 Installation

Add DeckForge as an OpenClaw skill:

```bash
# Clone into your OpenClaw skills directory
cd ~/.openclaw/skills  # or your OpenClaw skills path
git clone https://github.com/a692570/deckforge.git presentation-maker

# Or manually copy the skill folder to your skills directory
```

The skill will be automatically discovered by OpenClaw on next startup.

## 💡 Usage Examples

### Create a Pitch Deck
```
"Create a pitch deck for my AI-powered customer support startup targeting Series A investors"
```

### Turn Notes into Slides
```
"Turn these notes into a 10-slide presentation: [paste your content here]"
```

### Style Existing Content
```
"Make a technical presentation about Kubernetes autoscaling for a DevOps conference"
```

## 🎨 Theme Presets

11 professionally designed styles included:

| Theme | Vibe | Best For |
|-------|------|----------|
| **Modern SaaS** (default) | Clean, confident, developer-friendly | Pitch decks, product demos |
| Neon Cyber | Futuristic, techy, cutting-edge | Tech talks, gaming, crypto |
| Midnight Executive | Premium, sophisticated, corporate | Board meetings, enterprise sales |
| Deep Space | Inspiring, vast, visionary | Keynotes, vision presentations |
| Terminal Green | Developer-focused, hacker aesthetic | Engineering talks, hackathons |
| Paper & Ink | Editorial, literary, refined | Storytelling, education |
| Swiss Modern | Precise, Bauhaus-inspired, geometric | Design presentations, portfolios |
| Soft Pastel | Friendly, approachable, creative | Marketing, community talks |
| Warm Editorial | Human, photographic, magazine | Brand storytelling, case studies |
| Brutalist | Raw, bold, unconventional | Creative pitches, art talks |
| Gradient Wave | Modern SaaS, energetic | Startup pitches, product launches |

See `STYLE_PRESETS.md` for full details on each theme.

## 📤 Output Formats

Every presentation generates three files:

- **`presentation.html`** — Full-featured HTML with animations, keyboard navigation, and offline capability
- **`presentation.pptx`** — Editable PowerPoint file (import into Google Slides, Keynote, or PowerPoint)
- **`presentation.pdf`** — Print-ready, email-friendly format (export from browser)

### Exporting to PPTX

```bash
python3 scripts/pptx_export.py presentation.html --output presentation.pptx
```

## 📁 File Structure

```
presentation-maker/
├── SKILL.md              # Full workflow documentation
├── STYLE_PRESETS.md      # 11 visual style presets
├── README.md             # This file
└── scripts/
    └── pptx_export.py    # PowerPoint conversion utility
```

## 🎯 Design Philosophy

**The quality bar:** Every slide should feel like it belongs on a top-tier SaaS marketing page.

- Clean typography with intentional font pairings
- Generous whitespace — content needs room to breathe
- Varied layouts — no two consecutive slides look identical
- Content-first, minimal decoration
- No generic filler copy or "purple gradient" AI slop

## 📄 License

MIT License — See LICENSE file for details.

---

**Built for OpenClaw** | [Report Issues](https://github.com/a692570/deckforge/issues)

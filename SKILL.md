---
name: presentation-maker
description: Create polished, professional HTML presentations with AI content generation, custom illustrations, and multi-format export (PPTX, PDF). Produces Gamma-quality output with modern design standards.
---

# Presentation Maker

Create stunning, presentation-ready slide decks from a simple topic idea. This skill handles everything: content planning, visual design, custom image generation, and export to multiple formats.

## Output Quality Standard

Every presentation should feel like it belongs on a top-tier SaaS marketing page. Clean, confident, minimal, developer-friendly.

---

## Quick Start

**For a new presentation:**
```
"Create a pitch deck about [topic]"
"Make a presentation on [subject] for [audience]"
```

**With your own content:**
```
"Turn these notes into slides: [paste content]"
"Style this outline as a presentation"
```

---

## The 5-Phase Workflow

### Phase 1: Content Planning

Gather the essentials before writing a single line of code.

**Required inputs:**
- **Topic** — What is this about?
- **Audience** — Who's watching? (Investors, customers, executives, technical team, general public)
- **Slide count** — Short (5-10), Medium (10-20), or Long (20+)
- **Key messages** — 3-5 things the audience must remember
- **Purpose** — Pitch deck, teaching/tutorial, conference talk, internal presentation, sales/marketing

**Output: Slide-by-Slide Outline**

Create a detailed outline with content types for each slide:

| Content Type | Use For |
|--------------|---------|
| `title` | Opening slide, section breaks |
| `content` | Standard information slides |
| `quote` | Testimonials, key statements |
| `stats` | Numbers, metrics, data points |
| `comparison` | Side-by-side contrasts |
| `image-heavy` | Visual storytelling |
| `diagram` | Processes, flows, architecture |
| `split` | Two-column layouts |
| `closing` | Call to action, final slide |

**Example outline:**
```
Slide 1: title — Company name + one-line value prop
Slide 2: content — The problem (pain points)
Slide 3: content — The solution (your product)
Slide 4: image-heavy — Product screenshot/demo
Slide 5: stats — Key metrics (users, growth, revenue)
Slide 6: comparison — Us vs. competitors
Slide 7: quote — Customer testimonial
Slide 8: diagram — How it works (3-step process)
Slide 9: content — Business model
Slide 10: closing — Call to action + contact
```

Get user approval on the outline before proceeding.

---

### Phase 2: HTML Generation (Primary Agent)

The primary agent writes the complete HTML presentation. This is too large for a sub-agent.

**Design requirements:**

1. **Varied layouts** — No two consecutive slides should look identical
2. **Typography hierarchy** — Clear distinction between headlines, subheads, body
3. **Generous whitespace** — Content needs room to breathe
4. **CSS custom properties** — All colors/fonts defined in `:root` for easy theming
5. **Image placeholders** — Mark where visuals would enhance (don't leave blank)

**HTML structure:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Presentation Title]</title>
    <link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=inter@400,500,600,700&f[]=space-grotesk@400,500,600,700">
    <style>
        :root {
            /* Colors */
            --bg-primary: #ffffff;
            --bg-dark: #0A0A0A;
            --text-primary: #1a1a1a;
            --text-secondary: #666666;
            --text-on-dark: #ffffff;
            --accent: #00E3AA;
            
            /* Typography */
            --font-display: 'Space Grotesk', sans-serif;
            --font-body: 'Inter', sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            
            /* Spacing */
            --slide-padding: 4rem;
            --content-max-width: 1200px;
            
            /* Animation */
            --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
        }
        /* ... slide styles ... */
    </style>
</head>
<body>
    <section class="slide title-slide" data-slide="1">
        <h1>Title</h1>
        <p class="subtitle">Subtitle</p>
        <!-- Speaker notes -->
        <div class="speaker-notes" style="display:none;">
            Notes for presenter...
        </div>
    </section>
    <!-- More slides... -->
    <script>
        // Navigation and animations
    </script>
</body>
</html>
```

**Layout variety examples:**

```css
/* Title slide — centered, large type */
.slide.title-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background: var(--bg-dark);
    color: var(--text-on-dark);
}

/* Content slide — left-aligned, generous padding */
.slide.content-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: var(--slide-padding);
    background: var(--bg-primary);
}

/* Split slide — two columns */
.slide.split-slide {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
    padding: var(--slide-padding);
}

/* Stats slide — big numbers */
.slide.stats-slide {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background: var(--bg-dark);
    color: var(--text-on-dark);
}
.stat-number { font-size: 4rem; font-weight: 700; color: var(--accent); }

/* Quote slide — testimonial style */
.slide.quote-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: var(--slide-padding);
    background: var(--bg-secondary);
}
blockquote { font-size: 1.5rem; font-style: italic; max-width: 800px; }

/* Image-heavy slide */
.slide.image-slide {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    padding: 0;
}
.slide.image-slide .image-container { 
    background-size: cover; 
    background-position: center;
    height: 100%;
}
```

**Anti-patterns to avoid:**
- ❌ Purple gradients on white backgrounds (AI slop)
- ❌ Generic stock photo backgrounds
- ❌ Walls of text (keep to 3-5 bullet points max)
- ❌ Identical layouts repeated
- ❌ "In today's rapidly evolving world..." copy
- ❌ Center-aligning everything
- ❌ System fonts (Inter, Roboto) without intention

---

### Phase 3: Image Generation

Fill image placeholders with appropriate visuals.

**When to use AI-generated images (nano-banana-pro):**
- Custom illustrations/diagrams
- Product mockups that don't exist yet
- Abstract concepts that need visualization
- Unique branded illustrations

**When to use stock photos (web_search):**
- Real-world scenes, people, locations
- Established product screenshots
- General business/technology imagery
- When photorealism matters

**Stock photo search queries:**
```
[topic] site:unsplash.com
[topic] professional free stock photo
[topic] business presentation pexels
```

**Image embedding options:**

1. **Base64 inline** (for small icons/illustrations):
```html
<img src="data:image/svg+xml;base64,PHN2Zy4u.">
```

2. **Relative paths** (for generated/downloaded images):
```html
<img src="assets/slide-3-diagram.png" alt="Process flow">
```

3. **CSS background** (for full-bleed images):
```css
.slide.image-slide .visual {
    background-image: url('assets/hero-image.jpg');
    background-size: cover;
}
```

**Image guidelines:**
- Use WebP or optimized PNG when possible
- Keep individual images under 500KB
- Always include descriptive alt text
- Ensure sufficient contrast with overlaid text

---

### Phase 4: Design Review (Kimi Sub-Agent)

Spawn Kimi to audit and refine the HTML.

**Review checklist:**
```
□ Visual hierarchy — Is it clear what to read first?
□ Copy quality — Punchy headlines, no filler words
□ Layout variety — No monotony between slides
□ Color consistency — Theme colors applied correctly
□ Typography — Readable sizes, proper contrast
□ Accessibility — Alt text, keyboard nav, reduced motion
□ Image quality — Appropriate, well-placed, optimized
□ Spacing — Generous but not excessive
□ Animation — Subtle, not distracting
```

**Spawn command:**
```
[ROLE: Presentation Design Auditor]

Review this HTML presentation for quality and design standards:
- File: [presentation.html]
- Target: Professional SaaS marketing page quality
- Style: [Modern SaaS / chosen style]

Check for:
1. Visual hierarchy and reading flow
2. Copy quality (eliminate AI slop phrases)
3. Layout variety across slides
4. Color/typography consistency
5. Accessibility compliance
6. Image placement and quality

Apply fixes directly to the HTML file. Focus on:
- Tightening copy (shorter headlines, punchier bullets)
- Adjusting spacing and alignment
- Ensuring consistent styling
- Adding missing alt text
- Removing any generic filler content

Return a summary of changes made.
```

---

### Phase 5: Export

Generate all deliverable formats.

**Step 5.1: PPTX Export**
```bash
python3 skills/presentation-maker/scripts/pptx_export.py [presentation].html --output [presentation].pptx
```

The upgraded exporter handles:
- Slide backgrounds from CSS
- Image embedding
- Typography sizing (h1/h2/body)
- Layout detection from CSS classes
- Speaker notes from HTML comments
- 16:9 widescreen dimensions
- Proper master slide layouts

**Step 5.2: PDF Export (via headless Chrome)**
```bash
chrome --headless --print-to-pdf=[presentation].pdf --run-all-compositor-stages-before-draw --virtual-time-budget=5000 [presentation].html
```

Or use browser automation:
1. Open HTML in browser
2. Wait for animations to settle
3. Print to PDF (landscape, 16:9)

**Step 5.3: Delivery**

Provide all three files:
- `[name].html` — Full experience with animations
- `[name].pptx` — Editable in Google Slides/PowerPoint
- `[name].pdf` — Shareable, print-ready

---

## Design Standards

**The quality bar:** Every slide should look like it belongs on a top-tier SaaS marketing page.

**Typography:**
- Clean, modern fonts (Inter, Space Grotesk)
- Clear hierarchy: Display font for headlines, body font for content
- Monospace for code/data (JetBrains Mono)

**Color:**
- Professional palettes (not neon/gradient-heavy)
- Generous use of white space
- Strategic accent colors
- High contrast for readability

**Layout:**
- Content-first, minimal decoration
- Generous whitespace
- Varied layouts per slide
- Grid-based alignment

**Animation:**
- Subtle, not flashy
- Purposeful motion (guide the eye)
- Respect `prefers-reduced-motion`

---

## Style Presets

See `STYLE_PRESETS.md` for 11 curated styles including:

1. **Modern SaaS** (default) — Clean, confident, developer-friendly
2. Neon Cyber — Futuristic, techy
3. Midnight Executive — Premium, corporate
4. Deep Space — Inspiring, visionary
5. Terminal Green — Developer/hacker aesthetic
6. Paper & Ink — Editorial, refined
7. Swiss Modern — Precise, Bauhaus-inspired
8. Soft Pastel — Friendly, approachable
9. Warm Editorial — Human, storytelling
10. Brutalist — Bold, unconventional
11. Gradient Wave — Modern SaaS, energetic

---

## File Structure

```
presentation.html          # Self-contained presentation
presentation.pptx          # PowerPoint export
presentation.pdf           # PDF export
presentation-assets/       # Images, if any
    ├── slide-1-hero.jpg
    ├── slide-4-diagram.png
    └── slide-7-logo.svg
```

---

## Speaker Notes

Include hidden speaker notes in HTML:
```html
<div class="speaker-notes" style="display:none;">
    Key points to mention:
    - Context about this metric
    - Mention the customer case study
    - Transition to next section
</div>
```

These are extracted during PPTX export and added as PowerPoint speaker notes.

---

## Navigation & Interactions

Every presentation includes:
- **Keyboard:** Arrow keys, Page Up/Down, Space
- **Touch:** Swipe left/right
- **Mouse:** Scroll wheel, click navigation
- **Progress:** Visual indicator of slide position

**Required JavaScript:**
```javascript
class SlidePresentation {
    constructor() {
        this.slides = document.querySelectorAll('.slide');
        this.current = 0;
        this.init();
    }
    
    init() {
        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowRight' || e.key === ' ') this.next();
            if (e.key === 'ArrowLeft') this.prev();
        });
        
        // Touch/swipe support
        let startX = 0;
        document.addEventListener('touchstart', (e) => startX = e.touches[0].clientX);
        document.addEventListener('touchend', (e) => {
            const diff = startX - e.changedTouches[0].clientX;
            if (Math.abs(diff) > 50) diff > 0 ? this.next() : this.prev();
        });
        
        // Scroll snap for slide container
        document.documentElement.style.scrollSnapType = 'y mandatory';
        this.slides.forEach(s => s.style.scrollSnapAlign = 'start');
    }
    
    next() { /* scroll to next slide */ }
    prev() { /* scroll to prev slide */ }
}
```

---

## Related Skills

- **nano-banana-pro** — Generate custom illustrations and diagrams
- **web_search** — Find stock photos and reference material
- **web_fetch** — Download images from Unsplash/Pexels
- **browser** — Preview presentations, print to PDF

---

## Example Sessions

### AI-Generated Pitch Deck
```
User: "Create a pitch deck for my AI startup"
→ Gather: topic, audience (investors), slides (12), key messages
→ Generate outline → Get approval
→ Write HTML with varied layouts
→ Generate custom product mockup image
→ Audit with Kimi, apply fixes
→ Export PPTX + PDF
→ Deliver all files
```

### User Content to Slides
```
User: "Turn these notes into a presentation: [content]"
→ Structure into slide outline
→ Pick style (Telnyx Modern)
→ Generate HTML
→ Add relevant stock photos
→ Export formats
→ Deliver
```

### Style Variations
```
User: "Make 3 style options for my deck"
→ Generate 3 mini preview slides with different themes
→ User picks their preferred style
→ Apply to full presentation
→ Export
```

---

## Requirements

- Python 3 with `python-pptx` library
- Modern browser (Chrome/Edge/Firefox/Safari)
- Optional: nano-banana-pro skill for AI images

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| PPTX export fails | Check `python-pptx` installed: `pip3 install python-pptx` |
| Images not in PPTX | Verify image paths are relative to HTML file |
| Fonts not loading | Check Fontshare/Google Fonts URL |
| Animations not working | Verify Intersection Observer is running |
| PDF has blank pages | Wait for animations to settle before printing |

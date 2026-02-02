# DeckForge - AI Presentation Workflow

Create stunning, presentation-ready slide decks from a simple topic idea. This document describes a complete workflow for generating professional HTML presentations with AI assistance.

## Output Quality Standard

Every presentation should feel like it belongs on a top-tier SaaS marketing page. Clean, confident, minimal, professional.

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
- **Topic** - What is this about?
- **Audience** - Who's watching? (Investors, customers, executives, technical team, general public)
- **Slide count** - Short (5-10), Medium (10-20), or Long (20+)
- **Key messages** - 3-5 things the audience must remember
- **Purpose** - Pitch deck, teaching/tutorial, conference talk, internal presentation, sales/marketing

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
Slide 1: title - Company name + one-line value prop
Slide 2: content - The problem (pain points)
Slide 3: content - The solution (your product)
Slide 4: image-heavy - Product screenshot/demo
Slide 5: stats - Key metrics (users, growth, revenue)
Slide 6: comparison - Us vs. competitors
Slide 7: quote - Customer testimonial
Slide 8: diagram - How it works (3-step process)
Slide 9: content - Business model
Slide 10: closing - Call to action + contact
```

Get user approval on the outline before proceeding.

---

### Phase 2: HTML Generation

Write the complete HTML presentation. This is the main creative work.

**Design requirements:**

1. **Varied layouts** - No two consecutive slides should look identical
2. **Typography hierarchy** - Clear distinction between headlines, subheads, body
3. **Generous whitespace** - Content needs room to breathe
4. **CSS custom properties** - All colors/fonts defined in `:root` for easy theming
5. **Image placeholders** - Mark where visuals would enhance (don't leave blank)

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
/* Title slide - centered, large type */
.slide.title-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background: var(--bg-dark);
    color: var(--text-on-dark);
}

/* Content slide - left-aligned, generous padding */
.slide.content-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: var(--slide-padding);
    background: var(--bg-primary);
}

/* Split slide - two columns */
.slide.split-slide {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
    padding: var(--slide-padding);
}

/* Stats slide - big numbers */
.slide.stats-slide {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background: var(--bg-dark);
    color: var(--text-on-dark);
}
.stat-number { font-size: 4rem; font-weight: 700; color: var(--accent); }

/* Quote slide - testimonial style */
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
- ❌ System fonts without intention

---

### Phase 3: Image Generation

Fill image placeholders with appropriate visuals.

**When to use AI-generated images:**
- Custom illustrations/diagrams
- Product mockups that don't exist yet
- Abstract concepts that need visualization
- Unique branded illustrations

**When to use stock photos:**
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

### Phase 4: Design Review

Audit and refine the HTML for quality.

**Review checklist:**
```
□ Visual hierarchy - Is it clear what to read first?
□ Copy quality - Punchy headlines, no filler words
□ Layout variety - No monotony between slides
□ Color consistency - Theme colors applied correctly
□ Typography - Readable sizes, proper contrast
□ Accessibility - Alt text, keyboard nav, reduced motion
□ Image quality - Appropriate, well-placed, optimized
□ Spacing - Generous but not excessive
□ Animation - Subtle, not distracting
```

Apply fixes directly:
- Tighten copy (shorter headlines, punchier bullets)
- Adjust spacing and alignment
- Ensure consistent styling
- Add missing alt text
- Remove generic filler content

---

### Phase 5: Export

Generate all deliverable formats.

**Step 5.1: PPTX Export**
```bash
python3 scripts/pptx_export.py [presentation].html --output [presentation].pptx
```

The exporter handles:
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

Or manually:
1. Open HTML in browser
2. Wait for animations to settle
3. Print to PDF (landscape, 16:9)

**Step 5.3: Delivery**

Provide all three files:
- `[name].html` - Full experience with animations
- `[name].pptx` - Editable in Google Slides/PowerPoint
- `[name].pdf` - Shareable, print-ready

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

## Brand Import Workflow

Extract brand tokens from existing assets and auto-generate custom style presets. This enables presentations that match your company's existing visual identity without manual color picking.

### From PPTX (PowerPoint Files)

Read an existing .pptx file to extract its theme and styling:

**Step 1: Unzip and locate theme files**
```bash
unzip -q company-deck.pptx -d pptx_extracted/
```

**Step 2: Parse theme XML (`ppt/theme/theme1.xml`)**

Look for these elements:
- `<a:clrScheme>` - Color scheme with names: `dk1`, `dk2`, `lt1`, `lt2`, `accent1` through `accent6`
- Each color has an `<a:srgbClr val="RRGGBB"/>` or `<a:sysClr val="..."/>` element
- Example extraction:
  ```xml
  <a:dk1><a:srgbClr val="1A1A1A"/></a:dk1>
  <a:accent1><a:srgbClr val="00E3AA"/></a:accent1>
  ```

**Step 3: Parse slide master for fonts (`ppt/slideMasters/slideMaster1.xml`)**

Find the font scheme:
- `<a:fontScheme>` contains `<a:majorFont>` and `<a:minorFont>`
- `<a:latin typeface="Font Name"/>` gives you the font families
- Major font = headlines/display, Minor font = body text

**Step 4: Extract background styles**

Check `ppt/slideLayouts/slideLayout1.xml` for:
- `<p:bg>` elements with solid fills, gradients, or image references
- `<a:solidFill>` with color values
- `<a:gradFill>` for gradient definitions

**Step 5: Generate custom preset**

Map extracted values to CSS variables:
- `dk1` → `--text-primary` or `--bg-dark`
- `lt1` → `--bg-primary`
- `accent1` → `--accent`
- `accent2-6` → `--accent-secondary`, etc.
- majorFont → `--font-display`
- minorFont → `--font-body`

### From Website URL

Fetch a company's website to extract their visual identity:

**Step 1: Fetch the page**
```bash
curl -s https://linear.app > website.html
```

**Step 2: Extract CSS color variables**

Look for in `<style>` blocks or linked CSS:
- `:root` CSS variables like `--color-primary`, `--brand-color`, `--accent`
- Common patterns: `primary`, `brand`, `accent`, `main`, `theme`
- Hex codes: `#RRGGBB`, `rgb()`, `hsl()`

**Step 3: Identify primary/secondary/accent colors**

Priority order for extraction:
1. Explicit brand color variables (`--color-brand`, `--primary`)
2. Button/link colors (CTAs reveal brand colors)
3. Header/navigation background
4. Logo color (if SVG or inspectable)

**Step 4: Extract font families**

From CSS `font-family` declarations:
- Body text font (most common `font-family`)
- Headline font (larger sizes, different family)
- Check Google Fonts or Fontshare URLs for exact names

**Step 5: Capture logo (optional)**

If accessible:
- Look for `<img>` with "logo" in class/name
- SVG logos in `<svg>` or `<symbol>`
- Favicon for color reference

**Step 6: Generate preset**

Use extracted colors/fonts to build a custom preset matching the website's visual identity.

### From Brand Guidelines PDF

Read a brand guidelines PDF to extract official design tokens:

**Step 1: Read the PDF**

Extract text content looking for:
- "Primary color", "Brand color", "Main color" + hex codes
- "Secondary", "Accent", "Highlight" colors
- Typography sections with font names
- Color palette tables or swatches

**Step 2: Identify color codes**

Search patterns:
- Hex codes: `#RRGGBB` or `#RGB`
- RGB values: `rgb(255, 255, 255)`
- CMYK: `C:100 M:0 Y:0 K:0` (convert to hex)
- Pantone references (use approximate hex if provided)

**Step 3: Extract typography**

Look for:
- "Primary typeface", "Brand font"
- Headline vs. body font distinctions
- Web-safe alternatives if specified

**Step 4: Note spacing/sizing rules**

If specified:
- Minimum logo clearspace
- Border/margin preferences (can inform `--slide-padding`)
- Grid systems (can inform layout approach)

**Step 5: Generate preset**

Apply extracted values to the standard preset format, respecting the brand's official guidelines.

### Output Format

Each import method produces a **Custom Brand Preset** block:

```css
/* Custom Brand Preset: [Company Name] */
:root {
    /* Extracted Color Palette */
    --bg-primary: #[from lt1 or website bg];
    --bg-secondary: #[lightened primary];
    --bg-dark: #[from dk1 or dark section];
    --text-primary: #[from dk1 or body text];
    --text-secondary: #[muted version];
    --text-on-dark: #[from lt1 or white];
    --accent: #[from accent1 or primary brand];
    --accent-secondary: #[from accent2-6];
    
    /* Extracted Typography */
    --font-display: '[majorFont]', sans-serif;
    --font-body: '[minorFont]', sans-serif;
    
    /* Derived */
    --border: rgba(0,0,0,0.1);
    --slide-padding: 4rem;
}
```

Include a comment header noting the source:
```css
/* Auto-generated from: company-deck.pptx */
/* Auto-generated from: https://linear.app */
/* Auto-generated from: brand-guidelines.pdf */
```

### Usage Examples

**Example 1: Import from PPTX**
```
"Create a presentation using the brand from attached company-deck.pptx"
```
AI actions:
1. Unzip and parse the PPTX theme XML
2. Extract color scheme and fonts
3. Generate custom preset
4. Create presentation using extracted brand

**Example 2: Import from Website URL**
```
"Match the brand style of https://linear.app for this pitch deck"
```
AI actions:
1. Fetch linear.app homepage
2. Extract CSS colors and fonts
3. Build custom preset matching Linear's aesthetic
4. Generate presentation with that styling

**Example 3: Import from Brand Guidelines PDF**
```
"Use our brand-guidelines.pdf to style a 10-slide product launch deck"
```
AI actions:
1. Read the PDF content
2. Extract official colors, fonts, and rules
3. Generate compliant custom preset
4. Create presentation following brand guidelines

---

## Style Presets

See `STYLE_PRESETS.md` for 11 curated styles including:

1. **Modern SaaS** (default) - Clean, confident, developer-friendly
2. Neon Cyber - Futuristic, techy
3. Midnight Executive - Premium, corporate
4. Deep Space - Inspiring, visionary
5. Terminal Green - Developer/hacker aesthetic
6. Paper & Ink - Editorial, refined
7. Swiss Modern - Precise, Bauhaus-inspired
8. Soft Pastel - Friendly, approachable
9. Warm Editorial - Human, storytelling
10. Brutalist - Bold, unconventional
11. Gradient Wave - Modern SaaS, energetic

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

## Example Sessions

### AI-Generated Pitch Deck
```
User: "Create a pitch deck for my AI startup"
→ Gather: topic, audience (investors), slides (12), key messages
→ Generate outline → Get approval
→ Write HTML with varied layouts
→ Generate custom product mockup image
→ Audit and apply fixes
→ Export PPTX + PDF
→ Deliver all files
```

### User Content to Slides
```
User: "Turn these notes into a presentation: [content]"
→ Structure into slide outline
→ Pick style (Modern SaaS)
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

- Python 3 with `python-pptx` library (for PPTX export)
- Modern browser (Chrome/Edge/Firefox/Safari)

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| PPTX export fails | Check `python-pptx` installed: `pip3 install python-pptx` |
| Images not in PPTX | Verify image paths are relative to HTML file |
| Fonts not loading | Check Fontshare/Google Fonts URL |
| Animations not working | Verify Intersection Observer is running |
| PDF has blank pages | Wait for animations to settle before printing |

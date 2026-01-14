---
name: pptx
description: Create beautiful ASI-branded presentations using HTML templates and AI-generated images. Workflow takes you from idea to polished PowerPoint.
---

# ASI Presentation Builder

Create professional, on-brand presentations using a structured workflow:
**Idea -> Plan -> Images -> Slides -> PPTX**

## Quick Start

```bash
# User request example:
"Create a presentation about our cloud migration services"
```

## Workflow Overview

### Phase 1: Plan the Presentation

Create a markdown plan file that outlines the entire presentation:

```markdown
# Cloud Migration Services

## Slide 1: Title
- Title: "Cloud Migration Made Simple"
- Subtitle: "ASI Solutions - Your Partner in Digital Transformation"
- Template: title
- Image: dark wave background

## Slide 2: The Challenge
- Heading: "Why Businesses Struggle with Cloud Migration"
- Points:
  - Complexity: Legacy systems create migration barriers
  - Risk: Downtime and data loss concerns
  - Skills: Internal expertise gaps
- Template: content-single
- Image: none

## Slide 3: Our Approach
- Heading: "The ASI Methodology"
- Col1: "Assess" - Comprehensive audit of current infrastructure
- Col2: "Migrate" - Phased migration with zero downtime
- Template: two-column
- Image: none

## Slide 4: Results
- Heading: "Proven Results"
- Stats:
  - 99.9% uptime during migrations
  - 40% cost reduction average
  - 200+ successful migrations
- Template: stats
- Image: none

## Slide 5: Close
- Title: "Ready to Transform?"
- Subtitle: "contact@asi.co.nz | 0800 ASI NZL"
- Template: title
- Image: dark wave background
```

### Phase 2: Generate Images

For slides requiring custom images, generate them using Google Gemini:

**MANDATORY**: Read [image-generation.md](image-generation.md) for ASI brand prompts.

Example workflow:
1. Identify slides needing images (backgrounds, hero shots, icons)
2. Use brand-approved prompts from image-generation.md
3. Generate via Gemini API
4. Save to `outputs/[name]/images/`

### Phase 3: Build HTML Slides

Use the templates in `templates/` as starting points:

| Template | Use Case |
|----------|----------|
| `title.html` | Opening and closing slides |
| `content-single.html` | Bullet points, single column |
| `two-column.html` | Comparisons, before/after |
| `stats.html` | Key metrics, numbers |

**Process:**
1. Copy appropriate template
2. Replace `{{PLACEHOLDER}}` values with actual content
3. Customize colors/layout as needed
4. Save to `outputs/[name]/slides/slide-XX.html`

### Phase 4: Convert to PowerPoint

Use `html2pptx` or PptxGenJS to convert HTML slides to .pptx:

```javascript
// Using PptxGenJS
import PptxGenJS from 'pptxgenjs';

const pptx = new PptxGenJS();
pptx.layout = 'LAYOUT_16x9';

// Add slides from HTML...
// IMPORTANT: Never use # prefix with hex colors - causes corruption
// Use: "00A3A3" not "#00A3A3"

await pptx.writeFile({ fileName: 'presentation.pptx' });
```

## Design System Reference

**MANDATORY**: Read [design-system.md](design-system.md) before creating any slides.

### Quick Reference

| Element | Value |
|---------|-------|
| Primary Color | `00A3A3` (ASI Teal) |
| Dark Background | `1A1A2E` |
| Font | Arial, Helvetica |
| Title Size | 44pt |
| Body Size | 18pt |
| Aspect Ratio | 16:9 (720pt x 405pt) |
| Safe Margins | 36pt |

### Color Rules
- Dark slides: Teal (#00A3A3) text on dark (#1A1A2E) background
- Light slides: Dark (#1A1A2E) text on white, teal accents
- Never use more than 3 colors per slide

## Output Structure

```
outputs/
└── [presentation-name]/
    ├── plan.md              # Presentation plan
    ├── images/              # Generated images
    │   ├── bg-dark.png
    │   └── hero-01.png
    ├── slides/              # HTML slides
    │   ├── slide-01.html
    │   └── slide-02.html
    └── [name].pptx          # Final PowerPoint
```

## Checklist

Before delivering:
- [ ] All slides follow ASI design system
- [ ] Colors use correct hex values (no # prefix in PptxGenJS)
- [ ] Images have proper negative space for text
- [ ] Text is readable (sufficient contrast)
- [ ] Consistent typography throughout
- [ ] ASI logo on title and closing slides
- [ ] No more than 6 bullet points per slide
- [ ] Slide numbers on content slides

## Dependencies

Required tools:
- Node.js (for PptxGenJS)
- Google API key (for image generation)

Install:
```bash
npm install pptxgenjs
```

## Examples

### Minimal Presentation (3 slides)
```
1. Title slide (dark background)
2. Key points (light, bullets)
3. Close/CTA (dark background)
```

### Standard Presentation (8-10 slides)
```
1. Title
2. Agenda/Overview
3-4. Problem/Challenge
5-6. Solution/Approach
7. Results/Stats
8. Case Study
9. Team/About
10. Close/CTA
```

### Detailed Presentation (15+ slides)
```
1. Title
2. Agenda
3-5. Context/Background
6-9. Main Content Sections
10-12. Supporting Evidence
13. Summary
14. Next Steps
15. Close/CTA
```

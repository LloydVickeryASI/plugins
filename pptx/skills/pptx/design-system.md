# ASI Design System for Presentations

This document defines the visual language for ASI-branded presentations.

## Color Palette

### Primary Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| ASI Teal | `00A3A3` | 0, 163, 163 | Primary brand color, headings, CTAs |
| ASI Dark | `1A1A2E` | 26, 26, 46 | Dark backgrounds, text |
| ASI White | `FFFFFF` | 255, 255, 255 | Light backgrounds, reversed text |

### Supporting Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Soft Teal | `E6F7F7` | 230, 247, 247 | Light backgrounds, highlights |
| Deep Navy | `0D0D1A` | 13, 13, 26 | Extra dark backgrounds |
| Cool Gray | `6B7280` | 107, 114, 128 | Secondary text, captions |
| Light Gray | `F3F4F6` | 243, 244, 246 | Subtle backgrounds |

### Accent Colors (use sparingly)
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Success Green | `10B981` | 16, 185, 129 | Positive indicators |
| Warning Amber | `F59E0B` | 245, 158, 11 | Warnings, highlights |
| Error Red | `EF4444` | 239, 68, 68 | Errors, critical items |

## Typography

### Web-Safe Font Stack
```css
/* Headings */
font-family: Arial, Helvetica, sans-serif;
font-weight: 700;

/* Body */
font-family: Arial, Helvetica, sans-serif;
font-weight: 400;

/* Monospace (code) */
font-family: Courier New, monospace;
```

### Type Scale
| Element | Size (pt) | Weight | Line Height |
|---------|-----------|--------|-------------|
| Title | 44 | Bold | 1.1 |
| H1 | 36 | Bold | 1.2 |
| H2 | 28 | Bold | 1.2 |
| H3 | 22 | Bold | 1.3 |
| Body | 18 | Regular | 1.5 |
| Caption | 14 | Regular | 1.4 |
| Small | 12 | Regular | 1.4 |

## Layout

### Slide Dimensions
- **Aspect Ratio:** 16:9
- **Width:** 720pt
- **Height:** 405pt
- **Safe Margins:** 36pt on all sides

### Grid System
- 12-column grid
- 24pt gutters
- Content area: 648pt x 333pt

## Slide Templates

### 1. Title Slide
- Large centered title
- Subtitle below
- ASI logo bottom-right
- Wave background or solid teal

### 2. Section Divider
- Large section number or icon
- Section title
- Teal background with wave pattern

### 3. Content - Single Column
- H2 heading
- Body text
- Optional image right

### 4. Content - Two Column
- H2 heading
- Two equal columns
- Good for comparisons

### 5. Image Full
- Full-bleed image
- Optional text overlay
- Use for impact

### 6. Quote
- Large quote marks
- Quote text
- Attribution
- Teal accent

### 7. Stats/Numbers
- 2-4 large statistics
- Supporting text below each
- Great for impact data

### 8. Timeline
- Horizontal or vertical timeline
- 3-5 milestones
- Dates and descriptions

### 9. Team/People
- Photo circles
- Names and titles
- 3-4 per slide

### 10. Closing/CTA
- Key message
- Contact information
- ASI logo prominent

## Image Generation Guidelines

When generating images for slides, use these prompts:

### Professional Photography Style
```
Professional business photography, clean composition with negative space
for text overlay in [position]. [Subject description]. Soft studio lighting,
shallow depth of field. Color palette: teal (#00A3A3) and dark navy (#1A1A2E)
accents. 16:9 aspect ratio, high resolution.
```

### Abstract/Background Style
```
Abstract digital background with flowing wave patterns in teal (#00A3A3)
gradient to dark navy (#1A1A2E). Subtle geometric shapes, modern tech feel.
Soft glow effects, minimalist design. Large negative space for text.
16:9 aspect ratio.
```

### Icon/Diagram Style
```
Clean minimalist icon of [subject] in flat design style. Teal (#00A3A3)
on white or dark navy (#1A1A2E) background. Thick consistent line weight,
rounded corners, modern tech aesthetic. Centered composition, square format.
```

## CSS Variables

```css
:root {
  /* Colors */
  --asi-teal: #00A3A3;
  --asi-dark: #1A1A2E;
  --asi-white: #FFFFFF;
  --asi-soft-teal: #E6F7F7;
  --asi-gray: #6B7280;
  --asi-light-gray: #F3F4F6;

  /* Typography */
  --font-heading: Arial, Helvetica, sans-serif;
  --font-body: Arial, Helvetica, sans-serif;

  /* Spacing */
  --slide-width: 720pt;
  --slide-height: 405pt;
  --margin: 36pt;
  --gutter: 24pt;
}
```

## Do's and Don'ts

### Do
- Use plenty of white space
- Stick to 2-3 colors per slide
- Use high-contrast text
- Keep text minimal (6 words per line, 6 lines per slide max)
- Use the wave pattern for brand recognition

### Don't
- Use more than 2 fonts
- Cram too much content on one slide
- Use low-contrast color combinations
- Use clip art or generic stock photos
- Forget the ASI logo on key slides

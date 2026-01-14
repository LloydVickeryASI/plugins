# Image Generation for Presentations

Generate on-brand images using Google Gemini's image generation capabilities.

## Using Google GenAI

### Via Gemini API (Recommended)

Generate images using the Gemini 2.0 Flash model with image generation enabled:

```bash
# Set your API key
export GOOGLE_API_KEY="your-api-key"

# Generate via curl
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash-exp:generateContent?key=$GOOGLE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "contents": [{
      "parts": [{"text": "Generate an image: Professional abstract background with flowing teal (#00A3A3) wave patterns on dark navy (#1A1A2E). Modern tech aesthetic, large negative space for text overlay. 16:9 aspect ratio."}]
    }],
    "generationConfig": {
      "responseModalities": ["image", "text"]
    }
  }'
```

### Via Imagen 3

For higher quality images, use Imagen 3:

```bash
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/imagen-3.0-generate-002:predict?key=$GOOGLE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "instances": [{
      "prompt": "Your prompt here"
    }],
    "parameters": {
      "sampleCount": 1,
      "aspectRatio": "16:9"
    }
  }'
```

## ASI Brand Prompts

### Slide Background - Dark Theme
```
Abstract digital background with elegant flowing wave patterns.
Color palette: teal gradient (#00A3A3) transitioning to deep navy (#1A1A2E).
Subtle particle effects and soft glow. Modern, sophisticated tech aesthetic.
Large negative space in center-right for text overlay.
16:9 aspect ratio, 1920x1080 resolution.
```

### Slide Background - Light Theme
```
Clean minimalist abstract background with soft teal (#00A3A3) wave accents
on pure white. Subtle geometric shapes, professional business aesthetic.
Very light, airy feel with generous negative space.
16:9 aspect ratio.
```

### Hero Image - Technology
```
Professional photography of modern server room or data center.
Cool blue and teal lighting (#00A3A3 accent), shallow depth of field.
Clean, organized cables and equipment. Soft bokeh in background.
Corporate tech aesthetic, no visible brand logos.
16:9 aspect ratio, high resolution.
```

### Hero Image - Team/Business
```
Professional corporate photography of diverse business team in modern office.
Natural lighting with teal accent lighting. Shallow depth of field.
Subjects engaged in collaborative discussion. Clean, contemporary setting.
Warm but professional atmosphere. 16:9 aspect ratio.
```

### Icon Style
```
Flat design icon of [SUBJECT] in minimalist style.
Teal (#00A3A3) on transparent or white background.
Consistent 4px stroke weight, rounded corners, modern tech aesthetic.
Simple geometric shapes, no gradients. Square format, 512x512px.
```

### Diagram/Infographic Background
```
Clean white background with subtle teal (#00A3A3) geometric grid pattern.
Very light opacity (10-15%), modern blueprint aesthetic.
Professional technical drawing feel. Negative space for overlaid content.
16:9 aspect ratio.
```

## Workflow

1. **Plan slide content** - Determine which slides need custom images
2. **Select prompt template** - Choose from ASI brand prompts above
3. **Customize prompt** - Add specific subject matter details
4. **Generate image** - Use Gemini API or Imagen 3
5. **Save to outputs** - Download and save to `outputs/[presentation-name]/images/`
6. **Integrate** - Reference in HTML templates or insert into PPTX

## Output Directory Structure

```
outputs/
└── my-presentation/
    ├── images/
    │   ├── slide-01-background.png
    │   ├── slide-03-hero.png
    │   └── slide-07-diagram.png
    ├── slides/
    │   ├── slide-01.html
    │   ├── slide-02.html
    │   └── ...
    └── my-presentation.pptx
```

## Tips

- **Negative space**: Always request space for text overlay
- **Brand colors**: Include hex codes (#00A3A3, #1A1A2E) explicitly
- **Aspect ratio**: Always specify 16:9 for slides
- **Iterate**: Use multi-turn refinement for best results
- **Resolution**: Request "high resolution" or specific dimensions

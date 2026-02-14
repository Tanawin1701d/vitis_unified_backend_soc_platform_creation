# Image Guide for Tutorial

## How to Add Images to the Tutorial

### Supported Image Formats
- `.jpg` - JPEG images (best for photos)
- `.png` - PNG images (best for diagrams, screenshots)
- `.gif` - Animated GIFs
- `.svg` - Vector graphics (scalable)

### Adding Images to Your Tutorial

Place your image files in this `images/` directory, then reference them in the markdown:

```markdown
![Alt Text](./images/filename.jpg)
*Figure 1: Description of the image*
```

### Example Structure

```
tutorial/
├── README.md
└── images/
    ├── zcu102-board.jpg
    ├── connections.png
    ├── vivado-install.jpg
    ├── block-design.png
    └── troubleshooting-diagram.svg
```

### Image Recommendations

| Type | Recommendation | Example |
|------|-----------------|---------|
| **Photos** | Use JPG, 800-1200px width | Hardware connections |
| **Diagrams** | Use PNG or SVG | Block designs, flow charts |
| **Screenshots** | Use PNG | Software UI, terminal output |
| **Logos** | Use PNG or SVG | Company/product logos |

### Markdown Image Syntax

Basic Image:
```markdown
![Description](./images/image.jpg)
```

With Figure Caption:
```markdown
![ZCU102 Board](./images/zcu102-board.jpg)
*Figure 1: Xilinx ZCU102 Evaluation Board*
```

Multiple Images in a Row (using HTML):
```html
<div>
  <img src="./images/image1.jpg" width="45%" />
  <img src="./images/image2.jpg" width="45%" />
</div>
```

### Image Quality Guidelines

- **Resolution**: 800px - 1200px for web viewing
- **File Size**: Keep under 500KB for faster loading
- **Format**: Use appropriate format for image type
- **Alt Text**: Always include descriptive alt text for accessibility

### Optimization Tips

1. Compress images before adding:
   ```bash
   # Using ImageMagick
   convert input.jpg -quality 85 -resize 1000x1000 output.jpg
   ```

2. Use consistent image dimensions
3. Add clear captions below images
4. Reference images in text ("See Figure 1 below")

---

## Current Images Needed for Tutorial

The README.md references these images. Add them to this directory:

- [ ] `zcu102-board.jpg` - Front view of the ZCU102 board
- [ ] `connections.png` - Power and USB connection diagram
- [ ] `vivado-install.jpg` - Screenshot of successful Vivado installation
- [ ] `block-design.png` - Example block design in Vivado

Add your images here and the markdown will automatically reference them!

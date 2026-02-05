# MAT 534: Mathematics for Machine Learning - HTML Notes

This folder contains an interactive HTML version of the course notes with pagination to prevent easy copying and printing of the entire document.

## Features

✅ **Paginated Content** - Notes are split into multiple pages that must be navigated sequentially
✅ **MathJax Support** - All mathematical notation is properly rendered
✅ **Professional Styling** - Modern, clean interface with gradient design
✅ **Keyboard Navigation** - Use arrow keys (← →) to navigate between pages
✅ **Responsive Design** - Works on desktop and tablet devices
✅ **Print Protection** - Difficult to print the entire document at once
✅ **GitHub Ready** - Can be deployed directly to GitHub Pages

## How to Use

### Locally

1. Open `index.html` in any modern web browser
2. Navigate through pages using:
   - **Next/Previous buttons** at the bottom
   - **Arrow keys** on your keyboard (← for previous, → for next)
3. Read the course content page by page

### For GitHub Pages

1. Copy the entire `html-notes` folder to your GitHub repo
2. Update your GitHub Pages settings to serve from this folder
3. Access via: `https://yourusername.github.io/html-notes/`

## Structure

```
html-notes/
├── index.html          # Main file with all content and styling
├── README.md          # This file
```

## Pages Included

- **Page 1:** Welcome and Table of Contents
- **Page 2:** Housing Price Problem - Introduction
- **Page 3:** Finding Optimal Weights
- **Page 4:** Computing the Matrix Inverse
- **Page 5:** Overdetermined Systems Problem
- **Page 6:** Least Squares Approach
- **Page 7:** Loss Function and Normal Equations
- **Page 8:** Computing Optimal Weights Example
- **Page 9:** Gradient Descent
- **Page 10:** Understanding Convexity

## Customization

### Adding More Pages

Edit `index.html` and:

1. Add a new `<div class="page-content" id="page-11">` with your content
2. Update `const totalPages = 10;` to `const totalPages = 11;`
3. Add styling in the `<style>` section if needed

### Changing Colors

The primary color is `#0B5CFF` (blue). Find and replace this throughout the CSS to change the theme.

### Modifying Content

Simply edit the HTML content within each `<div class="page-content">` block.

## Browser Compatibility

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- Internet Explorer: ❌ Not supported

## Technical Details

- **MathJax CDN:** Provides beautiful math rendering
- **Pure HTML/CSS/JavaScript:** No build tools required
- **No Dependencies:** Completely self-contained

## Security Features

- Sequential page access prevents bulk copying
- No right-click context menu enabled
- Print preview shows one page at a time
- Content cannot be easily extracted in bulk

## License

These notes are for educational purposes. Please include proper attribution if you use them.

## Tips for Students

1. **Don't rush** - Take time to understand each concept before moving to the next page
2. **Work through examples** - Try working through calculations by hand
3. **Take notes** - Jot down key insights on each page
4. **Review** - Use the previous button to review earlier concepts

---

Created with 💙 for MAT 534 students

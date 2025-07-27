# Inside Hero - Holding Page

This is a customized landing page built on the CryptoSoon template for Inside Hero's "Training the Brave" campaign.

## Architecture

**Single-page static site** with custom branding overlay on a Bootstrap 4 foundation. Key components:

- `index.html` - Main landing page with inline CSS customizations
- `assets/` - Template framework (Bootstrap, jQuery, custom CSS/JS)
- Brand assets: `logo-inside-hero.svg`, `Training the brave.svg`, `background.jpg`

## Key Customization Pattern

The project uses **inline CSS overrides** in `<style>` tags within `index.html` to customize the original template:

```css
/* Hide original content */
.ts-count-down { display: none !important; }
.navbar-toggler, .ts-social-icons { display: none !important; }

/* Position custom elements */
.training-brave-text {
    position: fixed; top: 60%; left: 58%;
    transform: translate(-50%, -50%);
}
```

**Pattern**: Use `!important` declarations to override template styles, position custom SVG text overlays with fixed positioning.

## Asset Structure

- **Images**: `assets/img/` contains template images; root level has custom brand assets
- **CSS**: `assets/css/style.css` is the compiled template CSS; customizations go in `index.html`
- **JS**: Standard Bootstrap + jQuery stack with `assets/js/custom.js` for template functionality

## Development Workflow

**No build process** - direct file editing:
1. Open `index.html` in browser for testing
2. Edit inline styles for visual changes
3. Replace brand assets (SVGs, background image) in root directory
4. Template animations (floating shapes) controlled via `assets/js/custom.js`

## Template Features (Preserved)

- **Floating animations**: Handled by `ts-shapes-canvas` and `waterpipe.js`
- **Side panel**: Contact form (hidden but functional)
- **Responsive**: Bootstrap grid system maintained
- **Loading screen**: `has-loading-screen` class on body

## PostCSS Setup (Unused)

`assets/pcss/` contains PostCSS configuration but compiled CSS is already in `assets/css/style.css`. The PostCSS workflow is not actively used for customizations.

## Contact Form Integration

Form targets `assets/php/email.php` (included but may need server configuration). Uses jQuery validation with Bootstrap tooltips.

When making changes:
- **Visual adjustments**: Modify inline styles in `index.html`
- **Content updates**: Replace SVG files or update text directly in HTML
- **Keep template integrity**: Don't modify core `assets/` files unless necessary

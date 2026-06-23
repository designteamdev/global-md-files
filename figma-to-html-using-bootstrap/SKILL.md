---
name: figma-to-html-using-bootstrap
description: Convert Figma designs into production-ready responsive HTML5 and Bootstrap pages. Use when Codex is asked to implement, recreate, or update a Figma design as static HTML/CSS using Bootstrap, especially when it must follow an existing project's HTML structure, style.css conventions, local images folder, SEO metadata, accessibility requirements, and desktop/tablet/mobile responsive behavior.
---

# Figma To HTML Using Bootstrap

## Core Workflow

1. Review project files before writing code:
   - Existing HTML files for structure, naming convention, section hierarchy, comments, and reusable patterns.
   - Existing Bootstrap implementation.
   - Existing `style.css` conventions.
   - Figma design sections, content order, typography, spacing, colors, imagery, and responsive behavior.
   - Existing local assets, images, icons, and content.

2. Convert the Figma design into semantic HTML5 + Bootstrap:
   - Follow the existing HTML file structure exactly.
   - Keep the content hierarchy and section order identical to the Figma design.
   - Maintain content consistency throughout the page.
   - Do not change content unless required for valid, accessible HTML.
   - Reuse existing section structures when similar sections already exist.
   - Use common section spacing first. If a section needs different padding, add an extra class and override that padding.
   - Use anchor tags for links and button-like links: `<a href=""></a>`. Do not use `<button>` in place of an anchor.

3. Implement SEO-friendly, accessible structure:
   - Use `<!DOCTYPE html>` and `<html lang="en">`.
   - Include `title`, `description`, `keywords`, `viewport`, and `canonical` when applicable.
   - Use semantic elements such as `header`, `nav`, `main`, `section`, `article`, `aside`, and `footer`.
   - Use only one `h1` per page.
   - Maintain proper `h2` and `h3` hierarchy.
   - Add meaningful image `alt` text.
   - Use accessible form labels.
   - Maintain proper contrast and keyboard-friendly markup.

## Bootstrap Rules

- Use only Bootstrap Grid System and `container`.
- Do not use Bootstrap for other purposes.
- Do not use Bootstrap utility classes.
- Avoid Bootstrap classes that contain `!important` in Bootstrap CSS. Use custom classes instead.
- Desktop, tablet, and mobile responsive layouts are mandatory.

## CSS Rules

- Put all custom CSS in `style.css`.
- Do not use inline CSS.
- Do not use `<style>` tags in HTML.
- Define colors, fonts, spacing, and reusable values as CSS variables in `:root`.
- Keep CSS organized section-wise.
- Mark major sections with comments, such as:

```html
<!-- Hero Section -->
<!-- Features Section -->
<!-- Testimonial Section -->
<!-- Footer -->
```

- Match the Figma design as closely as possible:
  - Font family
  - Font size
  - Font weight
  - Line height
  - Letter spacing
  - Text transform
  - Colors
  - Background colors
  - Border radius
  - Shadows
  - Padding
  - Margin
  - Gap
  - Section spacing
  - Card spacing
  - Component alignment
  - Button styles
  - Form styles
  - Hover states
  - Responsive behavior
- Avoid `vw` and `rem` unless the user specifically asks for them.
- Avoid classes on inline text elements such as `p`, `span`, `h1`, `h2`, `h3`, `h4`, `h5`, and `h6`; style through parent classes where practical.
- Use inline-element classes only when necessary.
- Write readable, maintainable custom CSS.
- Remove unused CSS.
- Avoid `!important`; use stronger selectors or multiple classes first. Use `!important` only when truly necessary.
- If the same section needs different styling on different pages, create a distinct section class name.
- Keep all media queries at the end of the file.

## Reusable Components

- Reuse HTML structures and CSS classes when multiple sections have similar layouts.
- Avoid duplicate code.
- Follow the project's current class naming and code pattern.

## Sliders And Animation

- Use third-party CDNs for sliders, animation, and other interactive features when needed.
- Use GSAP and ScrollTrigger for section reveal animations or letter animations only when necessary.
- Use Slick Slider for regular designed sliders.
- Use Swiper for specially designed sliders.
- Use Splide.js for marquee-type sliders.

## Image Handling Rules

Use only images from the project's local images folder.

Never use:

```html
http://localhost:3845
https://...
Figma image URLs
Base64 images
Placeholder images
Stock images from web
Generated images with AI
```

Use this image path format everywhere:

```html
<img src="images/about-img.png" alt="About Image">
```

If the Figma design includes an image that is not already in the local images folder, stop and ask for the missing asset instead of using remote, placeholder, stock, base64, or AI-generated imagery.

Match image position, size, aspect ratio, alignment, cropping, object fit, and spacing to the Figma design.

## Responsive Targets

Verify the implementation at:

- Desktop: `1920px`, `1440px`, `1366px`, `1280px`
- Tablet: `1024px`, `768px`
- Mobile: `575px`, `480px`, `360px`

Ensure:

- Proper stacking
- Responsive typography
- Responsive spacing
- No layout breaking
- No horizontal scrolling
- No incoherent overlap

## Output Standard

Deliver:

1. Complete HTML file.
2. Complete `style.css` file.
3. Responsive Bootstrap implementation.
4. Pixel-perfect Figma matching.
5. SEO-friendly structure.
6. Accessible markup.
7. Clean, maintainable, production-ready code.

# Additional Mandatory Implementation Rules

## Figma Accuracy (Highest Priority)

The final HTML implementation must match the provided Figma design as closely as possible.

Do NOT approximate layouts.

Follow exactly:

* Section order
* Content hierarchy
* Typography
* Font family
* Font size
* Font weight
* Line height
* Letter spacing
* Colors
* Spacing
* Margin
* Padding
* Grid structure
* Border radius
* Shadows
* Hover states
* Alignment
* Component sizing
* Image proportions
* Desktop and mobile behavior

The final output should visually match the Figma design with pixel-perfect accuracy.

If any design inconsistency appears between existing HTML and Figma, prioritize maintaining the existing project structure while reproducing the Figma layout as accurately as possible.

---

## HTML & Component Rules

* Follow the existing project HTML structure and naming conventions.
* Reuse existing components whenever possible.
* Do not create unnecessary wrappers.
* Keep markup clean and semantic.
* Maintain scalable architecture.

---

## CSS Rules

* Put all custom styles inside:

```text
style.css
```

* Use CSS variables for:

  * colors
  * typography
  * spacing
  * radius
  * transitions

* Keep styles modular and section-wise.

* Avoid duplicated CSS.

* Keep media queries grouped at the end.

---

## JavaScript Rules (Mandatory)

All custom JavaScript must be placed inside:

```text
common.js
```

Do NOT place custom scripts inside HTML pages unless specifically required.

Requirements:

* Use Vanilla JavaScript by default.
* Use jQuery only when necessary.
* Write reusable functions.
* Validate elements before execution.
* Keep functions modular.
* Avoid duplicate event listeners.
* Use event delegation where applicable.
* Maintain clean naming conventions.

Example:

```javascript
const element =
document.querySelector(
'.selector'
);

if(element){
// functionality
}
```

---

## Interaction & Animation Rules

Every JavaScript interaction should feel smooth and polished.

Apply smooth behavior where appropriate:

* smooth transitions
* smooth scrolling
* fade effects
* subtle transforms
* smooth open/close states
* hover transitions
* stagger animations
* loading transitions

Preferred tools:

* CSS transitions
* GSAP
* ScrollTrigger

Avoid:

* sudden jumps
* abrupt state changes
* excessive animations
* laggy interactions

Animations should improve UX and must not reduce performance.

---

## Functionality Rules

Implement functionality whenever required by design:

Examples:

* sliders
* tabs
* accordions
* filtering
* modals
* tooltips
* counters
* forms
* menus
* animations
* interactions

Use existing project patterns first before creating new implementations.

All functionality should feel production-ready.

---

## Final Output Expectation

Deliver:

1. Pixel-perfect HTML
2. Responsive implementation
3. Production-ready CSS
4. Optimized JS inside common.js inside the js folder
5. Smooth interactions
6. Maintainable structure
7. Clean reusable code

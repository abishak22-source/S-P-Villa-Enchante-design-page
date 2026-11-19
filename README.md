# S&P Villa Enchante —  Guide

For most design changes, edit `index.html` and `css/style.css`. The JavaScript required for the existing menu, enquiry form, gallery, map, and plan viewer is embedded at the bottom of `index.html`; you do not need to edit it for normal layout or style changes.

## Project structure

```text
S&P-Villa-Enchante/
|-- index.html       Page sections, editable content, and built-in behavior
|-- css/
|   `-- style.css    Colors, layout, glass effects, responsive styles, and motion
|-- images/          Project photos, logos, icons, and site plan
`-- README.md        This guide
```

Each page section in `index.html` starts with a descriptive HTML comment. Search for the section ID or comment name to find the relevant markup.

## Page sections and where to edit

| Page area | HTML ID/class | Common edits |
|---|---|---|
| Header and menu | `#header`, `.nav`, `#drawer` | Navigation labels and links |
| Hero | `#home`, `.kelo__art` | Background and campaign image paths |
| Enquiry form | `#enquiry` | Field labels and visible structure; preserve the form IDs |
| Overview | `#overview` | Section layout and images; copy is in the `window.SITE` data block near the bottom of `index.html` |
| About | `#about` | Section layout; copy is in `window.SITE.about` |
| Statement | `#statement` | Decorative title text |
| Features | `#features` | Section heading/layout; cards are in `window.SITE.features` |
| Amenities | `#amenities` | Section structure; content is in `window.SITE.amenities` |
| Gallery | `#gallery` | Gallery container; photos are in `window.SITE.gallery` |
| Floor plans | `#floorplans` | Site plan image and viewer controls |
| Master plan | `#masterplan` | Image/layout; copy is in `window.SITE.masterPlan` |
| Location | `#location` | Map/layout; text and map search are in `window.SITE.location` |
| Specifications | `#specifications` | Section layout; list is in `window.SITE.specifications` |
| Contact | `#contact` | Section layout; cards are in `window.SITE.contact` |
| Footer | `.footer` | Footer text and logo |

Dynamic cards and paragraphs are built from the `window.SITE` data block in `index.html`. If you edit that block, change only the text or image value and keep its quotes and commas. For layout changes, edit the matching section markup and CSS instead.

## CSS editing guide

Open `css/style.css` and search for the selector you want to change:

- Global colors and fonts: `:root` near the top.
- Header: `.header`, `.nav`, `.drawer`.
- Hero background visibility: `.hero--kelo .intro__scrim`.
- Hero zoom: `@keyframes kZoom`.
- Campaign image frame: `.hero--kelo .kelo__art`.
- Enquiry glass panel: `.hero--kelo .hero__enquiry`.
- Section layout and spacing: the matching class, such as `.split`, `.features`, `.gallery`, or `.amenities`.
- Mobile layout: the related `@media (max-width: ...)` rules.

For example, `.hero--kelo .hero__enquiry` targets the enquiry card inside this hero. Including the parent section class helps keep a style change limited to that section.

Common CSS properties:

- `border-radius` rounds corners.
- `box-shadow` adds depth.
- `linear-gradient()` and `radial-gradient()` create color fades and glows.
- `backdrop-filter: blur(...)` creates the glass effect.
- `transition` smooths a hover or focus change.
- `@keyframes` defines timed movement. The hero zoom is an animation on a still image, not a video.

## Images

All local images are in `images/`. HTML paths look like `images/name.webp`. CSS paths look like `../images/name.webp` because the stylesheet is inside `css/`. When replacing an image, update the path wherever it is used. For the hero background, update its preload path in the HTML head as well.

## Enquiry form IDs

The form IDs (`enquiryForm`, `fName`, `fPhone`, `fEmail`, `fConsent`, `submitBtn`, and others) are used by the built-in form behavior. Keep them unchanged when editing form layout or labels.

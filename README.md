# S&P Villa Enchante - Easy Edit Guide

Daily design edits panna HTML and CSS mattum open pannina podhum. Existing menu, form, gallery, map, and plan interactions work aaganum-nu internal JavaScript `index.html`-oda bottom-la irukku; adhai edit panna thevai illai.

## Project folders

```text
S&P-Villa-Enchante/
|-- index.html       All page sections, editable content, and internal behavior
|-- css/
|   `-- style.css    Colors, sizes, layout, glass effects, responsive styles
|-- images/          Photos, logos, icons, and site plan
`-- README.md        This guide
```

## HTML-la enna edit pannalaam?

`index.html`-la ovvoru section-um clear comment-oda start aagum. Ctrl+F-la section `id` or comment name thedi andha block-ku pogalaam.

| Page part | HTML id/class | Common edit |
|---|---|---|
| Header/menu | `#header`, `.nav`, `#drawer` | Menu labels and links |
| Hero | `#home`, `.kelo__art` | Background and campaign image paths |
| Enquiry form | `#enquiry` | Field labels and visible structure; preserve form IDs |
| Overview | `#overview` | Section layout/images; paragraph content is in `window.SITE` below the page markup |
| About | `#about` | Section layout; copy is in `window.SITE.about` |
| Statement | `#statement` | Decorative title words |
| Features | `#features` | Section heading/layout; cards come from `window.SITE.features` |
| Amenities | `#amenities` | Section structure; content comes from `window.SITE.amenities` |
| Gallery | `#gallery` | Gallery container; photos come from `window.SITE.gallery` |
| Floor plans | `#floorplans` | Site-plan image and viewer controls |
| Master plan | `#masterplan` | Image/layout; copy is in `window.SITE.masterPlan` |
| Location | `#location` | Map/layout; text and map search are in `window.SITE.location` |
| Specifications | `#specifications` | Section layout; list comes from `window.SITE.specifications` |
| Contact | `#contact` | Section layout; cards come from `window.SITE.contact` |
| Footer | `.footer` | Footer text and logo |

Dynamic cards and paragraphs use the `window.SITE` data block inside the bottom script in `index.html`. It is JavaScript object syntax; if editing it, change only the text or image value and keep the quotes and commas. For normal layout edits, work in the section HTML and matching CSS instead.

## CSS-la enna edit pannalaam?

Open `css/style.css` and Ctrl+F thedi selector name-ai find pannunga:

- Global colors/fonts: `:root` near the top.
- Header: `.header`, `.nav`, `.drawer`.
- Hero background visibility: `.hero--kelo .intro__scrim`.
- Hero zoom movement: `@keyframes kZoom`.
- Campaign frame: `.hero--kelo .kelo__art`.
- Enquiry glass panel: `.hero--kelo .hero__enquiry`.
- Section layout/spacing: matching section class, for example `.split`, `.features`, `.gallery`, `.amenities`.
- Small-screen layout: matching `@media (max-width: ...)` rules.

Selector example: `.hero--kelo .hero__enquiry` affects only the enquiry card inside this hero. Use the section's parent class before a child class to avoid changing other sections.

`border-radius` = curved corners; `box-shadow` = depth; `linear-gradient` / `radial-gradient` = color fade; `backdrop-filter: blur(...)` = glass effect; `transition` = smooth hover/focus change; `@keyframes` = timed motion. Hero movement is a still image animation, not a video.

## Images

All local photos are inside `images/`. HTML image paths look like `images/name.webp`. CSS paths look like `../images/name.webp` because `style.css` is inside `css/`. When changing an image, update its path where it is used; for the hero background, also update its preload path in the HTML head.

### Important form note

The enquiry form's IDs (`enquiryForm`, `fName`, `fPhone`, `fEmail`, `fConsent`, `submitBtn`, and others) connect to the internal form behavior. Keep them unchanged when editing the form layout or labels.

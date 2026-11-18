# Villa Enchante Project Guide

Indha guide-la project files enga irukku, ovvoru section edhai control pannudhu, change panna endha file open pannanum nu simple-ah explain pannirukken.

## Folder structure

```text
S&P-Villa-Enchante/
|-- index.html       Page sections, content data, form, JavaScript
|-- css/
|   `-- style.css    Colors, layout, responsive design, animations
|-- images/          Website use pannura logos, project photos, icons
`-- README.md        Indha guide
```

`index.html`-a browser-la open pannina website paarkalaam. Edhavadhu change pannitu browser-la refresh pannunga; latest CSS/image changes theriyala na `Ctrl + F5` press pannunga.

## Endha change-ku endha file?

| Neenga maathanum | Enna seiyanum |
|---|---|
| Section text, feature details, amenities, gallery captions | `index.html`-la `const SITE = {` nu search panni andha data-va edit pannunga |
| First-page campaign image | `images/villa-enchante-campaign.jpeg`-a replace pannunga; pudhu file name-na `index.html`-la `introCampaign` pakkathula image path-um maathanum |
| Hero background slideshow photos | `index.html`-la `initIntroCarousel()` nu search panni slides list-la image path maathanum |
| Logo | `images/sandp-logo-white.png` file-ai replace pannunga; logo path HTML-la `logo__image` nu search pannina kidaikkum |
| Color, size, spacing, cards, buttons, animation | `css/style.css`-la andha element-oda class name-ai search panni edit pannunga |
| Enquiry form fields / labels | `index.html`-la `id="enquiry"` section-ai paarunga |
| Enquiry form Google endpoint | `index.html`-la `SITE.formEndpoint` nu search pannunga |
| Site plan image | `images/site-plan.webp`-a replace pannunga; pudhu file name-na `index.html`-la `planImg` nu search panni path-ai maathanum |

Photo replace pannumbodhu, pudhu image-um project-kku sambandhamaana Villa Enchante image-ah `images/` folder-kulla vechukonga. HTML/CSS-la use aagura file-ai mattum delete pannunga.

## Page sections: mela irundhu keezha

`index.html`-la section `id`-ai search pannina andha page area direct-ah kidaikkum.

| Page-la varra section | HTML ID | Adhula enna irukku? |
|---|---|---|
| First page / Hero | `home` | Villa Enchante campaign image, background images, enquiry form |
| Project overview | `overview` | Project intro heading, paragraphs, optional stats |
| About | `about` | S&P Foundation pathina short introduction |
| Villa features | `features` | Villa feature cards, image, title, description |
| Shared spaces | `amenities` | Clubhouse matrum OSR amenities list |
| Gallery | `gallery` | Villa, interior, amenity photos; category filters and image viewer |
| Floor plans | `floorplans` | Site plan image and zoom / drag controls |
| Master plan | `masterplan` | Community layout image and description |
| Location | `location` | Location text, map, Google Maps link |
| Specifications | `specifications` | Structure, flooring, kitchen pola details |
| Contact | `contact` | Contact information |

Header menu-la irukkira link, indha `id`-ku scroll aagum. Oru section-ai move panna/rename panna, header link-oda `href`-um section `id`-um match aaganum.

## `const SITE` content eppadi edit pannradhu?

`index.html`-la `const SITE = {` nu Ctrl+F panni kandupidunga. Andha block-kulla irukkira key names section content-ai kurikkum:

- `hero`: First-page intro text.
- `images`: Overview, about, master-plan image paths.
- `overview`: Overview title, paragraphs, stats.
- `about`: Developer introduction text.
- `features`: Feature cards. Oru item-la `title`, `text`, `img`, `icon` irukkum.
- `gallery`: Gallery photo path, `caption`, `cat` category.
- `amenities`: Group `title` matrum ovvoru group-oda `items`.
- `masterPlan`: Master-plan section paragraph.
- `location`: Location text, map search text, nearby places.
- `specifications`: Specification headings and bullet items.
- `contact`: Phone, email, address pola contact details.
- `formEndpoint`: Enquiry form submit aagumbodhu data pogira Google Apps Script URL.

Text mattum maathanumna indha data values-ai edit pannunga. Existing heading/paragraph wording-ai pudhu text venum nu decide pannama maatha vendam.

## JavaScript interactions enga?

Interactions ellam `index.html`-oda last side-la irukkira `<script>` block-la irukku. Ctrl+F-la function name search pannalaam.

| Function | Velai |
|---|---|
| `renderHero()` | Hero text set pannum |
| `renderStatic()` | Overview, about, master-plan content/images set pannum |
| `renderFeatures()` | Feature cards create pannum |
| `renderGallery()` | Gallery photos/filter set pannum |
| `renderAmenities()` | Amenity groups kaattum |
| `renderLocation()` | Map matrum location details set pannum |
| `renderSpecs()` | Specifications list create pannum |
| `renderContact()` | Contact details set pannum |
| `initIntroCarousel()` | Hero background slides-ai maathum |
| `initPlanViewer()` | Plan image zoom, drag, buttons control pannum |
| `initForm()` | Enquiry form validation, progress, submit handle pannum |
| `initNav()` | Header, mobile menu, section navigation handle pannum |
| `initTheme()` | Light/dark mode toggle handle pannum |
| `initScroll()` | Scroll reveal and page scroll effects handle pannum |

## CSS style-ai edit pannradhu

`css/style.css`-la class name search panni andha part-oda design maathalaam.

- Main colors/fonts: `:root`
- Header and logo: `.header`, `.logo__image`
- Hero image and form: `.hero--split`, `.intro__campaign`, `.hero__enquiry`
- Section spacing: `.section`
- Feature cards: `.features`, `.feature`
- Gallery: `.gallery`, `.g-item`
- Amenities: `.amenity-groups`, `.amenity-card`
- Floor plan: `.plan-viewer`
- Form controls: `.form`, `.field`, `.btn`
- Phone/tablet layout: `@media` blocks file-oda keezh pakkam irukkum.

## Images path eppadi work aagum?

Website use pannura local image path `images/`-la start aagum. Udharanama `images/site-plan.webp`. `index.html` allathu `css/style.css`-la oru image path use aagudhaa nu Ctrl+F panni paarthuttu dhaan andha image-ai remove pannunga; illena page-la broken image varalaam.

### Easy reminder

- **Content/data** -> `index.html` -> `const SITE`
- **Section layout** -> `index.html` -> section `id`
- **Colors/design/mobile size** -> `css/style.css`
- **Image file** -> `images/` + adha use pannura HTML/CSS path
- **Form connection** -> `index.html` -> `SITE.formEndpoint`

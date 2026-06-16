# Master Routing Registry — Need → Library

Read this first when deciding which library to use. Find the row that matches the user's need, take the **Primary** library, then open that library's deep-dive file. Use **Backup** only if the primary doesn't fit the stack or the exact component is missing.

All "Primary" picks assume a **React + Tailwind + shadcn/ui** project unless noted. Park UI is the only non-shadcn option (Panda CSS / Ark UI / multi-framework).

## 1. Animation & Motion (hero moments, "make it pop")

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Animated text — typing, gradient, shiny, scramble/decrypt, split, rotating, count-up, blur, fuzzy, glitch | react-bits | Magic UI | react-bits has 23 text effects with JS/TS × CSS/TW variants |
| Animated text — number ticker, aurora text, hyper text, word rotate, sparkles, morphing | Magic UI | react-bits | Magic UI text set is shadcn-native |
| WebGL/canvas backgrounds — aurora, particles, plasma, galaxy, hyperspeed, silk, threads, waves, lightning | react-bits | Magic UI | 40+ backgrounds; GPU-heavy, gate behind reduced-motion |
| Pattern backgrounds — dot/grid/retro grid, ripple, flickering grid, light rays | Magic UI | react-bits | Lighter CSS/SVG patterns |
| Special effects — animated beam, border beam, shine border, meteors, confetti, magic card, glare hover | Magic UI | — | The signature Magic UI set |
| Cursor effects — blob cursor, splash cursor, target cursor, click spark, crosshair | react-bits | Magic UI (smooth cursor) | |
| Scroll effects — scroll float/reveal/velocity, scroll stack | react-bits | Magic UI (scroll progress) | |
| Image effects — image trail, pixel transition, tilted card, decay card, circular gallery, dome gallery | react-bits | Animata | |
| Micro-interactions — small animated widgets, toggles, animated buttons, skeletons, preloaders | Animata | KokonutUI | 154+ hand-crafted small interactions |

## 2. Layout & Showcase

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Bento grid | Magic UI | KokonutUI / Animata | Magic UI BentoGrid is the cleanest |
| Dock (macOS-style) | Magic UI | react-bits | Both have a Dock |
| Marquee / logo loop / ticker | Magic UI | react-bits (LogoLoop) | |
| Orbiting circles / globe / icon cloud | Magic UI | — | 3D-ish showcase pieces |
| Card effects — flip, stack, spotlight, glass, carousel | KokonutUI | react-bits | KokonutUI has the richest card set |
| Masonry / infinite menu / gooey nav / staggered menu | react-bits | KokonutUI | |

## 3. Editors & Rich Content

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Rich-text / WYSIWYG / Notion-like editor (full framework) | Plate | Kibo UI (editor) | Plate = full plugin framework on Slate; use for serious editors |
| Lightweight inline editor | Kibo UI (editor) | Plate | Kibo editor wraps complexity for quick needs |
| AI editor / AI-assisted writing | Plate (editor-ai) | KokonutUI (ai-*) | `npx shadcn add @plate/editor-ai` |
| Code block — syntax highlight, copy, line numbers | Kibo UI (code-block) | KokonutUI (command-button) | |
| Code comparison / diff | Magic UI (code comparison) | Kibo UI (comparison) | |

## 4. Data & Application UI

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Kanban board (drag-drop columns) | Kibo UI (kanban) | — | The go-to; wraps dnd logic |
| Gantt chart / timeline planner | Kibo UI (gantt) | ui-x (timeline) | |
| Rich table / data grid | Kibo UI (table) | — | |
| Calendar | Kibo UI (calendar) / Kibo (mini-calendar) | ui-x (calendar) | |
| Tree view | Kibo UI (tree) | — | |
| Contribution graph (GitHub-style) | Kibo UI (contribution-graph) | — | |
| QR code | Kibo UI (qr-code) | — | |
| Video player | Kibo UI (video-player) | — | |
| Stories (IG-style) / reel / deck | Kibo UI | — | |

## 5. Forms & Inputs (advanced)

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Date field / date picker / date-time / range | ui-x | Kibo UI | ui-x has the most complete date stack incl. primitives |
| Combobox (typeahead) | ui-x | Kibo UI (combobox) | |
| Sortable list (drag to reorder) | ui-x (sortable) | Kibo UI (list) | |
| File dropzone / upload | ui-x (dropzone) | Kibo UI (dropzone) | Both solid; Kibo if already using Kibo |
| Password input (with toggle/strength) | ui-x | — | |
| Time / time field / time picker | ui-x | — | |
| Timeline | ui-x | Kibo UI (gantt) | |
| Virtualizer (long lists) | ui-x | — | |
| Color picker | Kibo UI (color-picker) | — | |
| Image crop / zoom | Kibo UI | stackzero (image-viewer) | |
| Rating input | stackzero/ui | Kibo UI (rating) | stackzero has star/face/like/upvote |

## 6. E-commerce

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Product variant selector (color/size/image swatches) | stackzero/ui (variant-selector) | — | The reason stackzero exists |
| Product card | stackzero/ui (product-card) | bundui (ecommerce) | |
| Cart UI | stackzero/ui (carts) | bundui | |
| Price format (currency, sale price) | stackzero/ui (price-format) | — | |
| Quantity input | stackzero/ui (quantity-input) | ui-x | |
| Ratings & reviews | stackzero/ui | Kibo UI (rating) | |
| Image carousel / viewer (product gallery) | stackzero/ui | react-bits (carousel) | |
| Address form / phone input / banners | stackzero/ui | ui-x | |

## 7. Marketing Page Blocks (whole sections)

| Need | Primary | Backup | Notes |
|---|---|---|---|
| Hero section block | bundui (marketing/hero) | Magic UI (hero video dialog) | |
| Pricing section | bundui (marketing/pricing) | — | |
| Team section | bundui (marketing/team-sections) | KokonutUI | |
| Testimonials | bundui | — | |
| CTA / newsletter / stats / logo cloud / feature sections | bundui | Magic UI | |
| Footer / navbar / banner / cookie consent | bundui (elements) | KokonutUI (navigation) | |
| Dashboard UI blocks | bundui (dashboard) | Kibo UI | |

## 8. AI-specific UI

| Need | Primary | Backup | Notes |
|---|---|---|---|
| AI prompt input / search | KokonutUI (ai-input-search, ai-prompt) | Kibo UI | |
| AI loading / thinking states | KokonutUI (ai-loading, ai-text-loading) | — | |
| AI voice UI | KokonutUI (ai-voice) | — | |
| AI chat editor surface | Plate (editor-ai) | Kibo UI (editor) | |

## 9. Non-shadcn / multi-framework

| Need | Primary | Notes |
|---|---|---|
| Panda CSS design system | Park UI | Ark UI primitives + Panda recipes |
| Solid or Vue (not just React) | Park UI | Shared composable API across frameworks |
| Headless primitives you'll heavily restyle | Park UI | Open-code, recipe-based |

## Decision shortcuts

- **"It moves and it's the star of the page"** → react-bits or Magic UI.
- **"It moves but it's small/utility"** → Animata.
- **"It holds or edits content/data"** → Kibo UI (or Plate for editors).
- **"It's a form input beyond shadcn's basics"** → ui-x.
- **"It sells something"** → stackzero/ui.
- **"It's a whole marketing section"** → bundui.
- **"It's cards or AI-flavored blocks"** → KokonutUI.
- **"They said Panda/Solid/Vue"** → Park UI.

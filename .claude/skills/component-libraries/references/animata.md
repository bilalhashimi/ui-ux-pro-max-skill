# Animata — Hand-Crafted Micro-Interactions

**Docs:** https://animata.design/components · **Tech:** React + Tailwind + Framer Motion · **Model:** copy-paste

## What it is

A hand-crafted collection of 154+ animation / interaction / **micro-interaction** components. Strongest at small, delightful, self-contained pieces — animated widgets, buttons, skeletons, preloaders, hero bits — rather than full-page WebGL spectacles. Copy-paste into a React + Tailwind + Framer Motion project.

## When to reach for it

- Small **micro-interactions**: animated counters, toggles, hover widgets, animated icons.
- Polished **skeletons / preloaders / progress** while loading.
- A quick animated **hero** or **bento** block without heavy WebGL.
- Lightweight alternative when react-bits/Magic UI feel too heavy.

## Install

Copy-paste from the component page (no central CLI). Ensure React + Tailwind + `framer-motion` are installed.

```bash
npm i framer-motion
# then copy the component source from animata.design into your project
```

## Catalog by category (154+)

| Category | Count |
|---|---|
| Text | 42 |
| Widget | 30 |
| Button | 13 |
| Card | 11 |
| Background | 10 |
| List | 7 |
| Skeleton | 6 |
| Container | 5 |
| Graphs & charts | 5 |
| Image | 5 |
| Hero | 4 |
| Bento grid | 3 |
| Tabs | 3 |
| Floating Action Buttons | 2 |
| Icon | 2 |
| PreLoader | 2 |
| Progress | 2 |
| Overlay | 1 |
| Scroll | 1 |

Browse the live category pages for exact component names — Animata's value is breadth of small interactions; pick by previewing.

## Usage pattern

```tsx
// Copied Animata component, e.g. an animated counter widget
import { Counter } from "@/components/animata/widget/counter";

<Counter value={1280} className="text-4xl font-semibold" />
```

## Gotchas

- No CLI/registry — you copy source; keep a consistent folder (`components/animata/...`).
- Standardize on **one** motion lib: Animata uses `framer-motion`/`motion`; don't also add GSAP.
- Great for utility motion; for marquee/beam/WebGL backgrounds prefer Magic UI / react-bits.
- Respect `prefers-reduced-motion` on looping widgets.

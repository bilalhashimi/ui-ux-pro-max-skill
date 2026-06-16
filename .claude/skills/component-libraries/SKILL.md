---
name: component-libraries
description: "Picks WHICH React/Tailwind/shadcn component library to use for a need, then installs and uses it correctly. Covers 10 libraries: react-bits (animated text/backgrounds), Magic UI (marketing effects: beam, meteors, marquee, bento), Animata (micro-interactions), KokonutUI (AI/cards blocks), Park UI (Ark UI + Panda, multi-framework), Plate (rich-text editor framework), Kibo UI (kanban, gantt, code-block, table, dropzone, editor), bundui (marketing/dashboard section blocks), stackzero/ui (e-commerce: product variants, ratings, carts), ui-x (advanced date/combobox/dropzone primitives). Use when building or adding: animated hero, landing effects, marquee, particle/aurora/beam background, animated text, bento grid, dock, rich text/WYSIWYG editor, kanban, gantt, code block, AI chat UI, file dropzone, product variant selector, rating, cart, team/pricing section, date picker, combobox, or any fancy/animated/interactive component. Pairs with shadcn/ui."
license: MIT
metadata:
  author: ui-ux-pro-max
  version: '1.0'
---

# Component Library Intelligence

This skill is the **routing brain** that decides which third-party component library to reach for, then installs and uses it correctly. It sits on top of the shadcn/ui base layer that the rest of UI/UX Pro Max already understands.

The core problem it solves: a model that only knows shadcn/ui will hand-roll a janky animated hero, a broken kanban board, or a fragile rich-text editor when a battle-tested library already exists. This skill makes the model **reach for the right tool first**.

## When to Use This Skill

Activate whenever the task involves adding a component or section that is **richer than a shadcn primitive** — anything animated, interactive, data-heavy, or domain-specific. Trigger phrases include:

- "animated hero", "landing page effects", "make it pop", "fancy section"
- "marquee", "infinite scroll logos", "ticker"
- "particle / aurora / beam / grid / plasma background", "animated background"
- "animated text", "typing effect", "gradient text", "scramble/decrypt text", "count up"
- "bento grid", "dock", "orbiting circles", "globe", "confetti", "meteors"
- "rich text editor", "WYSIWYG", "notion-like editor", "markdown editor"
- "kanban board", "gantt chart", "code block with syntax highlight", "AI chat UI", "file dropzone / upload"
- "product variant selector", "size/color picker", "star rating", "cart", "price format", "quantity input"
- "team section", "pricing section", "testimonials", "CTA section", "hero section block"
- "advanced date picker", "date range", "combobox", "sortable list", "timeline"
- "what library should I use for X", "is there a component for X"

## The Iron Law

> **Match the need to the library before writing a single line of component code.**

Never hand-build something one of these libraries already does well. First read the routing table, pick the library, confirm the stack fits, then install and use it.

## How to Use This Skill (workflow)

1. **Identify the need.** Reduce the user's request to a concrete need: "animated marketing hero", "rich text editor", "product variant UI", etc.
2. **Route.** Read `references/registry.md` — the master need→library decision table. It returns the recommended library (and runner-up) for the need.
3. **Confirm stack fit.** Check the user's stack against the library's requirements (see "Stack Compatibility" below). Most libraries assume React + Tailwind + shadcn/ui. Park UI is the exception (Ark UI + Panda CSS, multi-framework).
4. **Read the deep-dive.** Open the matching `references/<library>.md` for the exhaustive component list, install command, dependencies, and gotchas. Only read the file(s) you need — do not load all of them.
5. **Install correctly.** Use the exact install pattern from the deep-dive. Most are shadcn registry installs (`npx shadcn@latest add <registry-url>`), NOT npm packages.
6. **Implement, then self-check** against the "Integration Golden Rules" below and the parent UI/UX Pro Max accessibility/performance rules.

## Stack Compatibility (read before installing)

| Library | Base | Install model | Needs |
|---|---|---|---|
| react-bits | React | shadcn CLI or jsrepo or copy-paste | Tailwind optional (4 variants: JS/TS × CSS/TW); some bg use OGL/three |
| Magic UI | React + shadcn | shadcn registry | Tailwind, motion (framer-motion) |
| Animata | React | copy-paste | Tailwind, framer-motion |
| KokonutUI | React + shadcn | shadcn registry | Tailwind, motion |
| Park UI | Ark UI + Panda CSS | Park UI CLI / copy | **Panda CSS**, NOT Tailwind/shadcn; React/Solid/Vue |
| Plate | React + Slate + shadcn | shadcn registry | Slate, many plugin pkgs |
| Kibo UI | React + shadcn | shadcn registry | Tailwind, shadcn vars; per-component headless deps |
| bundui | React + shadcn | copy / CLI | Tailwind, shadcn, motion |
| stackzero/ui | React + shadcn | shadcn registry | Tailwind, shadcn, motion |
| ui-x | React + Radix + shadcn | shadcn registry | Tailwind, shadcn vars, Radix |

**Critical:** 9 of 10 libraries live in the shadcn/Tailwind ecosystem and compose cleanly. **Park UI does NOT** — it uses Panda CSS and Ark UI. Only recommend Park UI when the user wants a Panda CSS / multi-framework (Solid/Vue) system, or explicitly asks for it. Do not mix Park UI into a Tailwind+shadcn project.

## Quick Routing Cheat-Sheet

Full table in `references/registry.md`. Top-level mapping:

| Need | Primary | Backup |
|---|---|---|
| Animated text (typing, gradient, scramble, count-up) | react-bits | Magic UI |
| Animated/WebGL backgrounds (aurora, particles, plasma) | react-bits | Magic UI |
| Marketing special effects (beam, border-beam, meteors, confetti) | Magic UI | react-bits |
| Bento grid / dock / globe / marquee | Magic UI | KokonutUI |
| Micro-interaction widgets (animated counters, toggles, small UI) | Animata | KokonutUI |
| AI chat UI primitives | KokonutUI (ai-*) | Kibo UI (editor/ai) |
| Cards (flip, stack, spotlight, glass) | KokonutUI | react-bits |
| Rich-text / WYSIWYG / notion-like editor | Plate | Kibo UI (editor) |
| Kanban board | Kibo UI | — |
| Gantt chart | Kibo UI | — |
| Code block (syntax highlight, copy) | Kibo UI | KokonutUI |
| File dropzone / upload | Kibo UI | ui-x (dropzone) |
| Table / data grid (rich) | Kibo UI | — |
| Calendar / mini-calendar | Kibo UI | ui-x (calendar) |
| Advanced date/time picker & range | ui-x | Kibo UI |
| Combobox / sortable / timeline / password input | ui-x | — |
| Product variant selector (color/size/image) | stackzero/ui | — |
| Star/face/like ratings, price format, quantity, cart | stackzero/ui | — |
| Marketing blocks (hero, pricing, team, CTA, testimonials) | bundui | Magic UI |
| Multi-framework (Solid/Vue) or Panda CSS system | Park UI | — |

## Integration Golden Rules

1. **shadcn registry first.** Most of these install via `npx shadcn@latest add <url>`, which drops source into your repo. Prefer this over npm where both exist — you own and can edit the code.
2. **One motion lib.** These libraries standardize on `motion` (formerly framer-motion). Don't also pull in GSAP/react-spring unless a specific react-bits component requires it. Avoid version conflicts.
3. **Respect `prefers-reduced-motion`.** Animated backgrounds and text from react-bits/Magic UI/Animata can be heavy and motion-sick-inducing. Gate them, and provide a static fallback. (Parent rule: `reduced-motion`.)
4. **Budget the GPU.** WebGL/canvas backgrounds (react-bits Backgrounds, Magic UI Particles) are expensive. One per page, above the fold, lazy-mount below the fold, and never behind body text without a contrast scrim.
5. **Don't mix design languages.** Pick a primary system (shadcn + one accent library) per project. Layering react-bits + KokonutUI + bundui + Kibo at once produces visual incoherence. Use shadcn as the base, add ONE library for the hero moment, and Kibo/ui-x/stackzero for functional needs.
6. **Park UI is a separate world.** Never drop Park UI components into a Tailwind/shadcn project. It's Panda CSS + Ark UI.
7. **Verify the registry URL.** Registry namespaces change. Pull the exact `add` command from each component's doc page; the deep-dive files give the canonical pattern but confirm the slug.
8. **License check for commercial work.** Most are MIT. react-bits is **MIT + Commons Clause** (can't sell the components themselves as a product). Flag this if the user is building a component-selling product.

## Reference Files

Read only what the task needs:

- `references/registry.md` — master need→library routing table (READ FIRST when routing)
- `references/react-bits.md` — animated text, backgrounds, animations, UI components
- `references/magic-ui.md` — marketing animations, special effects, device mocks, backgrounds
- `references/animata.md` — micro-interaction widgets and effects
- `references/kokonutui.md` — AI, cards, backgrounds, buttons, text blocks
- `references/park-ui.md` — Ark UI + Panda CSS multi-framework primitives
- `references/plate.md` — rich-text editor framework, plugins, install
- `references/kibo-ui.md` — high-level shadcn extensions (kanban, gantt, editor, AI, dropzone…)
- `references/bundui.md` — marketing/ecommerce/dashboard blocks
- `references/stackzero-ui.md` — e-commerce components and blocks
- `references/ui-x.md` — advanced form/date/dropzone primitives

- `data/component-libraries.csv` — machine-readable registry (need, library, category, install, deps, docs, license)

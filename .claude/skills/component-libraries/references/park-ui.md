# Park UI — Ark UI + Panda CSS (multi-framework)

**Repo:** chakra-ui/park-ui (cschroeter) · **Docs:** https://park-ui.com/docs/introduction · **License:** MIT · **Stars:** 2.3k+ · **Built on:** Ark UI (headless) + Panda CSS (recipes)

## What it is

A component system distributed as **source code** (open-code, like shadcn) but built on **Ark UI** headless primitives and **Panda CSS** recipes instead of Radix + Tailwind. Its key differentiator: the shared composable API stays consistent **across JS frameworks** — React, Solid, and Vue.

## When to reach for it — and when NOT to

**Use Park UI when:**
- The project uses **Panda CSS** (not Tailwind).
- You target **Solid or Vue** (or want one API across frameworks).
- You want Ark UI headless primitives with polished default recipes you fully own.

**Do NOT use Park UI when:**
- The project is **Tailwind + shadcn/ui** (the default for the other 9 libraries here). Park UI's Panda recipes do not compose with Tailwind utility classes or shadcn CSS variables. Mixing them creates two parallel styling systems. In a shadcn project, use shadcn/ui itself plus Kibo/ui-x instead.

This is the **odd one out** in this skill — keep it isolated.

## Install / setup

Two ways (per docs):
- **CLI:** install components into your project with the Park UI CLI.
- **Docs:** copy component source directly from the website.

Setup requires **Panda CSS** configured in the project and a Park UI preset. Pick your framework (React/Solid/Vue) during setup.

```bash
# conceptual — follow park-ui.com for exact current commands
npm create panda
npx @park-ui/cli init
npx @park-ui/cli components add button
```

## Principles (from docs)

- **Open Code:** full source ownership; every component + recipe is readable/editable. "No more bug reports — fix it in your codebase."
- **Composition:** everything built on Ark UI, architected for composability.
- **Code Distribution:** shipped as source, not an npm black-box.
- **Beautiful Design:** minimalistic defaults, consistent styling; Figma Kit available.
- **AI Ready:** open code + consistent API is easy for LLMs to read and extend.

## Components

The intro page doesn't enumerate them; Park UI covers the standard Ark UI surface — button, field, select, combobox, dialog, popover, menu, tabs, accordion, tooltip, switch, slider, date-picker, pagination, toast, etc. Browse https://park-ui.com/docs for the current list and per-component source.

## Gotchas

- **Panda, not Tailwind.** This is the single most important fact. Don't import Park UI into a Tailwind/shadcn app.
- Theming is via Panda **recipes**, not CSS variables + utility classes.
- Multi-framework is the reason to choose it; in a React-only Tailwind app, shadcn is the better default.

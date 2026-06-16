# bundui — Marketing / App Section Blocks

**Docs:** https://bundui.io · **Tech:** Tailwind CSS + shadcn/ui + Motion (React) · **Model:** copy / CLI ("View Code" per block)

## What it is

A library of ready-made **blocks** (whole page sections), plus components and motion, built with Tailwind + shadcn/ui. Where Magic UI/react-bits give you the moving parts, bundui gives you **assembled sections** — hero, pricing, team, testimonials, CTA — that you paste in and customize. The fastest way to stand up a marketing or dashboard page.

## When to reach for it

- You need a **whole section** fast: hero, pricing, team, testimonials, CTA, stats, feature, FAQ, footer.
- Marketing landing pages, dashboard UI shells, ecommerce/real-estate page sections.
- Pair with Magic UI/react-bits to drop animated accents into bundui's static structure.

## Install / use

Open the block on bundui.io and use **View Code** to copy, or use the CLI where provided. Requires Tailwind + shadcn/ui set up; some blocks use `motion`.

```bash
# many blocks are copy-paste from "View Code";
# CLI-published blocks install via shadcn registry, e.g.:
npx shadcn@latest add "https://bundui.io/r/<block>.json"   # confirm slug on the page
```

## Block catalog (by group)

### Marketing
Hero Sections (5), CTA Sections (4), Pricing Sections (3), Testimonials (3), Feature Sections (2), Blog Sections (2), Team Sections (2), Stats Section (2), Promotional (2), Logo Clouds (2), Newsletter Sections (1), Integrations (1), Footers (1), Bento Grids (1), Contact Sections (1), How It Works (1)

### Elements
Navbars (4), Banners (3), Cookie Consent (3)

### Other groups (in sidebar)
Ecommerce, Dashboard UI, Real Estate

Also offers standalone **Components** and **Motion** sections beyond blocks.

## Usage pattern

```tsx
// Paste a bundui Team Section block, then swap data/styles
import { TeamSection } from "@/components/blocks/team-section";

<TeamSection
  heading="Meet the team"
  members={members}            /* name, role, avatar, socials */
/>
```

## Gotchas

- Requires Tailwind + shadcn/ui; blocks reuse shadcn components and tokens.
- Blocks are starting points — replace placeholder copy/images and align to your design tokens.
- Don't stack three block libraries; use bundui for structure and ONE accent library (Magic UI/react-bits) for motion.
- Confirm whether a block is copy-paste vs. CLI-published before scripting installs.

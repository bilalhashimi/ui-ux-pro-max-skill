# KokonutUI — Tailwind + shadcn + Motion Components

**Repo:** kokonut-labs/kokonutui · **Docs:** https://kokonutui.com · **License:** MIT · **Stars:** 1.9k+

## What it is

Open-source collection of stunning components built with Tailwind CSS, shadcn/ui and Motion. Strongest at **AI UI blocks, rich cards, animated backgrounds, and stylish buttons**. shadcn-native — installs into your repo.

## When to reach for it

- **AI product UI**: prompt inputs, AI loading/thinking states, voice UI.
- **Cards** with personality: flip, stack, spotlight, liquid glass, bento, tweet.
- Stylish **buttons** and **animated text** for marketing.
- Navigation flourishes: morphic navbar, action search bar, smooth drawer/tabs.

## Install

shadcn registry, per component:

```bash
npx shadcn@latest add @kokonutui/ai-prompt
npx shadcn@latest add @kokonutui/card-flip
npx shadcn@latest add @kokonutui/bento-grid
# (confirm slug on the component page)
```

## Dependencies

- shadcn/ui initialized + Tailwind + `motion`.

## Full component catalog

### AI (5)
ai-input-search, ai-loading, ai-prompt, ai-text-loading, ai-voice

### Backgrounds (4)
background-paths, beams-background, flow-field, shape-hero

### Buttons (9)
attract-button, command-button, gradient-button, hold-button, particle-button, slide-text-button, social-button, switch-button, v0-button

### Cards (10)
apple-activity-card, bento-grid, card-flip, card-stack, carousel-cards, currency-transfer, liquid-glass-card, mouse-effect-card, spotlight-cards, tweet-card

### Inputs (4)
avatar-picker, file-upload, loader, team-selector

### Navigation (6)
action-search-bar, morphic-navbar, profile-dropdown, smooth-drawer, smooth-tab, toolbar

### Texts (8)
dynamic-text, glitch-text, matrix-text, scroll-text, shimmer-text, sliced-text, swoosh-text, type-writer

## Usage pattern

```tsx
import AIPrompt from "@/components/kokonutui/ai-prompt";
import CardFlip from "@/components/kokonutui/card-flip";

<section className="grid gap-6 md:grid-cols-2">
  <AIPrompt onSubmit={handleAsk} />
  <CardFlip front={<Front />} back={<Back />} />
</section>
```

## Gotchas

- Requires shadcn init (CSS vars + `cn`) and `motion`.
- Overlaps Magic UI on text/bento — don't install both for the same purpose; pick one accent library per project.
- AI blocks are presentational — wire your own model/streaming logic.
- For a true rich-text editor, use Plate/Kibo, not KokonutUI inputs.

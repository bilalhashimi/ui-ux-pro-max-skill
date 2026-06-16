# Magic UI — Animated Components for Design Engineers

**Repo:** magicuidesign/magicui · **Docs:** https://magicui.design/docs/components · **License:** MIT · **Stars:** 21k+

## What it is

A shadcn-native library of animated components and special effects you copy-paste into your app. Built for React/Next.js + Tailwind + `motion` (framer-motion). The most popular companion to shadcn/ui for marketing polish. 150+ components/effects.

## When to reach for it

- shadcn-native marketing animations and **special effects** (beam, border beam, meteors, confetti).
- Showcase pieces: bento grid, dock, globe, orbiting circles, icon cloud, marquee.
- Device mockups (Safari/iPhone/Android frames) for product screenshots.

Backup to react-bits when you need WebGL backgrounds or a creative effect Magic UI lacks.

## Install

shadcn registry, per component:

```bash
npx shadcn@latest add "https://magicui.design/r/marquee"
npx shadcn@latest add "https://magicui.design/r/border-beam"
npx shadcn@latest add "https://magicui.design/r/bento-grid"
```

## Dependencies

- React + Tailwind + shadcn/ui set up (`components.json`, CSS vars).
- `motion` (framer-motion) — installed automatically by most components.
- A few use `cobe` (Globe) or canvas.

## Full component catalog

### Components (16)
Marquee, Terminal, Hero Video Dialog, Bento Grid, Animated List, Dock, Globe, Tweet Card, Orbiting Circles, Avatar Circles, Icon Cloud, Lens, Pointer, Smooth Cursor, Progressive Blur, Dotted Map

### Special Effects (9)
Animated Beam, Border Beam, Shine Border, Magic Card, Glare Hover, Meteors, Confetti, Particles, Animated Theme Toggler

### Animations / text (21)
Blur Fade, Text Animations, Text Animate, Typing Animation, Line Shadow Text, Aurora Text, Video Text, Number Ticker, Animated Shiny Text, Animated Gradient Text, Text Reveal, Dia Text Reveal, Hyper Text, Word Rotate, Scroll Based Velocity, Sparkles Text, Morphing Text, Spinning Text, Text Highlighter, Text 3D Flip

### Device Mocks (3)
Safari, iPhone, Android

### Buttons (3)
Rainbow Button, Shimmer Button, Ripple Button

### Backgrounds (11)
Flickering Grid, Animated Grid Pattern, Retro Grid, Ripple, Dot Pattern, Grid Pattern, Hexagon Pattern, Striped Pattern, Interactive Grid Pattern, Light Rays, Noise Texture

### Community (15)
Shiny Button, File Tree, Code Comparison, Scroll Progress, Neon Gradient Card, Comic Text, Kinetic Text, Cool Mode, Pixel Image, Pulsating Button, Warp Background, Interactive Hover Button, Animated Circular Progress Bar, Backlight

## Usage pattern

```tsx
import { Marquee } from "@/components/magicui/marquee";
import { BorderBeam } from "@/components/magicui/border-beam";

export function Logos() {
  return (
    <Marquee pauseOnHover className="[--duration:20s]">
      {logos.map((l) => (
        <div key={l.name} className="relative rounded-xl border p-4">
          <img src={l.src} alt={l.name} className="h-8" />
          <BorderBeam size={80} duration={12} />
        </div>
      ))}
    </Marquee>
  );
}
```

## Gotchas

- Requires shadcn/ui already initialized (shares CSS variables + `cn` util). Run `npx shadcn@latest init` first.
- Confetti uses an imperative API — fire it from an event handler, not on every render.
- Pattern backgrounds (Dot/Grid) are cheap; Particles/Warp are heavier — respect reduced-motion.
- Globe (`cobe`) renders to canvas; keep one per viewport.
- Pair with bundui for full section blocks; Magic UI gives the moving parts, not whole layouts.

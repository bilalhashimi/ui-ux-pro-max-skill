# react-bits — Animated React Components

**Repo:** DavidHDev/react-bits · **Docs:** https://reactbits.dev · **License:** MIT + Commons Clause (you may use components in apps, but may not sell the components themselves as a product) · **Stars:** 20k+

## What it is

The largest creative library of animated React components — 130+ effects for **text, backgrounds, animations, and UI**. Each component ships in **4 variants**: JS-CSS, JS-Tailwind, TS-CSS, TS-Tailwind. Minimal deps, tree-shakeable, copy-paste or CLI.

## When to reach for it

- The hero/landing needs a **wow** animated background or animated headline.
- You want a specific creative effect (laser flow, metallic paint, pixel transition, image trail).
- Cursor / scroll / image creative effects.

Backup to Magic UI for shadcn-native special effects (beam, meteors, confetti).

## Install

Supports **shadcn** and **jsrepo**, plus manual copy. Per-component CLI command (pick variant suffix):

```bash
# shadcn registry — variant suffix: -JS-CSS | -JS-TW | -TS-CSS | -TS-TW
npx shadcn@latest add @react-bits/BlurText-TS-TW
npx shadcn@latest add @react-bits/Aurora-TS-TW
```

Or copy source directly from each component page. Some WebGL backgrounds pull `ogl` or `three`; text/animation components are lightweight.

## Dependencies

- Core: React 18+. Tailwind only for the `-TW` variants.
- WebGL backgrounds (Aurora, Galaxy, Hyperspeed, Silk, Plasma, Prism, LiquidEther, etc.): may require `ogl` and/or `three`.
- Some physics components may use `gsap` or `matter-js` — check the component's Dependencies tab.

## Full component catalog

### Text Animations (23)
ASCIIText, BlurText, CircularText, CountUp, CurvedLoop, DecryptedText, FallingText, FuzzyText, GlitchText, GradientText, RotatingText, ScrambledText, ScrollFloat, ScrollReveal, ScrollVelocity, ShinyText, Shuffle, SplitText, TextCursor, TextPressure, TextType, TrueFocus, VariableProximity

### Animations / effects (30)
AnimatedContent, Antigravity, BlobCursor, ClickSpark, Crosshair, Cubes, ElectricBorder, FadeContent, GhostCursor, GlareHover, GradualBlur, ImageTrail, LaserFlow, LogoLoop, MagicRings, Magnet, MagnetLines, MetaBalls, MetallicPaint, Noise, OrbitImages, PixelTrail, PixelTransition, Ribbons, ShapeBlur, SplashCursor, StarBorder, StickerPeel, Strands, TargetCursor

### Backgrounds (44, mostly WebGL/canvas)
Aurora, Balatro, Ballpit, Beams, ColorBends, DarkVeil, Dither, DotField, DotGrid, EvilEye, FaultyTerminal, Ferrofluid, FloatingLines, Galaxy, GradientBlinds, Grainient, GridDistortion, GridMotion, GridScan, Hyperspeed, Iridescence, LetterGlitch, LightPillar, LightRays, Lightfall, Lightning, LineWaves, LiquidChrome, LiquidEther, Orb, Particles, PixelBlast, PixelSnow, Plasma, PlasmaWave, Prism, PrismaticBurst, Radar, RippleGrid, ShapeGrid, SideRays, Silk, SoftAurora, Threads, Waves

### Components / UI (35)
AnimatedList, BorderGlow, BounceCards, BubbleMenu, CardNav, CardSwap, Carousel, ChromaGrid, CircularGallery, Counter, DecayCard, Dock, DomeGallery, ElasticSlider, FlowingMenu, FluidGlass, FlyingPosters, Folder, GlassIcons, GlassSurface, GooeyNav, InfiniteMenu, Lanyard, MagicBento, Masonry, ModelViewer, PillNav, PixelCard, ProfileCard, ReflectiveCard, ScrollStack, SpotlightCard, Stack, StaggeredMenu, Stepper, TiltedCard

## Usage pattern

```tsx
import Aurora from "@/components/Aurora/Aurora";
import BlurText from "@/components/BlurText/BlurText";

export function Hero() {
  return (
    <section className="relative h-dvh overflow-hidden">
      <Aurora className="absolute inset-0 -z-10" />     {/* GPU background */}
      <div className="relative z-10 flex h-full items-center justify-center">
        <BlurText text="Ship stunning interfaces" className="text-5xl font-bold" />
      </div>
    </section>
  );
}
```

## Gotchas

- **GPU cost.** Backgrounds are WebGL — one per page, above the fold. Lazy-mount or swap for a static image below the fold and on low-power devices.
- **Reduced motion.** Always gate heavy effects behind `prefers-reduced-motion` and offer a static fallback.
- **Contrast.** Never put body text directly over a busy animated background without a scrim/overlay (parent rule: `color-contrast`).
- **Variant pick.** Use `-TS-TW` in a TypeScript + Tailwind project. Mixing the `-CSS` variant drags in extra `.css` files.
- **Commons Clause.** Fine for apps/sites; do NOT repackage and sell the components themselves.

# stackzero/ui — E-commerce Components & Blocks

**Repo:** stackzero-labs/ui · **Docs:** https://ui.stackzero.co/docs · **License:** MIT · **Built for:** React + Next.js + Tailwind + shadcn/ui (+ motion)

## What it is

A collection of components purpose-built for **e-commerce and commerce apps** — the one library in this set that specializes in selling: product variant selectors, ratings, price formatting, quantity inputs, carts, reviews, and product galleries. shadcn-native.

## When to reach for it

- **Product variant selector** — color swatches, size pills, image variants, multi-attribute. (The headline component.)
- **Ratings** — star, fractional star, face, like, upvote (animated).
- **Price format** — currency formatting, sale/discount price display.
- **Quantity input**, **cart** UI, **reviews**, **product card**, **banners**, **address form**, **phone number input**.
- **Image carousel / image viewer** for product galleries (basic + motion).

## Install

shadcn registry, per component/block:

```bash
npx shadcn@latest add "https://ui.stackzero.co/r/variant-selector.json"
npx shadcn@latest add "https://ui.stackzero.co/r/rating-star.json"
npx shadcn@latest add "https://ui.stackzero.co/r/price-format.json"
# (confirm exact registry URL on each page)
```

## Dependencies

- shadcn/ui initialized (Tailwind + CSS vars + `cn`); `motion` for animated ratings/viewers.

## Catalog

### Components
- **image-carousel:** horizontal
- **image-viewer:** basic, motion
- **input:** icon
- **phone-number-input:** basic
- **price-format:** basic, sale
- **quantity-input:** basic
- **rating-face:** basic, gradient
- **rating-like:** like-rating
- **rating-star:** basic, fractions
- **rating-upvote:** basic, animated
- **variant-color-selector:** basic
- **variant-selector:** basic, images, multiple

### Blocks (full sections)
address, banners, carts, product-card, **product-variants**, reviews

## Usage pattern

```tsx
import { VariantSelector } from "@/components/ui/variant-selector";
import { PriceFormat } from "@/components/ui/price-format";
import { RatingStar } from "@/components/ui/rating-star";

<VariantSelector
  options={[{ label: "S" }, { label: "M" }, { label: "L" }]}
  value={size} onValueChange={setSize}
/>
<PriceFormat amount={4999} currency="USD" />        {/* $49.99 */}
<RatingStar value={4.5} fractions />
```

## Gotchas

- Requires shadcn init; shares tokens.
- Variant logic (which combos are in stock) is yours to wire — the component handles selection UI, not inventory.
- Combine with bundui ecommerce blocks for full PDP/listing layouts; stackzero gives the commerce-specific widgets.
- Ratings come in several flavors — pick one style and stay consistent.

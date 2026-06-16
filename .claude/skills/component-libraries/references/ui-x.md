# ui-x — Advanced shadcn-compatible Primitives

**Repo:** junwen-k/ui-x · **Docs:** https://ui-x.junwen-k.dev · **License:** MIT · **Built on:** React + Radix + Tailwind + shadcn conventions

## What it is

"Additional beautifully designed components you can copy and paste" — accessible, customizable, shadcn-compatible. Its sweet spot is **advanced form & input primitives** that shadcn doesn't ship: a complete date/time stack, combobox, dropzone, sortable, password input, virtualizer, timeline. Many ship as both a high-level component and a low-level `*-primitive` you can fully restyle.

## When to reach for it

- **Date & time inputs:** date-field, date-picker, date-time-field, date-time-range-field, time-field, calendar — the most complete date stack in this set.
- **Combobox** (typeahead select).
- **Dropzone** (file upload) — alternative to Kibo's.
- **Sortable** (drag-to-reorder lists).
- **Password input** with toggle.
- **Virtualizer** for long lists, **Timeline**, **Description list**, **Kbd**, **Native select**, **Badge group**, **Control group**, **Input base**, **File list**, **Confirmer**.

## Install

shadcn registry, per component:

```bash
npx shadcn@latest add "https://ui-x.junwen-k.dev/r/date-picker.json"
npx shadcn@latest add "https://ui-x.junwen-k.dev/r/combobox.json"
npx shadcn@latest add "https://ui-x.junwen-k.dev/r/dropzone.json"
# (confirm exact registry URL on each component page)
```

## Dependencies

- shadcn/ui initialized (Tailwind + CSS vars + `cn`); Radix primitives pulled per component.

## Component catalog

badge-group, calendar, combobox (+ combobox-primitive), confirmer, control-group, date-field, date-picker (+ date-picker-primitive), date-time-field (+ primitive), date-time-range-field (+ primitive), description-list, dropzone (+ dropzone-primitive), file-list, input-base, kbd, native-select, password-input (+ primitive), sortable, time-field, time, timeline, virtualizer

Plus shadcn-style **blocks**: authentication-01..04 and a large set of chart blocks (area / bar / line / pie / radar / radial variants).

## Usage pattern

```tsx
import { DatePicker } from "@/components/ui/date-picker";
import { Sortable, SortableItem } from "@/components/ui/sortable";

<DatePicker value={date} onValueChange={setDate} />
<Sortable value={items} onValueChange={setItems}>
  {items.map((i) => <SortableItem key={i.id} value={i.id}>{i.label}</SortableItem>)}
</Sortable>
```

## Gotchas

- Requires shadcn init; shares CSS vars + `cn`.
- Prefer the **primitive** variant when you need heavy custom styling; the standard variant for quick use.
- Overlaps Kibo on dropzone/combobox/calendar — if already using Kibo, stay there; otherwise ui-x's date stack is more complete.
- It's primitives/inputs, not marketing flair — combine with Magic UI/bundui for visuals.

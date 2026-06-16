# Kibo UI — High-Level shadcn/ui Extensions

**Repo:** shadcnblocks/kibo (haydenbleasel) · **Docs:** https://www.kibo-ui.com/docs · **License:** MIT · **Stars:** 3.8k+

## What it is

A custom shadcn registry of **composable, accessible, functional** components that go beyond shadcn primitives. Where shadcn wraps Radix, Kibo wraps the harder stuff (drag-and-drop, editors, charts, media) so you don't hand-roll it. Uses the same Tailwind CSS variable theming as shadcn — drops in seamlessly. This is the **functional/data-UI** workhorse of the set.

## When to reach for it

- App/data UI: **kanban, gantt, table, tree, calendar, contribution graph**.
- Developer UI: **code-block, snippet, sandbox, editor, comparison**.
- Media: **video-player, image-crop, image-zoom, stories, reel, deck**.
- Rich utilities shadcn lacks: **dropzone, color-picker, combobox, qr-code, rating, marquee, ticker**.

## Install

shadcn registry, per component:

```bash
npx shadcn@latest add @kibo-ui/kanban
npx shadcn@latest add @kibo-ui/gantt
npx shadcn@latest add @kibo-ui/code-block
npx shadcn@latest add @kibo-ui/editor
npx shadcn@latest add @kibo-ui/dropzone
# (confirm exact slug on each component's docs page)
```

## Dependencies

- shadcn/ui initialized (Tailwind + CSS vars + `cn`).
- Per-component headless deps installed automatically: e.g. kanban/gantt pull a dnd library; editor pulls Tiptap/ProseMirror-family deps; code-block pulls a syntax highlighter; table pulls TanStack Table.

## Full component catalog (41)

announcement, avatar-stack, banner, calendar, choicebox, **code-block**, color-picker, combobox, comparison, **contribution-graph**, credit-card, cursor, deck, dialog-stack, **dropzone**, **editor**, **gantt**, glimpse, image-crop, image-zoom, **kanban**, list, marquee, mini-calendar, pill, qr-code, rating, reel, relative-time, sandbox, snippet, spinner, status, stories, **table**, tags, theme-switcher, ticker, **tree**, typography, video-player

## Usage pattern (kanban)

```tsx
import { KanbanProvider, KanbanBoard, KanbanCard, KanbanCards, KanbanHeader }
  from "@/components/ui/kibo-ui/kanban";

<KanbanProvider columns={columns} data={features} onDataChange={setFeatures}>
  {(column) => (
    <KanbanBoard id={column.id} key={column.id}>
      <KanbanHeader>{column.name}</KanbanHeader>
      <KanbanCards id={column.id}>
        {(item) => <KanbanCard key={item.id} {...item} />}
      </KanbanCards>
    </KanbanBoard>
  )}
</KanbanProvider>
```

## Gotchas

- Must run `npx shadcn@latest init` first — Kibo relies on shadcn's CSS variables and `cn`.
- Components are **composable** (provider + sub-parts), not single black-box props — read the doc for the part names.
- kanban/gantt manage their own drag state; lift `onDataChange` to persist.
- editor is a lighter quick-win; for a full Notion-class editor with many plugins use **Plate** instead.
- table = TanStack-backed; for simple display, shadcn's `<Table>` is enough.
- AI: pair Kibo `editor` with KokonutUI `ai-*` blocks for an assistant surface.

# Plate (platejs) — Rich-Text Editor Framework

**Repo:** udecode/plate · **Docs:** https://platejs.org · **License:** MIT · **Stars:** 16k+ · **Built on:** Slate + React, ships with shadcn/ui components, has AI + MCP support

## What it is

A **framework** for building rich-text editors — not a single drop-in component. Architecture = **Framework · Plugins · Components**. You compose plugins (headings, lists, tables, mentions, AI, slash menu, etc.) onto a Slate-based core and render with provided shadcn/ui-styled components. This is the serious choice for Notion-like / WYSIWYG / AI writing editors.

## When to reach for it

- A real **rich-text / WYSIWYG / Notion-like editor** with extensibility.
- **AI-assisted writing** surface (`editor-ai`).
- You need fine control: custom blocks, marks, serialization (Markdown/HTML), collaboration hooks.

If you just need a quick lightweight editor, Kibo UI `editor` is faster; choose Plate when the editor is a core feature.

## Install

shadcn registry — start from a prebuilt editor kit, then add plugins:

```bash
# Full AI editor starting point
npx shadcn@latest add @plate/editor-ai

# Or a basic editor, then add capability plugins
npx shadcn@latest add @plate/editor-basic
```

Browse https://platejs.org for the catalog of plugin/component registry slugs.

## Architecture & plugin system

- **Framework core:** Slate value + React rendering, managed via Plate's `createPlateEditor` / `<Plate>` provider.
- **Plugins:** each feature (bold, heading, list, table, link, mention, slash command, AI, drag handle, input rules) is a plugin you register. "Plugin Input Rules" turn markdown-like typing (e.g. `# ` → H1) into formatting.
- **Components:** shadcn/ui-styled UI parts (toolbar, dropdowns, floating menus) that you copy in and wire to plugins.
- **AI + MCP:** first-class AI plugins and Model Context Protocol support for AI editing flows.

## Usage pattern (conceptual)

```tsx
import { Plate, usePlateEditor } from "platejs/react";
import { EditorKit } from "@/components/editor/editor-kit"; // plugins bundle from the kit
import { Editor, EditorContainer } from "@/components/ui/editor";

export function MyEditor() {
  const editor = usePlateEditor({ plugins: EditorKit });
  return (
    <Plate editor={editor}>
      <EditorContainer>
        <Editor placeholder="Type / for commands…" />
      </EditorContainer>
    </Plate>
  );
}
```

## Dependencies

- React + Slate family packages (pulled by the kit).
- shadcn/ui initialized (Plate's components use shadcn styling/CSS vars).
- Many small `@platejs/*` plugin packages — installed per feature.

## Gotchas

- It's a framework: expect to assemble plugins + components, not a one-liner. Start from a kit (`editor-ai` / `editor-basic`) and trim.
- shadcn must be initialized; Plate components share its tokens.
- Serialization (Markdown/HTML export) is plugin-driven — add the serializer plugin you need.
- Heavier than Kibo `editor`; only justified when editing is central to the product.
- Collaboration/Yjs is available but adds infra (a sync backend) — don't enable unless needed.

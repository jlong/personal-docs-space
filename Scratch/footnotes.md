---
tags: test, mcp
status: draft
---

# Footnotes Test

The Milkdown editor[^1] now supports GFM-style footnotes. This feature was inspired by GitHub's own implementation[^2], which brought footnotes to markdown fields across the platform in 2021.

Footnotes are particularly useful in technical documentation[^3] where authors need to reference supplementary information without breaking the reading flow. They work with both numeric and named identifiers[^naming].

## How It Works

When you write a footnote reference like `[^1]`, it renders as a superscript link. The corresponding definition appears at the bottom of the document in a dedicated section. Clicking the reference scrolls you to the definition[^scroll], and clicking the definition label scrolls you back.

## Use Cases

Footnotes shine in several contexts:

- **Knowledge bases** — cite sources without cluttering the main text[^kb]
- **Technical specs** — add implementation notes that only some readers need[^specs]
- **Meeting notes** — reference action items or follow-ups inline[^meetings]

The ProseMirror schema[^prosemirror] handles the node types, while CSS provides the visual styling. The navigation plugin adds the interactive scroll behavior between references and definitions.

## Edge Cases

Footnotes can contain rich content including **bold text**, *italics*, and `inline code`[^rich]. They can also reference URLs and other resources[^urls].

Multiple paragraphs can reference the same footnote[^reuse]. This is the second reference to the reuse footnote[^reuse].

[^1]: Milkdown is a plugin-driven WYSIWYG markdown editor framework built on top of ProseMirror and Remark.

[^2]: See the GitHub changelog announcement: "Footnotes now supported in Markdown fields" (September 30, 2021).

[^3]: Technical documentation benefits from footnotes because they keep the primary narrative clean while still providing depth for readers who want it.

[^naming]: Named identifiers like `[^naming]` are more descriptive than numeric ones and make the markdown source easier to maintain.

[^scroll]: The smooth scrolling is implemented via a ProseMirror plugin that intercepts click events on footnote elements.

[^kb]: Knowledge base articles often need to cite multiple sources. Footnotes keep the citations organized without requiring a separate references section.

[^specs]: Implementation notes in technical specs can be lengthy. Footnotes let you include them without overwhelming readers focused on the high-level design.

[^meetings]: Meeting notes with inline footnotes are easier to scan than notes where every action item interrupts the flow.

[^prosemirror]: ProseMirror is the underlying editor framework that powers Milkdown. It provides a robust document model with support for custom node types.

[^rich]: Footnote definitions support the same inline formatting as regular paragraphs.

[^urls]: For example, the GFM footnotes specification is documented in the micromark-extension-gfm-footnote package.

[^reuse]: A single footnote definition can be referenced from multiple locations in the document. Each reference links to the same definition.

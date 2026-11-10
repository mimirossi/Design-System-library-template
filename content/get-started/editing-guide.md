---
title: Editing guide
group: Get started
order: 20
description: How to add text, images, code, tokens and Figma frames to any page.
---

## How pages work

Every page is one Markdown file in the `content/` folder. Saving a change on GitHub republishes the site in about a minute.

- **Edit this page** at the top of any page opens that file in the GitHub editor.
- **Upload images** opens the image folder for that page.
- **New component page** at the bottom of the sidebar creates a page from the template.
- **Edit mode** in the top bar shows or hides placeholders and edit links. Switch it off to see the site as developers will.

The yellow dashed boxes are placeholders. Each one says what belongs there. Replace the box with the real content and the counter in the sidebar goes down.

## Page settings

The block between the `---` lines at the top of a file sets the page up.

```yaml
---
title: Button
group: Actions
order: 10
type: component
status: Draft
description: Triggers an action or event.
figma: https://www.figma.com/design/FILE/Name?node-id=1-2
---
```

| Field | What it does |
| --- | --- |
| `title` | Page title and sidebar label |
| `group` | Sidebar section. A new name creates a new section |
| `order` | Position inside the section, lowest first |
| `type` | `component` or `foundation`. Sections the template expects are flagged while missing |
| `status` | Free label next to the title: Draft, Beta, Stable, Deprecated |
| `description` | Line under the title, also used on overview cards |
| `figma` | Adds an "Open in Figma" button |

## Placeholders

A quote that starts with `[!TODO]` renders as a placeholder box. Delete it once the content is in.

```markdown
> [!TODO]
> **Anatomy.** Add the annotated image and list the parts.
```

## Images

Upload the file to `assets/images/<page-name>/`, then reference it. Text in quotes becomes the caption.

```markdown
![Button anatomy](assets/images/button/anatomy.png "The four parts of a button")
```

An image that is referenced but not uploaded yet shows a placeholder with the exact file name to upload, so the page template can list every image a page needs in advance.

## Code snippets

A fenced block gets syntax highlighting and a copy button.

```css title="button.css"
.button {
  border-radius: var(--radius-md);
}
```

Blocks with a `tab` label that follow each other are grouped. Adding `preview` to an HTML block renders it live, using the styles in `preview/preview.css`.

```html preview tab="HTML"
<button class="example-button">Primary</button>
<button class="example-button secondary">Secondary</button>
```

```jsx tab="React"
<Button>Primary</Button>
<Button variant="secondary">Secondary</Button>
```

That group is written like this:

````markdown
```html preview tab="HTML"
<button class="example-button">Primary</button>
```

```jsx tab="React"
<Button>Primary</Button>
```
````

## Do and don't

> [!DO]
> Use one primary button per view.

> [!DONT]
> Don't place two primary buttons side by side.

```markdown
> [!DO]
> Use one primary button per view.

> [!DONT]
> Don't place two primary buttons side by side.
```

`[!NOTE]` and `[!WARNING]` work the same way.

> [!NOTE]
> Notes are for context developers should not miss.

## Design tokens

Export the variables from Figma as JSON and upload the files to `tokens/`. A `tokens` block turns a file into a table with swatches and copyable CSS variable names. `path` limits the table to one group.

```tokens
file: tokens/example.tokens.json
path: color
```

````markdown
```tokens
file: tokens/example.tokens.json
path: color
```
````

Uploading a newer export under the same file name updates every table that reads it.

## Figma

Paste a Figma link on a line of its own and it becomes an embedded frame. Use **Copy link to selection** in Figma so the embed opens on the right component.

```markdown
https://www.figma.com/design/FILE_KEY/File-name?node-id=12-345
```

People viewing the page need view access to the Figma file to see the embed.

## Tables

```markdown
| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| `size` | `sm`, `md`, `lg` | `md` | Height of the control |
```

## Site settings

`site.config.json` holds the site title, the order of sidebar sections, the sections each page type must have, and the repository the edit links point to. `app/theme.css` holds fonts and colours of the site itself.

# Workspace Rules

This file defines the specific instructions and metadata standards for this Obsidian vault. These rules take precedence over general defaults, unless being overridden by skills or user-defined prompts.

## Note Generation Rules

Whenever creating a new Markdown note (.md) in this vault, always include the following YAML frontmatter fields at the top of the file:

```yaml
---
created: [YYYY-MM-DD]
category: 
tags:
  - tmp
---
```

- Do NOT generate over 2 tags and use tag hierarchy whenever necessary
- Automatically assign `category` while keeping the total number of category minimal. This means only creating a new category when absolutely necessary. Otherwise, an existing category from current vault should be used.
- The following section for available `category` should be updated by you every time after creating a new category. You should initialize it when it is empty.
- Whenever you create a new `category`, create a note inside `./Categories` which should included a `base` for indexing the category. The created `base` should be named after the `category` and should be put under `./Templates/Bases`

### The list of currently available `category`
- Clippings
- Meetings
- Projects
- Sparks
- Daily


## File locations

1. All generated notes should be by default put into `./Notes` folder, unless explicitly being asked to do differently.
2. For `Attachments`, put image files under `./Attachments/imgs` and other file types (such PDFs) under `./Attachments/PDFs`

## Links
Whenever providing web links or hyperlinks in notes, do not proceed unless if you are confident the link is correct and relevant to the context.

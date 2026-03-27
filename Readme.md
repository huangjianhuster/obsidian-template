This obsidian vault is a simplified version adopted from kepano's [How I use Obsidian](https://stephango.com/vault), extended with a modular agent-skill framework. 

This vault is suitable if you are looking for:
- a clean and simple vault structure for scientific usage
- pre-installed/configured AI skills (with obsidian-related skills and others)

## Basic Structure

```text
/
├── Attachments/    # Images, PDFs, and non-markdown assets
├── Categories/     # Dashboards (Indices for the vault)
│   ├── Projects.md # Active and archived projects dashboard
│   └── Sparks.md   # Idea and fleeting note collection
├── Clippings/      # Web captures and articles
│   └── 68 Bits...  # Example of captured external content
├── Daily/          # Daily journals (YYYY-MM-DD)
│   └── 2026-03-16  # Example of a time-stamped log
├── Notes/          # Active workspace and drafts
│   └── Example_p.. # Example of a specific project note
├── References/     # Permanent knowledge and research
│   └── Example_r.. # Example of static reference material
├── System/         # Agent skills, scripts, and configuration
└── Templates/      # Note and .base view templates
```

## Core Concepts

### 1. Dashboards (Categories)
Instead of searching through folders, use the notes in `/Categories` to navigate your vault. These notes often embed dynamic views (using Obsidian Bases) to show active projects or recent meetings.

### 2. Obsidian Bases
The vault uses `.base` files (found in `/Templates/Bases`) to create database-like views. These allow you to filter and sort notes by their YAML properties without manual indexing.

### 3. AI Skills
The `/System/Agents/ai/skills` directory defines specialized capabilities for AI agents interacting with this vault. Each skill includes procedural instructions and often helper scripts (Python/Bash) for advanced file processing.

### 4. Tags

You should completely rely on the `tags` field in the metadata header to organize notes. Check the yaml style metadata header example from:
```
./Notes/Example_project

### which has the following header
---
categories:
  - "[[Projects]]"
start: 2025-10-01
end: 2025-12-30
tags:
 - biophysics
---
```

For different categories of notes, you should create a template (inside `./Templates`, check examples there) to help you automatically generate the header, instead of typing manually.


## Get Started

1. **Download the Vault**, and use Obsidian to open it.
2. **Explore Dashboards**: Open `Categories/Projects.md` or `Categories/Sparks.md`. Modify to your own preference.
3. **Daily Logging**: the "Daily Note" should only be used as indexing; All notes created in a specific date will be shown here.
4. Use `unique note creator` (from core plugins in obsidian) for creating new notes and apply a specific template.
5. **Templates**: Use the `Templates/` folder when creating new projects or meeting notes to ensure consistent metadata.


---
name: create-copilot-toolbook-html
description: |-
  Creates standalone interactive HTML handbooks from the English `copilot-toolbox` list in two language versions: English and German. Groups tools by category, adds collapsible sections, search, and a blue/orange Copilot Toolbook design with author and GitHub attribution.

  Use when the user says:
    - "create-copilot-toolbook-html"
    - "make a German and English HTML handbook"
    - "create bilingual toolbook pages"
    - "export the toolbox as searchable HTML manuals"
    - "generate the Copilot Toolbook"
---
---
author: Michael Greth - yourcopilot.de
source: github.com/mysharepoint
version: 1.0
---
# Create Copilot Toolbook HTML

## When to use
Use this skill when the user wants to generate standalone, interactive HTML handbooks from the English `copilot-toolbox` SharePoint list. Generate two static HTML files by default: one English version and one German version.

The output files must be self-contained HTML files with no external scripts, fonts, or CSS dependencies. They should be suitable for publishing or sharing as static reference pages.

## Inputs
- Target site: current SharePoint site unless the user names another site.
- Source list title: `copilot-toolbox` unless the user provides another list.
- English output title: `Copilot Toolbook`.
- German output title: `Copilot Toolbook` or `Copilot-Toolbook`.
- English output file name: `copilot-toolbook-en.html` unless the user provides another file name.
- German output file name: `copilot-toolbook-de.html` unless the user provides another file name.
- Author attribution: `Michael Greth - yourcopilot.de`.
- Source attribution: `github.com/mysharepoint`.
- Design: blue/orange, clean, modern, readable.

## Expected source columns
Read these fields where present:
- `Title`
- `description`
- `Category`
- `Purpose`
- `UseCase`
- `Example`
- `PromptTemplate`
- `KeyParameters`
- `Prerequisites`
- `Complexity`
- `OutputType`
- `Status`
- `Tags`
- `Source`
- `FirstSeen`
- `LastSeen`
- `RemovedOn`
- `ReviewNotes`

Required field: `Title`. If optional fields are missing, generate the HTML with the available fields.

## Language behavior
Generate two versions:

### English version
- UI labels, section headings, search placeholder, status explanations, and metadata labels are in English.
- List content is shown as stored in the source list.

### German version
- UI labels, section headings, search placeholder, status explanations, and metadata labels are in German.
- Do not machine-translate tool names or stored source content unless the user explicitly requests translation.
- Keep original tool descriptions from `description` unchanged.
- German label examples:
  - Search tools → `Tools durchsuchen`
  - Total tools → `Tools gesamt`
  - Categories → `Kategorien`
  - Purpose → `Zweck`
  - Use Case → `Anwendungsfall`
  - Example → `Beispiel`
  - Prompt Template → `Prompt-Vorlage`
  - Key Parameters → `Wichtige Parameter`
  - Prerequisites → `Voraussetzungen`
  - Review Notes → `Review-Hinweise`
  - Removed → `Entfernt`
  - Archived → `Archiviert`

## Steps
1. Resolve the `copilot-toolbox` list on the current site. If it cannot be found, tell the user to run `create-copilot-toolbox` first.
2. Use `get_list_schema(...)` only when needed to confirm fields or item count.
3. Use `list_items(...)` to read all toolbox items. Use the list item count as `rowLimit` when known; otherwise use a sufficiently large row limit with explicit `viewFields`.
4. Include all tools by default, but visually distinguish `new`, `active`, `archived`, and `removed` status values. If the user requests only active tools, filter accordingly.
5. Use `execute_code(...)` with `outputDataRef: true` to generate the complete HTML string or a JSON object containing both HTML files. HTML output must be stored via `outputDataRef` before creating files.
6. Generate both HTML files with the same data and layout, changing only UI language labels and explanatory text.
7. The generated HTML must be standalone:
   - Inline CSS only.
   - Inline JavaScript only.
   - No remote scripts, fonts, images, or stylesheets.
   - Escape all list content before inserting it into HTML.
8. Structure each page:
   - Header with `Copilot Toolbook` title.
   - Subtitle describing it as an interactive handbook for Copilot-in-SharePoint / agent tools.
   - Attribution: `Michael Greth - yourcopilot.de` and `github.com/mysharepoint`.
   - Summary cards: total tools, active/new/removed/archived counts, category count.
   - Search input at the top.
   - Category sections sorted alphabetically.
   - Each category is collapsible/expandable.
   - Each tool appears as a card or row with visible tool name, status badge, description, purpose, use case, example, prompt template, key parameters, prerequisites, complexity, output type, tags, and review notes where available.
9. Client-side search behavior:
   - Search across tool name, description, category, purpose, use case, example, prompt template, key parameters, prerequisites, tags, and review notes.
   - Hide non-matching tools while typing.
   - Show matching categories automatically expanded.
   - Show a result count.
   - Include a clear-search control if practical.
10. Design requirements:
   - Blue/orange palette.
   - Use a deep blue header, orange accent lines/buttons/badges, light background, readable cards.
   - Status badges should be visually distinct.
   - Make the layout responsive for desktop and mobile.
11. Save both HTML files with `create_file(...)` in the current document library or a sensible output library if the user specified one. If no destination is clear, create them in the current library.
12. Return both file URLs and a concise generation report.

## Output format
Return a short report:
- `Result`: created / failed.
- `Source list`: list used and item count.
- `English output`: file name and URL.
- `German output`: file name and URL.
- `Content`: number of categories and tools included.
- `Notes`: skipped fields, filters applied, missing optional columns, or untranslated source content.

## HTML implementation guidance
Each HTML file should include:
- `<input id="searchBox" type="search">`
- category containers with `data-category`.
- tool cards with a combined lowercase searchable text in `data-search`.
- JavaScript functions for filtering, expanding/collapsing categories, updating result count, and clearing search.
- CSS variables such as `--blue`, `--blue-dark`, `--orange`, `--bg`, `--card`, `--text`.

## Constraints
- Do not invent tool documentation that is not in the list.
- Do not overwrite the source list.
- Do not use external assets or network resources.
- Escape user/list content before inserting into HTML.
- Generate English and German handbook files by default.
- Do not translate stored tool descriptions unless explicitly requested.
- If list reading, HTML generation, or file creation fails, say so plainly and do not claim the handbook was created.
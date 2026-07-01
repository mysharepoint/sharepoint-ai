---
name: create-copilot-toolbox
description: |-
  Creates a generalized English-only `copilot-toolbox` list on the current SharePoint site for documenting agent tools. Intended for GitHub installation on a new site; includes status values `new`, `active`, `archived`, `removed` and update-safe category choices.

  Use when the user says:
    - "create-copilot-toolbox"
    - "create the copilot-toolbox list on this site"
    - "set up the English tool documentation list"
    - "install the GitHub toolbox"
    - "create a new copilot-toolbox list from the skill"

author: Michael Greth - yourcopilot.de
source: github.com/mysharepoint
version: 1.0

---
# Create Copilot Toolbox

## When to use
Use this skill when a site needs a fresh, reusable, English-only `copilot-toolbox` SharePoint list for documenting Copilot-in-SharePoint tools. It is intended for installation from a portable GitHub package into a new SharePoint site: the user installs the skill in that site's Agent Assets, invokes it, and the skill creates or configures the list in that site.

Do not treat any demo list as the target unless the user is currently on that site and explicitly asks to run it there. Do not change an existing bilingual list unless the user explicitly asks for migration or modernization.

## Inputs
- Target site: current SharePoint site where the skill is invoked, unless the user names another site.
- Target list title: `copilot-toolbox` unless the user provides a different name.
- Setup mode:
  - `new setup` by default: create the English list structure on the current site.
  - `existing list safe update`: only if a `copilot-toolbox` list already exists on the current site.
  - `migration`: only when the user explicitly asks to migrate an old bilingual structure.
- Required status values: `new`, `active`, `archived`, `removed`.

## Recommended English schema
Create or ensure these columns. Use stable internal names when possible.

| Display name | Internal name | Type | Required | Notes |
|---|---|---:|---:|---|
| Tool Name | `Title` | Text | Yes | Primary key for tool comparison. |
| Description | `description` | Multiple lines | No | Store the original tool description verbatim from the tool catalog or `--agenttools`. |
| Category | `Category` | Choice | No | Functional grouping. Keep choices updateable; add new category choices discovered by update skill. |
| Purpose | `Purpose` | Multiple lines | No | Short human-readable purpose. |
| Use Case | `UseCase` | Multiple lines | No | When to use this tool. |
| Example | `Example` | Multiple lines | No | Example user request. |
| Prompt Template | `PromptTemplate` | Multiple lines | No | Reusable prompt wording. |
| Key Parameters | `KeyParameters` | Multiple lines | No | Important parameters, not full schemas. |
| Prerequisites | `Prerequisites` | Multiple lines | No | Context, permissions, or prior tool calls. |
| Complexity | `Complexity` | Choice | No | `Simple`, `Intermediate`, `Advanced`. |
| Output Type | `OutputType` | Choice | No | `Data`, `File`, `Navigation`, `Confirmation`, `Schema`, `UI Panel`, `Image`, `Form`. |
| Status | `Status` | Choice | No | `new`, `active`, `archived`, `removed`. |
| Tags | `Tags` | Multiple lines | No | Search keywords, comma-separated. |
| Source | `Source` | Choice | No | `tool-catalog`, `--agenttools`, `manual`, `generated`. |
| First Seen | `FirstSeen` | DateTime | No | Optional tracking for update skill. |
| Last Seen | `LastSeen` | DateTime | No | Optional tracking for update skill. |
| Removed On | `RemovedOn` | DateTime | No | Set when a tool disappears from the current catalog. |
| Review Notes | `ReviewNotes` | Multiple lines | No | Editorial notes. |

### Status semantics
- `new`: detected in the current catalog but not yet reviewed.
- `active`: available in the current catalog and editorially reviewed.
- `archived`: manually archived or kept as historical documentation; not automatically set by normal catalog diff.
- `removed`: no longer present in the current catalog / `--agenttools` source. Do not delete removed tools.

### Initial category choices
Use these English category values as starting choices. The update skill may add new category choices later when a current tool source contains a category not yet in the field.
- File reading and analysis
- File creation
- File management
- Lists and libraries
- List items
- Views and formatting
- Search and discovery
- Automation and rules
- Approvals
- Permissions and sharing
- Field value resolution
- Navigation and context
- Skills and agents
- OneDrive
- Recycle bin and restore
- Code and visualization
- Users and organization
- Templates and forms
- Uncategorized

## Steps
1. Work against the current site where the skill is invoked. Do not use hard-coded site URLs.
2. Check whether a list named `copilot-toolbox` already exists only to avoid duplicate creation.
3. If the list does not exist, create it with the English schema above.
4. If the list already exists, add only missing English columns and missing choice values. Do not delete or rename existing columns automatically.
5. Ensure the `Status` choice field contains `new`, `active`, `archived`, and `removed`.
6. Ensure the `Category` choice field contains the initial category choices above, including `Uncategorized`. Add missing category choices; do not remove existing choices.
7. Preserve `Title` as the tool key and `description` as the original unmodified tool description field.
8. Create useful standard views if the available SharePoint tools support view creation: `All Tools`, `New Tools`, `Active Tools`, `Removed Tools`, `Archived Tools`, and `By Category`.
9. Migration from older bilingual columns is optional and only runs if explicitly requested. If requested, map English values without overwriting populated target fields: `ZweckEN` → `Purpose`, `AnwendungEN` → `UseCase`, `BeispielEN` → `Example`, `PromptVorlageEN` → `PromptTemplate`, `Schluesselparameter` → `KeyParameters`, `Vorbedingung` → `Prerequisites`, German complexity/output/status choices to their English equivalents only when explicitly requested.
10. If a SharePoint tool fails or returns empty, say so plainly and stop rather than inventing schema state.

## Output format
Return a short setup report:
- `Result`: created / updated / already configured / failed.
- `Target site`: site where the list was created or checked.
- `List`: list title and URL if available.
- `Columns`: created, already present, skipped.
- `Choices`: status, category, complexity, and output type values confirmed.
- `Views`: created or skipped.
- `Notes`: whether migration was not run, because this is a new setup.

## Constraints
- Default behavior is new setup on the current site, not migration of a demo list.
- Do not delete old columns automatically.
- Do not overwrite editorial fields unless explicitly requested.
- Keep `Title` as the tool key and `description` as the original unmodified tool description.
- Keep status semantics compatible with the update skill: new tools are `new`, reviewed tools are `active`, manually archived tools are `archived`, missing tools are `removed`.
- Do not invent unavailable tools, parameters, or descriptions.
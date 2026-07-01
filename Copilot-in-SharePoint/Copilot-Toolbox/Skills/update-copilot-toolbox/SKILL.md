---
name: update-copilot-toolbox
description: |-
  Updates and enriches the English `copilot-toolbox` list from `--agenttools` or the available tool catalog. Adds new tools as `new`, marks disappeared tools as `removed`, fills empty documentation fields such as Category, Purpose, Use Case, Example, Prompt Template, Key Parameters, Prerequisites, Complexity, and Output Type, and preserves reviewed content.

  Use when the user says:
    - "update-copilot-toolbox"
    - "update the copilot-toolbox list"
    - "sync the English toolbox from --agenttools"
    - "fill missing toolbox columns"
    - "refresh the GitHub toolbox list"
---
---
author: Michael Greth - yourcopilot.de
source: github.com/mysharepoint
version: 1.0
---
# Update Copilot Toolbox

## When to use
Use this skill when the English `copilot-toolbox` list on the current SharePoint site should be synchronized and enriched from the currently available Copilot-in-SharePoint / agent tool catalog, especially from a pasted `--agenttools` output.

This skill is part of a portable GitHub package. It must work on the current site where it is installed and invoked. Do not use hard-coded site URLs, list IDs, or demo-specific column names.

## Inputs
- Target site: current SharePoint site unless the user names another site.
- Target list title: `copilot-toolbox` unless the user provides another name.
- Source of current tools:
  1. Prefer a user-provided `--agenttools` output.
  2. Otherwise use the currently available tool names and tool descriptions from the tool catalog, if available.
- Key column: `Title` / display name `Tool Name`.
- Original tool description column: `description`.
- Status values: `new`, `active`, `archived`, `removed`.

## Expected list schema
The target list should normally be created by the `create-copilot-toolbox` skill. Use these internal names when reading or writing:
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

Required for sync: `Title`, `description`, `Status`. Optional documentation fields should be filled when present. If optional fields are missing, continue with available fields and report the skipped fields.

## Status semantics
- `new`: tool exists in the current catalog but is not yet editorially reviewed.
- `active`: tool exists in the current catalog and has been reviewed.
- `archived`: manual/historical archive state. Do not use this automatically for tools that simply disappeared from the current catalog.
- `removed`: tool no longer appears in the current catalog / `--agenttools` output. Do not delete the item.

## Documentation enrichment rules
Fill these fields for new tools and for existing tools where the field is empty:

- `Category`: classify the tool into one of the existing category choices or a newly discovered source category.
- `Purpose`: one concise sentence describing what the tool is for.
- `UseCase`: one concise sentence describing when a user or agent should use it.
- `Example`: one realistic user request that would trigger the tool.
- `PromptTemplate`: one reusable prompt template with placeholders such as `[file]`, `[list]`, `[recipient]`, or `[topic]`.
- `KeyParameters`: comma-separated important parameters or inputs. Prefer real parameter names from `--agenttools` / tool schema if available; otherwise list conceptual inputs conservatively.
- `Prerequisites`: required context, permissions, prior lookup, or `None` when there is no obvious prerequisite.
- `Complexity`: choose `Simple`, `Intermediate`, or `Advanced`.
- `OutputType`: choose one of `Data`, `File`, `Navigation`, `Confirmation`, `Schema`, `UI Panel`, `Image`, `Form`.
- `Tags`: comma-separated search keywords derived from the tool name, category, and description.

Do not overwrite populated documentation fields unless the user explicitly asks to regenerate or refresh editorial content. Treat generated documentation as draft/reference text; do not claim it is Microsoft-authored.

### Classification guidance
Use the tool name and original description to classify conservatively:

- File reading and analysis: `cat_file`, `digest_file`, `grep_contents`, `semantic_search`, `analyze_image`, version comparison/read tools.
- File creation: `create_file`, `create_chart`, PDF conversion, form/document collection creation.
- File management: copy, move, rename, delete/recycle files, create folders, folder colors, shortcuts.
- Lists and libraries: list/library discovery, schema, create/update list, delete list, views.
- List items: create, update, batch update, delete list items, item versions.
- Views and formatting: view definitions, view formatting, column formatting, preview view changes.
- Search and discovery: find items, search content, internet search.
- Automation and rules: quick steps, rules, rule panels, workflow-like configuration.
- Approvals: approvals configuration, create approval request, approval status, resolve approval.
- Permissions and sharing: check permissions, share, unshare.
- Field value resolution: user, lookup, taxonomy, location, datetime, sensitivity labels, term sets.
- Navigation and context: current list/library, navigate to URL, context file.
- Skills and agents: load skill, create skill, function call result.
- OneDrive: OneDrive details, favorites.
- Recycle bin and restore: recycle bin contents, restore items/lists.
- Code and visualization: execute code, charts, dashboards, generated reports.
- Users and organization: org chart, user info.
- Templates and forms: create forms, document collection forms, template-like creation.

### Complexity guidance
- `Simple`: single-step read, lookup, navigation, sharing, or direct create/update with known inputs.
- `Intermediate`: operations needing prior discovery, batching, filters, special value resolution, or multi-field updates.
- `Advanced`: destructive/irreversible operations, code generation, complex formatting, automation, approvals, schema creation, cross-version analysis, or multi-step orchestration.

### Output type guidance
- `Data`: returns metadata, search results, summaries, schema, values, or analysis.
- `File`: creates or converts a file, chart image, document, presentation, spreadsheet, or HTML.
- `Navigation`: opens or navigates to a URL/panel.
- `Confirmation`: performs an action and returns success/failure.
- `Schema`: returns or changes list/library structure.
- `UI Panel`: opens SharePoint UI panels.
- `Image`: returns an image analysis or generated image reference.
- `Form`: creates or returns form URLs.

## Steps
1. Resolve the `copilot-toolbox` list on the current site. If it cannot be found, tell the user to run `create-copilot-toolbox` first.
2. Use `get_list_schema(...)` to confirm fields and choice values when needed. Confirm that `Status` supports `new`, `active`, `archived`, and `removed`.
3. If `Status` is missing `removed`, update the list schema/choice field before changing item statuses. Do not proceed to set `removed` until the choice exists.
4. Confirm current `Category`, `Complexity`, and `OutputType` choices. Add missing choices before writing values. Never remove old choice values automatically.
5. Parse the current tool list from `--agenttools` or from the available tool catalog:
   - Normalize tool names only for comparison: trim and lowercase.
   - Store the original tool name exactly in `Title`.
   - Store the original tool description verbatim in `description`; do not rewrite it.
   - Extract source category and parameter names if the source provides them.
6. Build enrichment values for each current tool using the documentation enrichment rules. If a field cannot be inferred safely, leave it blank except `Category`, where `Uncategorized` may be used.
7. Before creating or updating items, compare generated/source categories with existing `Category` choices. Add every missing category choice before writing items that use it.
8. Use `list_items(...)` to load existing entries. Retrieve at least `ID`, `Title`, `description`, `Category`, `Purpose`, `UseCase`, `Example`, `PromptTemplate`, `KeyParameters`, `Prerequisites`, `Complexity`, `OutputType`, `Status`, `Tags`, `Source`, `FirstSeen`, `LastSeen`, `RemovedOn`, `ReviewNotes` where present.
9. Use `execute_code(...)` for comparison and enrichment preparation when useful. Produce groups: `new`, `present`, `removed`, `descriptionMissing`, `documentationMissing`, and `reactivated`.
10. Create missing tools with `create_list_items_v2(...)`. Set all available fields that can be safely populated:
   - `Title` = original tool name
   - `description` = original tool description
   - `Category`, `Purpose`, `UseCase`, `Example`, `PromptTemplate`, `KeyParameters`, `Prerequisites`, `Complexity`, `OutputType`, `Tags`
   - `Status` = `new`
   - `Source` = `--agenttools` or `tool-catalog` if the column exists
   - `FirstSeen` = current UTC date/time if the column exists
   - `LastSeen` = current UTC date/time if the column exists
11. Update existing present tools conservatively:
   - Set `LastSeen` to the current UTC date/time if the column exists.
   - Clear `RemovedOn` if the column exists and the tool is present again.
   - Fill `description` only when it is empty and the original description is available.
   - Fill empty documentation fields using the generated enrichment values.
   - Do not overwrite populated editorial fields unless the user explicitly asks for regeneration.
   - Do not automatically change `new` to `active`; `new` means discovered but not reviewed.
   - If a tool is currently available and has `Status = removed`, set it to `active` and mention it as reactivated.
   - If a tool is `archived`, do not reactivate it automatically unless the user explicitly asks.
12. Mark disappeared tools as removed:
   - Set `Status = removed`.
   - Set `RemovedOn` to the current UTC date/time if the column exists.
   - Do not delete list items.
   - Do not clear descriptions or editorial fields.
   - Do not change tools already marked `archived`; archived is a manual/historical state.
13. If the user explicitly requests full active marking, set currently available non-new, non-archived tools to `active`; otherwise preserve `new` until human review.
14. If a SharePoint tool fails or returns empty, say so plainly and stop rather than inventing update results.

## Output format
Return a short report:
- `Result`: existing tools / current tools detected / created / updated / removed.
- `New`: tool names created with `Status = new`.
- `Removed`: tool names set to `Status = removed`.
- `Reactivated`: removed tools found again and set to `active`.
- `Categories`: newly added category choices, or `none`.
- `Documentation`: number of tools where empty documentation fields were filled.
- `Descriptions`: number of descriptions newly set or filled.
- `Tracking`: number of `LastSeen`, `FirstSeen`, and `RemovedOn` values updated, if those columns exist.
- `Notes`: missing source information, missing columns, skipped populated editorial fields, or choice-value issues.

## Constraints
- Do not invent tool names or capabilities beyond the original description / tool schema / `--agenttools` source.
- Keep the original tool description in `description` unchanged.
- Generated `Purpose`, `UseCase`, `Example`, `PromptTemplate`, `KeyParameters`, `Prerequisites`, `Complexity`, `OutputType`, and `Tags` are allowed, but must be conservative and derived from the tool name, description, or schema.
- Do not delete tools that disappeared; mark them `removed`.
- Do not automatically mark disappeared tools as `archived`; reserve `archived` for manual/historical archive state.
- Do not remove old category choices automatically.
- Add new category choices before writing item values that use them.
- Do not overwrite populated editorial fields unless the user explicitly requests a regeneration.
- Do not use hard-coded site URLs or list IDs.
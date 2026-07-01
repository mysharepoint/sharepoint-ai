---
author: Michael Greth - yourcopilot.de
source: github.com/mysharepoint
version: 1.0
---

# Copilot Toolbook Site Context

## Purpose

This site hosts the Copilot Toolbook: a dynamic, interactive handbook for agent tools in Copilot for SharePoint.

Copilot in SharePoint provides built-in tools and skills for working with files, lists, libraries, search, automation, approvals, permissions, visualization, and related SharePoint tasks. This set stores those tools in a structured SharePoint list and generates searchable HTML handbooks from that list.

## Standard list

List name: `copilot-toolbox`

Purpose: English-only tool documentation list for tracking available tools, original descriptions, categories, examples, prerequisites, lifecycle status, and review notes.

## Required skills

Install these skills in `Agent Assets / Skills`:

- `create-copilot-toolbox`
- `update-copilot-toolbox`
- `create-copilot-toolbook-html`

## Workflow

1. Run `create-copilot-toolbox` once to create the `copilot-toolbox` list structure.
2. Run `update-copilot-toolbox` whenever a new `--agenttools` output or updated tool catalog is available.
3. Review items with `Status = new`; after editorial review, set them to `active`.
4. Run `create-copilot-toolbook-html` to generate two standalone HTML handbooks:
   - `copilot-toolbook-en.html`
   - `copilot-toolbook-de.html`

## Status logic

- `new`: newly detected, not reviewed yet.
- `active`: reviewed and currently available.
- `removed`: no longer found in the current tool catalog or `--agenttools` output.
- `archived`: manually archived or kept as historical documentation.

Do not delete missing tools automatically. Mark them as `removed`. After review, removed tools may be manually archived.

## Important fields

- `Title`: tool name and comparison key.
- `description`: original tool description, stored unchanged.
- `Category`: functional category. New categories may be added by the update skill.
- `Purpose`: short explanation of what the tool is for.
- `UseCase`: when the tool should be used.
- `Example`: sample user request.
- `PromptTemplate`: reusable prompt wording.
- `KeyParameters`: important parameters or inputs.
- `Prerequisites`: required context, permissions, or prior tool calls.
- `Complexity`: `Simple`, `Intermediate`, or `Advanced`.
- `OutputType`: expected output type.
- `Status`: lifecycle status.
- `Tags`: search keywords.
- `FirstSeen`: when the tool was first detected.
- `LastSeen`: when the tool was last detected.
- `RemovedOn`: when the tool disappeared from the current catalog.
- `ReviewNotes`: editorial or technical review notes.

## HTML handbooks

The `create-copilot-toolbook-html` skill creates standalone interactive HTML files with:

- categories sorted alphabetically,
- collapsible category sections,
- client-side search,
- status badges,
- blue/orange Copilot Toolbook design,
- author attribution: `Michael Greth - yourcopilot.de`,
- source attribution: `github.com/mysharepoint`.

The German HTML version translates the interface labels, not the stored tool descriptions, unless explicitly requested.

## Safety rules

- Do not invent tool names, parameters, or capabilities.
- Do not overwrite editorial fields during updates.
- Store original tool descriptions unchanged in `description`.
- Add newly discovered category choices before writing items that use them.
- Treat this as a technical deployment package. If Microsoft changes the tool structure, naming, or availability after July 1, 2026, review and update the package logic.

## Version note

Package baseline: July 1, 2026.

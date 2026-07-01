---
author: Michael Greth - yourcopilot.de
source: github.com/mysharepoint
version: 1.0
---

# Copilot Toolbook for SharePoint

Baseline: July 1, 2026

## Overview

Copilot Toolbook for SharePoint is a technical deployment package for creating a dynamic handbook of agent tools in Copilot for SharePoint.

Copilot in SharePoint includes built-in tools and skills for working with files, lists, libraries, search, automation, approvals, permissions, visualization, and related SharePoint tasks. This package captures those tools in a structured SharePoint list and generates standalone, searchable HTML handbooks from that list.

## Package contents

```text
AgentAssets/
  SHAREPOINT.md
  Skills/
    create-copilot-toolbox/
      SKILL.md
    update-copilot-toolbox/
      SKILL.md
    create-copilot-toolbook-html/
      SKILL.md
```

## Skills

### create-copilot-toolbox

Creates the SharePoint list `copilot-toolbox` on the current site.

The list stores structured tool documentation, including tool name, original description, category, purpose, use case, examples, prompt templates, key parameters, prerequisites, status, and review notes.

### update-copilot-toolbox

Updates the `copilot-toolbox` list from the current tool catalog or a pasted `--agenttools` output.

Update behavior:

- New tools are added with `Status = new`.
- Existing tools are preserved.
- Tools no longer found in the current catalog are marked `removed`.
- Manually archived tools remain `archived`.
- New categories discovered during update are added to the `Category` choice field before items are written.

After an update, users should review new tools and set them to `active` when validated. Removed tools can later be archived manually if they should remain as historical documentation.

### create-copilot-toolbook-html

Creates two standalone interactive HTML handbooks from the `copilot-toolbox` list:

- `copilot-toolbook-en.html` – English version
- `copilot-toolbook-de.html` – German version

The handbooks include:

- category-based structure,
- collapsible sections,
- client-side search,
- status badges,
- blue/orange Copilot Toolbook design,
- author attribution,
- GitHub source attribution.

The German version translates the interface labels, not the stored tool descriptions, unless explicitly requested.

## List fields

| Field | Purpose |
|---|---|
| `Title` | Tool name and comparison key |
| `description` | Original tool description, stored unchanged |
| `Category` | Functional category |
| `Purpose` | Short explanation of what the tool is for |
| `UseCase` | Typical use case |
| `Example` | Example user request |
| `PromptTemplate` | Reusable prompt wording |
| `KeyParameters` | Important parameters or inputs |
| `Prerequisites` | Required context, permissions, or prior tool calls |
| `Complexity` | `Simple`, `Intermediate`, or `Advanced` |
| `OutputType` | Expected output type |
| `Status` | Lifecycle status |
| `Tags` | Search keywords |
| `Source` | Source of the tool entry |
| `FirstSeen` | When the tool was first detected |
| `LastSeen` | When the tool was last detected |
| `RemovedOn` | When the tool disappeared from the current catalog |
| `ReviewNotes` | Editorial or technical review notes |

## Status values

| Status | Meaning |
|---|---|
| `new` | Newly detected and not reviewed yet |
| `active` | Reviewed and currently available |
| `removed` | No longer present in the current tool catalog or `--agenttools` output |
| `archived` | Manually archived or retained as historical documentation |

## Deployment steps

1. Copy the files into the target site's Agent Assets library.
2. Install the three skill folders under `AgentAssets/Skills`.
3. Add `SHAREPOINT.md` to the target site's Agent Assets context.
4. Run `create-copilot-toolbox` once to create the list structure.
5. Run `update-copilot-toolbox` to populate or refresh the list.
6. Review `new` items and set validated entries to `active`.
7. Run `create-copilot-toolbook-html` to generate the English and German HTML handbooks.

## Notes

This package is a technical deployment package. If Microsoft changes the structure, naming, or availability of Copilot for SharePoint agent tools after July 1, 2026, the list schema, update logic, or handbook generation may need to be adjusted.

Do not delete missing tools automatically. Mark them as `removed` and review them manually before archiving.

## License and disclaimer

This project is provided under the terms of the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this project and associated documentation files, to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the project, and to permit persons to whom the project is furnished to do so, subject to the inclusion of the copyright notice and this permission notice in all copies or substantial portions of the project.

The project is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the project or the use or other dealings in the project.

Use of this project is at your own risk. No guarantee is given that the package will work in every Microsoft 365 tenant, SharePoint environment, Copilot configuration, or future product version. Always review, test, and validate the generated lists, skills, and HTML output before using them in a production environment.

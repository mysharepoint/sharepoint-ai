# Copilot in SharePoint — Tool Reference

> **75 tools** across **18 categories** — the complete toolbox for Copilot in SharePoint.

Each tool has its own Markdown file with YAML frontmatter, bilingual descriptions (EN/DE), examples, prompt templates, and key parameters.

## Categories

### Read & Analyze

📁 `read-and-analyze/` — 6 tools

| Tool | Purpose |
|------|----------|
| [analyze-image](read-and-analyze/analyze-image.md) | Analyzes SharePoint/OneDrive images using AI vision (GPT-4o). |
| [cat-file](read-and-analyze/cat-file.md) | Reads file content. Text files directly, Office docs and PDFs are extracted automatically. |
| [compare-file-versions](read-and-analyze/compare-file-versions.md) | Analyzes changes in Word, PowerPoint, or Excel documents across versions. |
| [digest-file](read-and-analyze/digest-file.md) | Summarizes and compares files using a specialized M365 file analysis agent. |
| [grep-contents](read-and-analyze/grep-contents.md) | Searches files for exact text or regex; returns matched lines with context. |
| [semantic-search](read-and-analyze/semantic-search.md) | Searches files by topic or concept (semantic). Returns matched passages with context. |

### Create Files

📁 `create-files/` — 2 tools

| Tool | Purpose |
|------|----------|
| [create-file](create-files/create-file.md) | Creates new files: text, PDF, Word (.docx), PowerPoint (.pptx), Excel (.xlsx). |
| [create-chart](create-files/create-chart.md) | Creates charts from data – bar, line, pie, scatter – no code needed. |

### Manage Files

📁 `manage-files/` — 7 tools

| Tool | Purpose |
|------|----------|
| [copy-items](manage-files/copy-items.md) | Copies files or folders to a destination folder. |
| [move-items](manage-files/move-items.md) | Moves files or folders to a destination folder. |
| [rename-item](manage-files/rename-item.md) | Renames files or folders in a document library. |
| [delete-items](manage-files/delete-items.md) | Deletes files or folders from a document library (recycle bin). |
| [create-folder](manage-files/create-folder.md) | Creates one or more folders in a document library, optionally with color. |
| [set-folder-color](manage-files/set-folder-color.md) | Sets or changes the color of one or more folders. |
| [add-shortcut](manage-files/add-shortcut.md) | Creates shortcuts to files or folders across source-to-destination pairs. |

### Search & Discovery

📁 `search-and-discovery/` — 4 tools

| Tool | Purpose |
|------|----------|
| [find-items](search-and-discovery/find-items.md) | Finds files by name, extension, or pattern. Like Unix find. |
| [list-items](search-and-discovery/list-items.md) | Lists, counts, or filters items in a list, library, or folder. |
| [search-content-tool](search-and-discovery/search-content-tool.md) | Searches the M365 tenant for content beyond SharePoint – emails, Teams, etc. |
| [discover-sharepoint-lists](search-and-discovery/discover-sharepoint-lists.md) | Discovers all lists and document libraries in a SharePoint site. |

### Lists & Libraries

📁 `lists-and-libraries/` — 4 tools

| Tool | Purpose |
|------|----------|
| [create-or-update-list](lists-and-libraries/create-or-update-list.md) | Creates a new SharePoint list/library or updates an existing one. |
| [delete-list](lists-and-libraries/delete-list.md) | Permanently deletes a SharePoint list or document library (recycle bin). |
| [get-list-schema](lists-and-libraries/get-list-schema.md) | Retrieves the complete schema of a list – fields, types, content types, item count. |
| [delete-field](lists-and-libraries/delete-field.md) | Permanently deletes columns from a SharePoint list. All data is lost. |

### List Items

📁 `list-items/` — 5 tools

| Tool | Purpose |
|------|----------|
| [create-list-items](list-items/create-list-items.md) | Creates new items in a SharePoint list with specified field values. |
| [update-list-items](list-items/update-list-items.md) | Updates existing items in a SharePoint list with new field values. |
| [update-batch-list-items](list-items/update-batch-list-items.md) | Updates multiple list items matching a CAML query in a single batch operation. |
| [delete-list-item](list-items/delete-list-item.md) | Deletes one or more items from a SharePoint list by item ID. |
| [list-item-versions](list-items/list-item-versions.md) | Lists all versions of a list item – editor, timestamp, size. |

### Views & Formatting

📁 `views-and-formatting/` — 6 tools

| Tool | Purpose |
|------|----------|
| [get-views-of-list](views-and-formatting/get-views-of-list.md) | Retrieves all views of a list or library. |
| [get-view-definition](views-and-formatting/get-view-definition.md) | Retrieves the complete definition of a view – CAML query, fields, sorting. |
| [preview-view-changes](views-and-formatting/preview-view-changes.md) | Previews how a list would look after applying view changes. |
| [delete-view](views-and-formatting/delete-view.md) | Permanently deletes one or more views from a SharePoint list. |
| [apply-column-formatting-v2](views-and-formatting/apply-column-formatting-v2.md) | Applies column-level formatting JSON to a list field – pills, icons, data bars. |
| [apply-view-formatting-v2](views-and-formatting/apply-view-formatting-v2.md) | Applies view-level formatting JSON to a list view. |

### Automation & Rules

📁 `automation-and-rules/` — 8 tools

| Tool | Purpose |
|------|----------|
| [create-or-update-rule-v2](automation-and-rules/create-or-update-rule-v2.md) | Creates or updates a SharePoint rule in a list or document library. |
| [get-rules](automation-and-rules/get-rules.md) | Retrieves all SharePoint rules defined for a list. |
| [delete-rule](automation-and-rules/delete-rule.md) | Deletes one or more rules from a SharePoint list. |
| [open-rules-management-panel-v2](automation-and-rules/open-rules-management-panel-v2.md) | Opens the rules management panel to view and manage rules. |
| [create-or-update-quick-step](automation-and-rules/create-or-update-quick-step.md) | Creates or updates a quick step (quick action) in a list. |
| [get-quicksteps](automation-and-rules/get-quicksteps.md) | Retrieves all quick steps and quick step columns of a list. |
| [delete-quickstep](automation-and-rules/delete-quickstep.md) | Deletes a quick step from a list or library. |
| [configure-quick-step-columns](automation-and-rules/configure-quick-step-columns.md) | Creates, updates, or deletes quick step columns in a list. |

### Approvals

📁 `approvals/` — 5 tools

| Tool | Purpose |
|------|----------|
| [configure-approvals-v2](approvals/configure-approvals-v2.md) | Configures modern approvals for a SharePoint list. |
| [get-approval-enabled-v2](approvals/get-approval-enabled-v2.md) | Checks whether approvals are enabled on a list. |
| [create-approval-request-v2](approvals/create-approval-request-v2.md) | Creates an approval request for a list item or document. |
| [get-approval-request](approvals/get-approval-request.md) | Gets approval request details for a specific list item. |
| [resolve-approval-request](approvals/resolve-approval-request.md) | Approves, rejects, or cancels an approval request. |

### Permissions & Sharing

📁 `permissions-and-sharing/` — 4 tools

| Tool | Purpose |
|------|----------|
| [check-permissions](permissions-and-sharing/check-permissions.md) | Checks whether specified users have access to items. |
| [share-file](permissions-and-sharing/share-file.md) | Shares a file by creating a sharing link and sending an email notification. |
| [unshare-file](permissions-and-sharing/unshare-file.md) | Removes a user's access to a file. |
| [get-sensitivity-labels](permissions-and-sharing/get-sensitivity-labels.md) | Retrieves available sensitivity labels configured for the organization. |

### Resolve Field Values

📁 `resolve-field-values/` — 6 tools

| Tool | Purpose |
|------|----------|
| [get-user-info](resolve-field-values/get-user-info.md) | Resolves person names or emails into SharePoint User field format. |
| [get-lookup-info](resolve-field-values/get-lookup-info.md) | Resolves lookup field values into correct SharePoint format. |
| [get-datetime-info](resolve-field-values/get-datetime-info.md) | Formats date/time values for SharePoint DateTime fields. |
| [get-taxonomy-info](resolve-field-values/get-taxonomy-info.md) | Resolves taxonomy terms for SharePoint managed metadata fields. |
| [get-term-sets](resolve-field-values/get-term-sets.md) | Retrieves the definition and hierarchy of SharePoint term sets. |
| [get-location-info](resolve-field-values/get-location-info.md) | Resolves location names or addresses into SharePoint Location field format. |

### Navigation & Context

📁 `navigation-and-context/` — 4 tools

| Tool | Purpose |
|------|----------|
| [navigate-to-url](navigation-and-context/navigate-to-url.md) | Navigates to a SharePoint list, library, or page. |
| [get-current-list-or-library](navigation-and-context/get-current-list-or-library.md) | Retrieves info about the current list or library the user is viewing. |
| [set-context-file](navigation-and-context/set-context-file.md) | Creates or updates the SHAREPOINT.md context file for the site. |
| [get-function-call-result](navigation-and-context/get-function-call-result.md) | Retrieves the full output of a previous function call by reference ID. |

### Skills & Agents

📁 `skills-and-agents/` — 2 tools

| Tool | Purpose |
|------|----------|
| [load-skill](skills-and-agents/load-skill.md) | Loads a skill from AgentAssets/Skills and makes it available. |
| [create-skill](skills-and-agents/create-skill.md) | Creates or updates a reusable skill file in the AgentAssets library. |

### OneDrive

📁 `onedrive/` — 3 tools

| Tool | Purpose |
|------|----------|
| [get-onedrive-details](onedrive/get-onedrive-details.md) | Retrieves the current user's OneDrive details (URL, IDs). |
| [get-onedrive-favorites](onedrive/get-onedrive-favorites.md) | Retrieves the user's favorited items from OneDrive and SharePoint. |
| [update-onedrive-favorite](onedrive/update-onedrive-favorite.md) | Adds or removes items from OneDrive favorites. |

### Recycle Bin & Restore

📁 `recycle-bin-and-restore/` — 4 tools

| Tool | Purpose |
|------|----------|
| [get-recycle-bin-contents](recycle-bin-and-restore/get-recycle-bin-contents.md) | Retrieves items from the recycle bin of a SharePoint site. |
| [restore-recycle-bin-items](recycle-bin-and-restore/restore-recycle-bin-items.md) | Restores files and folders from the recycle bin. |
| [get-restoreable-lists](recycle-bin-and-restore/get-restoreable-lists.md) | Retrieves deleted lists/libraries that can be restored. |
| [restore-list](recycle-bin-and-restore/restore-list.md) | Restores lists or libraries from the recycle bin. |

### Code & Visualization

📁 `code-and-visualization/` — 1 tools

| Tool | Purpose |
|------|----------|
| [execute-code](code-and-visualization/execute-code.md) | Executes sandboxed JavaScript – calculations, data transformation, Canvas images, HTML reports. |

### Users & Organization

📁 `users-and-organization/` — 1 tools

| Tool | Purpose |
|------|----------|
| [org-chart](users-and-organization/org-chart.md) | Retrieves org chart information from M365 organizational data. |

### Templates & Forms

📁 `templates-and-forms/` — 3 tools

| Tool | Purpose |
|------|----------|
| [template-finder](templates-and-forms/template-finder.md) | Finds matching templates – highest priority for template requests. |
| [create-form](templates-and-forms/create-form.md) | Creates a new form on a SharePoint list with fields, theme, and notifications. |
| [suggest-new-columns](templates-and-forms/suggest-new-columns.md) | Analyzes a library and suggests new columns. |

## Structure

```
en/
├── read-and-analyze/
│   ├── analyze-image.md
│   ├── cat-file.md
│   ├── compare-file-versions.md
│   ├── digest-file.md
│   ├── grep-contents.md
│   └── semantic-search.md
├── create-files/
│   ├── create-file.md
│   └── create-chart.md
├── manage-files/
│   ├── copy-items.md
│   ├── move-items.md
│   ├── rename-item.md
│   ├── delete-items.md
│   ├── create-folder.md
│   ├── set-folder-color.md
│   └── add-shortcut.md
├── search-and-discovery/
│   ├── find-items.md
│   ├── list-items.md
│   ├── search-content-tool.md
│   └── discover-sharepoint-lists.md
├── lists-and-libraries/
│   ├── create-or-update-list.md
│   ├── delete-list.md
│   ├── get-list-schema.md
│   └── delete-field.md
├── list-items/
│   ├── create-list-items.md
│   ├── update-list-items.md
│   ├── update-batch-list-items.md
│   ├── delete-list-item.md
│   └── list-item-versions.md
├── views-and-formatting/
│   ├── get-views-of-list.md
│   ├── get-view-definition.md
│   ├── preview-view-changes.md
│   ├── delete-view.md
│   ├── apply-column-formatting-v2.md
│   └── apply-view-formatting-v2.md
├── automation-and-rules/
│   ├── create-or-update-rule-v2.md
│   ├── get-rules.md
│   ├── delete-rule.md
│   ├── open-rules-management-panel-v2.md
│   ├── create-or-update-quick-step.md
│   ├── get-quicksteps.md
│   ├── delete-quickstep.md
│   └── configure-quick-step-columns.md
├── approvals/
│   ├── configure-approvals-v2.md
│   ├── get-approval-enabled-v2.md
│   ├── create-approval-request-v2.md
│   ├── get-approval-request.md
│   └── resolve-approval-request.md
├── permissions-and-sharing/
│   ├── check-permissions.md
│   ├── share-file.md
│   ├── unshare-file.md
│   └── get-sensitivity-labels.md
├── resolve-field-values/
│   ├── get-user-info.md
│   ├── get-lookup-info.md
│   ├── get-datetime-info.md
│   ├── get-taxonomy-info.md
│   ├── get-term-sets.md
│   └── get-location-info.md
├── navigation-and-context/
│   ├── navigate-to-url.md
│   ├── get-current-list-or-library.md
│   ├── set-context-file.md
│   └── get-function-call-result.md
├── skills-and-agents/
│   ├── load-skill.md
│   └── create-skill.md
├── onedrive/
│   ├── get-onedrive-details.md
│   ├── get-onedrive-favorites.md
│   └── update-onedrive-favorite.md
├── recycle-bin-and-restore/
│   ├── get-recycle-bin-contents.md
│   ├── restore-recycle-bin-items.md
│   ├── get-restoreable-lists.md
│   └── restore-list.md
├── code-and-visualization/
│   └── execute-code.md
├── users-and-organization/
│   └── org-chart.md
├── templates-and-forms/
│   ├── template-finder.md
│   ├── create-form.md
│   └── suggest-new-columns.md
└── README.md
```

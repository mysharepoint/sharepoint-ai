---
title: "create_list_items"
category: "List Items"
kategorie: "Listeneinträge"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "fieldInternalNames[], values[], listUrl"
prerequisite: "get_list_schema, ggf. get_user_info/get_lookup_info/get_datetime_info"
tags: ["Eintrag", "erstellen", "hinzufügen", "Liste", "item", "create", "add", "list"]
---

# create_list_items

## Purpose (EN)

Creates new items in a SharePoint list with specified field values.

## Zweck (DE)

Erstellt neue Einträge in einer SharePoint-Liste mit definierten Feldwerten.

## Use Case (EN)

Add new text blocks, quotes, or entries to lists.

## Anwendung (DE)

Neue Textbausteine, Zitate oder Einträge in Listen einfügen.

## Example (EN)

> Add a new text block with title 'Grid Expansion' and status 'Draft'.

## Beispiel (DE)

> Füge einen neuen Textbaustein mit Titel 'Netzausbau' und Status 'Entwurf' hinzu.

## Prompt Template (EN)

> Create a new item in [list] with [field=value].

## Prompt-Vorlage (DE)

> Erstelle einen neuen Eintrag in [Liste] mit [Feld=Wert].

## Key Parameters

`fieldInternalNames[], values[], listUrl`

## Prerequisite

get_list_schema, ggf. get_user_info/get_lookup_info/get_datetime_info

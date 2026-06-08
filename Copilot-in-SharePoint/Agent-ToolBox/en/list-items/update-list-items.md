---
title: "update_list_items"
category: "List Items"
kategorie: "Listeneinträge"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "Item-IDs, fieldInternalNames[], values[]"
prerequisite: "get_list_schema (InternalName), ggf. Lookup-/User-Auflösung"
tags: ["aktualisieren", "ändern", "Eintrag", "update", "edit", "item", "modify"]
---

# update_list_items

## Purpose (EN)

Updates existing items in a SharePoint list with new field values.

## Zweck (DE)

Aktualisiert bestehende Einträge in einer SharePoint-Liste.

## Use Case (EN)

Edit individual items – e.g. change status from Draft to Approved.

## Anwendung (DE)

Einzelne Einträge bearbeiten – z.B. Status von Entwurf auf Genehmigt ändern.

## Example (EN)

> Set the status of item 5 to Approved.

## Beispiel (DE)

> Setze den Status von Eintrag 5 auf Genehmigt.

## Prompt Template (EN)

> Change [field] of item [ID] in [list] to [value].

## Prompt-Vorlage (DE)

> Ändere [Feld] von Eintrag [ID] in [Liste] auf [Wert].

## Key Parameters

`Item-IDs, fieldInternalNames[], values[]`

## Prerequisite

get_list_schema (InternalName), ggf. Lookup-/User-Auflösung

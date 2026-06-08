---
title: "update_batch_list_items"
category: "List Items"
kategorie: "Listeneinträge"
complexity: "Advanced"
output_type: "Confirmation"
key_parameters: "Liste, CAML-Query, neue Feldwerte"
prerequisite: "get_list_schema"
tags: ["Batch", "Masse", "aktualisieren", "CAML", "bulk", "update", "batch"]
---

# update_batch_list_items

## Purpose (EN)

Updates multiple list items matching a CAML query in a single batch operation.

## Zweck (DE)

Aktualisiert mehrere Listeneinträge per CAML-Query in einem Batch-Vorgang.

## Use Case (EN)

Bulk updates – e.g. set all entries of a topic to Archived.

## Anwendung (DE)

Massenaktualisierungen – z.B. alle Einträge eines Themenfelds auf Archiviert setzen.

## Example (EN)

> Set all entries with topic Offshore to status Archived.

## Beispiel (DE)

> Setze alle Einträge mit Themenfeld Offshore auf Status Archiviert.

## Prompt Template (EN)

> Change all items in [list] where [condition] to [field=value].

## Prompt-Vorlage (DE)

> Ändere alle Einträge in [Liste] wo [Bedingung] auf [Feld=Wert].

## Key Parameters

`Liste, CAML-Query, neue Feldwerte`

## Prerequisite

get_list_schema

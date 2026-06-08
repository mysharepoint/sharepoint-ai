---
title: "delete_field"
category: "Lists & Libraries"
kategorie: "Listen & Bibliotheken"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "Liste, Feldname(n)"
prerequisite: "get_list_schema (InternalName ermitteln)"
tags: ["Spalte", "löschen", "Feld", "entfernen", "column", "delete", "field", "remove"]
---

# delete_field

## Purpose (EN)

Permanently deletes columns from a SharePoint list. All data is lost.

## Zweck (DE)

Löscht Spalten dauerhaft aus einer SharePoint-Liste. Alle Daten gehen verloren.

## Use Case (EN)

Remove unused columns to clean up lists.

## Anwendung (DE)

Nicht mehr benötigte Spalten entfernen, um Listen aufzuräumen.

## Example (EN)

> Delete the column Old_Category from the list.

## Beispiel (DE)

> Lösche die Spalte Alte_Kategorie aus der Liste.

## Prompt Template (EN)

> Delete the column [column name] from [list].

## Prompt-Vorlage (DE)

> Lösche die Spalte [Spaltenname] aus [Liste].

## Key Parameters

`Liste, Feldname(n)`

## Prerequisite

get_list_schema (InternalName ermitteln)

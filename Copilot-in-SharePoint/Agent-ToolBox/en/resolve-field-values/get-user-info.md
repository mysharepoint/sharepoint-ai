---
title: "get_user_info"
category: "Resolve Field Values"
kategorie: "Feldwerte auflösen"
complexity: "Simple"
output_type: "Data"
key_parameters: "userName oder E-Mail"
prerequisite: "Keine – MUSS vor create_list_items/update_list_items mit User-Feldern laufen"
tags: ["Benutzer", "Person", "auflösen", "User", "resolve", "person", "lookup"]
---

# get_user_info

## Purpose (EN)

Resolves person names or emails into SharePoint User field format.

## Zweck (DE)

Löst Personennamen oder E-Mail-Adressen in das SharePoint-User-Format auf.

## Use Case (EN)

Get correct user values before creating items with person columns.

## Anwendung (DE)

Korrekte Benutzerwerte ermitteln, bevor Einträge mit Personen-Spalten erstellt werden.

## Example (EN)

> Resolve the name Emma Collins for a user field.

## Beispiel (DE)

> Löse den Namen Emma Collins für ein User-Feld auf.

## Prompt Template (EN)

> Resolve [name/email] for a user field.

## Prompt-Vorlage (DE)

> Löse [Name/E-Mail] für ein User-Feld auf.

## Key Parameters

`userName oder E-Mail`

## Prerequisite

Keine – MUSS vor create_list_items/update_list_items mit User-Feldern laufen

---
title: "get_view_definition"
category: "Views & Formatting"
kategorie: "Ansichten & Formatierung"
complexity: "Medium"
output_type: "Schema"
key_parameters: "Liste, Ansichts-ID(s)"
prerequisite: "get_views_of_list (liefert IDs)"
tags: ["Ansicht", "Definition", "CAML", "Felder", "view", "definition", "query"]
---

# get_view_definition

## Purpose (EN)

Retrieves the complete definition of a view – CAML query, fields, sorting.

## Zweck (DE)

Ruft die vollständige Definition einer Ansicht ab – CAML-Query, Felder, Sortierung.

## Use Case (EN)

Analyze existing views to modify or build new ones on top.

## Anwendung (DE)

Bestehende Ansichten analysieren, um sie zu ändern oder neue darauf aufzubauen.

## Example (EN)

> Show me the definition of the default view of the BWEC-TB-QUOTE list.

## Beispiel (DE)

> Zeige mir die Definition der Standardansicht der BWEC-TB-QUOTE-Liste.

## Prompt Template (EN)

> Show the definition of the view [view name] in [list].

## Prompt-Vorlage (DE)

> Zeige die Definition der Ansicht [Ansichtsname] in [Liste].

## Key Parameters

`Liste, Ansichts-ID(s)`

## Prerequisite

get_views_of_list (liefert IDs)

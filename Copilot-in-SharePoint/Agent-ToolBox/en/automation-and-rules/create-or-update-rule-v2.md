---
title: "create_or_update_rule_v2"
category: "Automation & Rules"
kategorie: "Automatisierung & Regeln"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "Liste, Bedingungen, Aktionen"
prerequisite: "get_list_schema"
tags: ["Regel", "Automatisierung", "Benachrichtigung", "rule", "automation", "notification"]
---

# create_or_update_rule_v2

## Purpose (EN)

Creates or updates a SharePoint rule in a list or document library.

## Zweck (DE)

Erstellt oder aktualisiert eine SharePoint-Regel in einer Liste oder Bibliothek.

## Use Case (EN)

Set up automatic notifications or actions.

## Anwendung (DE)

Automatische Benachrichtigungen oder Aktionen einrichten.

## Example (EN)

> Create a rule: send me an email when a new item with status Draft is created.

## Beispiel (DE)

> Erstelle eine Regel: Sende mir eine E-Mail wenn ein neuer Eintrag mit Status Entwurf erstellt wird.

## Prompt Template (EN)

> Create a rule in [list]: When [condition] then [action].

## Prompt-Vorlage (DE)

> Erstelle eine Regel in [Liste]: Wenn [Bedingung] dann [Aktion].

## Key Parameters

`Liste, Bedingungen, Aktionen`

## Prerequisite

get_list_schema

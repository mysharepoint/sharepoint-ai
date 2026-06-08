---
title: "create_or_update_quick_step"
category: "Automation & Rules"
kategorie: "Automatisierung & Regeln"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "Liste, Quick-Step-Definition"
prerequisite: "get_list_schema"
tags: ["Quick Step", "Schnellaktion", "Automatisierung", "quick step", "action", "shortcut"]
---

# create_or_update_quick_step

## Purpose (EN)

Creates or updates a quick step (quick action) in a list.

## Zweck (DE)

Erstellt oder aktualisiert einen Quick Step (Schnellaktion) in einer Liste.

## Use Case (EN)

Define quick actions – e.g. set status to Approved with one click.

## Anwendung (DE)

Schnellaktionen definieren – z.B. Status auf Genehmigt setzen per Knopfdruck.

## Example (EN)

> Create a quick step Approve that sets status to Approved.

## Beispiel (DE)

> Erstelle einen Quick Step Freigeben der den Status auf Genehmigt setzt.

## Prompt Template (EN)

> Create a quick step [name] in [list] that performs [action].

## Prompt-Vorlage (DE)

> Erstelle einen Quick Step [Name] in [Liste] der [Aktion] ausführt.

## Key Parameters

`Liste, Quick-Step-Definition`

## Prerequisite

get_list_schema

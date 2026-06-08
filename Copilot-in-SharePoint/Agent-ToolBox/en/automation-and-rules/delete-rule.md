---
title: "delete_rule"
category: "Automation & Rules"
kategorie: "Automatisierung & Regeln"
complexity: "Simple"
output_type: "Confirmation"
key_parameters: "Liste, Regel-ID(s)"
prerequisite: "get_rules (liefert IDs)"
tags: ["Regel", "löschen", "entfernen", "rule", "delete", "remove"]
---

# delete_rule

## Purpose (EN)

Deletes one or more rules from a SharePoint list.

## Zweck (DE)

Löscht eine oder mehrere Regeln aus einer SharePoint-Liste.

## Use Case (EN)

Remove automation rules that are no longer needed.

## Anwendung (DE)

Nicht mehr benötigte Automatisierungsregeln entfernen.

## Example (EN)

> Delete the rule Notification on new draft.

## Beispiel (DE)

> Lösche die Regel Benachrichtigung bei neuem Entwurf.

## Prompt Template (EN)

> Delete the rule [rule name/ID] from [list].

## Prompt-Vorlage (DE)

> Lösche die Regel [Regelname/ID] aus [Liste].

## Key Parameters

`Liste, Regel-ID(s)`

## Prerequisite

get_rules (liefert IDs)

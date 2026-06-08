---
title: "create_approval_request_v2"
category: "Approvals"
kategorie: "Genehmigungen"
complexity: "Medium"
output_type: "Confirmation"
key_parameters: "Element, Genehmiger"
prerequisite: "configure_approvals_v2 (muss aktiviert sein)"
tags: ["Genehmigung", "Anfrage", "starten", "approval", "request", "submit"]
---

# create_approval_request_v2

## Purpose (EN)

Creates an approval request for a list item or document.

## Zweck (DE)

Erstellt eine Genehmigungsanfrage für ein Listenelement oder Dokument.

## Use Case (EN)

Start a specific approval process for a particular item.

## Anwendung (DE)

Einen konkreten Freigabeprozess für ein bestimmtes Element starten.

## Example (EN)

> Create an approval request for item 15 with James Whitmore as approver.

## Beispiel (DE)

> Erstelle eine Genehmigungsanfrage für Eintrag 15 mit James Whitmore als Genehmiger.

## Prompt Template (EN)

> Create an approval request for [item] with [approver].

## Prompt-Vorlage (DE)

> Erstelle eine Genehmigungsanfrage für [Element] mit [Genehmiger].

## Key Parameters

`Element, Genehmiger`

## Prerequisite

configure_approvals_v2 (muss aktiviert sein)

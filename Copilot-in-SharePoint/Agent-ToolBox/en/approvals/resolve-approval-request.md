---
title: "resolve_approval_request"
category: "Approvals"
kategorie: "Genehmigungen"
complexity: "Simple"
output_type: "Confirmation"
key_parameters: "Anfrage-ID, Aktion (approve/reject/cancel)"
prerequisite: "get_approval_request (liefert Anfrage-ID)"
tags: ["Genehmigung", "genehmigen", "ablehnen", "approval", "approve", "reject", "cancel"]
---

# resolve_approval_request

## Purpose (EN)

Approves, rejects, or cancels an approval request.

## Zweck (DE)

Genehmigt, lehnt ab oder storniert eine Genehmigungsanfrage.

## Use Case (EN)

Complete pending approval processes.

## Anwendung (DE)

Laufende Genehmigungsprozesse abschließen.

## Example (EN)

> Approve the request for item 15.

## Beispiel (DE)

> Genehmige die Anfrage für Eintrag 15.

## Prompt Template (EN)

> [Approve/Reject/Cancel] the request for [item].

## Prompt-Vorlage (DE)

> [Genehmige/Lehne ab/Storniere] die Anfrage für [Element].

## Key Parameters

`Anfrage-ID, Aktion (approve/reject/cancel)`

## Prerequisite

get_approval_request (liefert Anfrage-ID)

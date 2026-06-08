---
title: "grep_contents"
category: "Read & Analyze"
kategorie: "Dateien lesen & analysieren"
complexity: "Medium"
output_type: "Data"
key_parameters: "Dateiliste (aus find_items), Suchbegriff/Regex"
prerequisite: "find_items (liefert die Dateiliste)"
tags: ["suchen", "grep", "Regex", "Text", "Treffer", "search", "match", "pattern"]
---

# grep_contents

## Purpose (EN)

Searches files for exact text or regex; returns matched lines with context.

## Zweck (DE)

Durchsucht Dateien nach exaktem Text oder Regex. Gibt Trefferzeilen mit Kontext zurück.

## Use Case (EN)

Search for specific terms in documents – e.g. all mentions of 'grid expansion'.

## Anwendung (DE)

Gezielt nach Begriffen in Dokumenten suchen – z.B. alle Erwähnungen von 'Netzausbau'.

## Example (EN)

> Search all briefing documents for the term 'supply chain'.

## Beispiel (DE)

> Suche in allen Briefing-Dokumenten nach dem Begriff 'Lieferkette'.

## Prompt Template (EN)

> Search [files] for the term [search term].

## Prompt-Vorlage (DE)

> Suche in [Dateien] nach dem Begriff [Suchbegriff].

## Key Parameters

`Dateiliste (aus find_items), Suchbegriff/Regex`

## Prerequisite

find_items (liefert die Dateiliste)

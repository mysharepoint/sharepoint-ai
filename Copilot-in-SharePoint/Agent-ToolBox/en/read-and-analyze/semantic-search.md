---
title: "semantic_search"
category: "Read & Analyze"
kategorie: "Dateien lesen & analysieren"
complexity: "Medium"
output_type: "Data"
key_parameters: "Dateiliste (aus find_items), thematische Suchanfrage"
prerequisite: "find_items (liefert die Dateiliste)"
tags: ["semantisch", "Thema", "Konzept", "Passage", "semantic", "topic", "meaning"]
---

# semantic_search

## Purpose (EN)

Searches files by topic or concept (semantic). Returns matched passages with context.

## Zweck (DE)

Durchsucht Dateien nach Themen oder Konzepten (semantisch). Gibt passende Passagen zurück.

## Use Case (EN)

Find topically relevant passages in documents – e.g. all passages about 'supply chains'.

## Anwendung (DE)

Inhaltlich relevante Stellen in Dokumenten finden – z.B. alle Passagen zum Thema 'Lieferketten'.

## Example (EN)

> Find all passages about energy policy in the reference files.

## Beispiel (DE)

> Finde in den Referenzdateien alle Passagen zum Thema Energiepolitik.

## Prompt Template (EN)

> Find in [files] all passages about [topic].

## Prompt-Vorlage (DE)

> Finde in [Dateien] alle Stellen zum Thema [Thema].

## Key Parameters

`Dateiliste (aus find_items), thematische Suchanfrage`

## Prerequisite

find_items (liefert die Dateiliste)

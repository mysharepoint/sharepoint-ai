---
title: "cat_file"
category: "Read & Analyze"
kategorie: "Dateien lesen & analysieren"
complexity: "Simple"
output_type: "Data"
key_parameters: "serverRelativeUrl, spItemUrl, files[] (Batch), returnContent"
prerequisite: "Keine zwingend; find_items liefert Dateipfade"
tags: ["lesen", "Datei", "PDF", "Word", "Excel", "extrahieren", "read", "content", "extract"]
---

# cat_file

## Purpose (EN)

Reads file content. Text files directly, Office docs and PDFs are extracted automatically.

## Zweck (DE)

Liest den Inhalt einer oder mehrerer Dateien. Textdateien direkt, Office-Dokumente und PDFs werden extrahiert.

## Use Case (EN)

Read file contents to answer questions or process text further.

## Anwendung (DE)

Dateiinhalte lesen, um Fragen zu beantworten oder Texte weiterzuverarbeiten.

## Example (EN)

> Read council-profile-bwec.md and summarize the content.

## Beispiel (DE)

> Lies die Datei council-profile-bwec.md und fasse den Inhalt zusammen.

## Prompt Template (EN)

> Read the file [filename] in [library] and [summarize / show content].

## Prompt-Vorlage (DE)

> Lies die Datei [Dateiname] in [Bibliothek] und [fasse zusammen / zeige den Inhalt].

## Key Parameters

`serverRelativeUrl, spItemUrl, files[] (Batch), returnContent`

## Prerequisite

Keine zwingend; find_items liefert Dateipfade

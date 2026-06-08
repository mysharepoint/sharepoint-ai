---
title: "create_file"
category: "Create Files"
kategorie: "Dateien erstellen"
complexity: "Medium"
output_type: "File"
key_parameters: "fileName, fileContent, slides[], sheets[], images[], listUrl, theme, files[] (Batch)"
prerequisite: "Für Bilder: list_items/find_items liefert spItemUrl. Für Daten: execute_code mit outputDataRef."
tags: ["erstellen", "Datei", "Word", "PowerPoint", "Excel", "PDF", "Präsentation", "create", "file", "document"]
---

# create_file

## Purpose (EN)

Creates new files: text, PDF, Word (.docx), PowerPoint (.pptx), Excel (.xlsx).

## Zweck (DE)

Erstellt neue Dateien: Text, PDF, Word (.docx), PowerPoint (.pptx), Excel (.xlsx).

## Use Case (EN)

Turn content or research into a file – statement as Word, overview as slides, data as Excel.

## Anwendung (DE)

Aus Inhalten oder Recherche eine Datei erzeugen – Statement als Word, Übersicht als Präsentation, Daten als Excel.

## Example (EN)

> Create a PowerPoint about the asparagus dish with image and recipe in the Workshop library.

## Beispiel (DE)

> Erstelle eine PowerPoint über das Spargelgericht mit Bild und Rezept in der Workshop-Bibliothek.

## Prompt Template (EN)

> Create a [format] file named [name] in [library] with [content/task].

## Prompt-Vorlage (DE)

> Erstelle eine [Format]-Datei namens [Name] in [Bibliothek] mit [Inhalt/Auftrag].

## Key Parameters

`fileName, fileContent, slides[], sheets[], images[], listUrl, theme, files[] (Batch)`

## Prerequisite

Für Bilder: list_items/find_items liefert spItemUrl. Für Daten: execute_code mit outputDataRef.

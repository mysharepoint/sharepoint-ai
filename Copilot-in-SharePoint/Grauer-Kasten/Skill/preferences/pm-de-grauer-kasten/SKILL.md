---
name: pm-de-grauer-kasten
description: |
  Legt das visuelle Design einer Microsoft-Source-Pressemitteilung über bereits
  erstellte Ausgabetexte. Nutzt das Microsoft-Logo aus `assets/MS LOGO.png`,
  erzeugt immer eine HTML- und eine PDF-Ausgabe und speichert beide Dateien im
  Ordner `/sites/CopilotCenter/MSGrauerKasten/output`.
cowork:
  category: writing
  icon: TextboxAlignMiddle
---

# pm-de-grauer-kasten — Microsoft-Source-Pressemitteilungs-Design

## Zweck

Dieser Skill ist eine reine **Gestaltungsschicht**. Er erfindet keine Inhalte.
Copilot erzeugt zuerst den Ausgabetext der deutschen Pressemitteilung, und
anschließend legt dieser Skill das definierte Microsoft-Source-EMEA-Layout
über den Inhalt: große, dünne Headline, schmale Textspalte, **grauer Kasten**
mit fett eingeleiteten Bulletpoints, blaue Quell-Links und das Microsoft-Logo
am oberen Rand.

## Verwendete Dateien und Assets

- Gestaltungsvorgabe: `preferences/pm-de-grauer-kasten/SKILL.md`
- Logo: `assets/MS LOGO.png`
- Ausgabeziel: `/sites/CopilotCenter/MSGrauerKasten/output`

## Wann verwenden

- Wenn der Hauptskill `grauer-kasten` nach der Inhaltserstellung automatisch das
  PM-Design anwenden soll.
- Wenn eine deutsche Microsoft-Pressemitteilung im definierten grauen-Kasten-
  Stil ausgegeben werden soll.

## Wann NICHT verwenden

- Nicht für Recherche oder Übersetzung selbst; das macht der Hauptskill.
- Nicht für allgemeine HTML-Berichte ohne dieses Layout.
- Nicht für Einzeldateien ohne HTML- und PDF-Ausgabe.

## Erwartete Eingabe

Vor Anwendung des Layouts müssen diese Inhaltsbausteine vorliegen:

1. **Titel**
2. **Thematischer Untertitel**
3. **Einleitungsabsatz**
4. **Lead-in-Zeile** für die Liste
5. **3 bis 6 Bullet-Punkte** mit fetter Lead-in-Phrase
6. **Quellverweis** mit Titel und URL des Originalartikels

## Verbindlicher Workflow

1. Übernimm den bereits erzeugten PM-Inhalt unverändert in seiner Aussage.
2. Wende das definierte Layout auf diesen Inhalt an.
3. Binde `assets/MS LOGO.png` oberhalb der Überschrift als Logo ein.
4. Erzeuge eine eigenständige **HTML-Datei**.
5. Erzeuge zusätzlich aus derselben gestalteten Ausgabe eine **PDF-Datei**.
6. Speichere **beide Dateien** im Ordner `/sites/CopilotCenter/MSGrauerKasten/output`.
7. Melde erst Erfolg, wenn beide Dateien erzeugt wurden.

## Design-Spezifikation

- **Schrift:** `"Segoe UI", system-ui, -apple-system, "Helvetica Neue", Arial`
- **Headline:** Gewicht 300, groß, linksbündig, Farbe `#242424`
- **Textspalte:** schmal, max. 660px, zentriert
- **Grauer Kasten:** Hintergrund `#f2f2f2`, ohne harte Umrandung
- **Bullets:** fetter Lead-in, danach normaler Erklärungstext
- **Links:** Microsoft-Blau `#0067b8`, unterstrichen
- **Logo:** Microsoft-Logo oben vor dem Inhalt sichtbar einbinden

## Guardrails

- Keine Inhalte ergänzen oder umschreiben, die nicht aus dem Hauptskill kommen
- Kein anderes Design verwenden
- Das Logo muss aus `assets/MS LOGO.png` referenziert werden
- Ausgabe immer als **HTML und PDF**
- Ablage immer in `/sites/CopilotCenter/MSGrauerKasten/output`
- Wenn die PDF-Erzeugung fehlschlägt, HTML trotzdem erzeugen und den Fehler offen benennen

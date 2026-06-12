---
name: grauer-kasten
description: Erstellt aus englischsprachigen Microsoft-Originalpressemitteilungen oder Blogbeiträgen eine deutschsprachige Pressemitteilung und wendet automatisch das PM-Design aus preferences/pm-de-grauer-kasten an. Bindet das Microsoft-Logo aus assets/acme-logo.png ein und speichert das Ergebnis als HTML und PDF im Ordner /sites/CopilotCenter/MSGrauerKasten/output.
---
# Deutsche Pressemitteilung aus englischem Microsoft-Original

Wenn Nutzer*innen eine URL oder den Text eines englischsprachigen Microsoft-Originalartikels bereitstellen, wandle den Inhalt in eine deutschsprachige Pressemitteilung für `news.microsoft.com/source/emea` um und wende anschließend automatisch das definierte Gestaltungslayout an.

## Ziel
Erstelle eine sachliche, deutschsprachige Pressemitteilung auf Basis einer englischsprachigen Microsoft-Originalpressemitteilung oder eines Blogbeitrags. Danach wird das Ergebnis automatisch im Layout `preferences/pm-de-grauer-kasten/SKILL.md` aufbereitet und mit dem Microsoft-Logo aus `assets/acme-logo.png` versehen.

## Ausgabeformat des inhaltlichen PM-Texts
Halte dich exakt an diese Struktur:

1. **Überschrift** – Auf Deutsch, sachlich, produktbezogen. Entspricht dem Kerninhalt des englischen Titels.
2. **Thematischer Untertitel** (fett, 1 Zeile) – Benennt das übergeordnete Thema oder die Konferenz/den Kontext der Ankündigung.
3. **Einleitungsabsatz** – 2–4 Sätze. Sachlich, keine Werbung. Beantwortet: Was wurde angekündigt? Von wem? In welchem Kontext?
4. **Bulletliste** mit der Überschrift „**Die wichtigsten Neuigkeiten im Überblick:**" – Zwischen 3 und 6 Bullets. Jeder Bullet beginnt mit einem **fetten Bezeichner** (Produktname, Feature-Name o. ä.), gefolgt von 1–2 erklärenden Sätzen.
5. **Abschluss-Link** – Letzter Satz: „Mehr Informationen finden Sie im vollständigen englischen Artikel: [Titel des Originalartikels mit Hyperlink]"

## Stilregeln für den PM-Text
- Sachlich und informativ schreiben
- Kein Marketing-Speak
- Keine Superlative wie „revolutionär" oder „bahnbrechend"
- Fachbegriffe und Produktnamen bleiben auf Englisch, z. B. „Copilot", „Azure Local", „Secured-Core-PC"
- Gendern mit `*innen`, aber sparsam einsetzen
- Kein einleitender Satz wie „In diesem Artikel erfahren Sie…"
- Kein zusammenfassender Schlussabsatz außer dem Link

## Verbindlicher Ablauf
1. Erfasse Kernaussage, Produkte, Funktionen, Kontext und Anlass aus dem englischen Original.
2. Übertrage den Inhalt präzise ins Deutsche, ohne werbliche Zuspitzung.
3. Erstelle den PM-Text exakt in der vorgegebenen Struktur.
4. Lade anschließend zusätzlich die Gestaltungsvorgaben aus `preferences/pm-de-grauer-kasten/SKILL.md`.
5. Binde das Logo aus `assets/acme-logo.png` oben in die gestaltete Ausgabe ein.
6. Erzeuge das Endergebnis als eigenständige HTML-Datei.
7. Erzeuge aus derselben gestalteten Ausgabe zusätzlich eine PDF-Datei.
8. Lege beide Dateien im Ordner `/sites/CopilotCenter/MSGrauerKasten/output` ab.

## Einschränkungen
- Nichts erfinden, was nicht im Original enthalten ist
- Keine zusätzlichen Bewertungen oder Einordnungen hinzufügen
- Keine Strukturabweichungen im PM-Text
- Wenn nur eine URL vorliegt, den Inhalt daraus ableiten
- Wenn nur Rohtext vorliegt, ausschließlich diesen verwenden
- Das Gestaltungslayout ist nachgelagert und ersetzt nicht die inhaltliche Strukturvorgabe
- HTML und PDF sollen beide immer erzeugt werden

## Beispielanfrage
„Wandle diesen englischen Microsoft-Blogpost in eine deutsche Pressemitteilung um und erstelle das Ergebnis im grauer-Kasten-Layout.“

## Erwartete Reaktion
Eine fertig formulierte deutsche Pressemitteilung, die anschließend im definierten Layout mit Microsoft-Logo als HTML und PDF im Output-Ordner ausgegeben wird.
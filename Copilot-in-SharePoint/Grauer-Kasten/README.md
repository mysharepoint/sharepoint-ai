# Grauer-Kasten-Skill

## Zweck
Der Skill `grauer-kasten` erzeugt aus einer englischsprachigen Microsoft-Originalmeldung eine deutschsprachige Pressemitteilung und wendet danach automatisch ein definiertes visuelles Layout an. Das Ergebnis wird als HTML und zusätzlich als PDF ausgegeben.

## Ausgangspunkt und Hintergedanke
Die Lösung trennt bewusst **Inhalt** und **Gestaltung**:

1. **Inhaltsebene**: Aus einer amerikanischen bzw. englischsprachigen Microsoft-Originalnews wird eine sachliche deutsche Pressemitteilung erzeugt.
2. **Gestaltungsebene**: Danach wird dieser fertige Inhalt in das definierte `grauer-kasten`-Design überführt.

Der Vorteil dieser Trennung:
- die Übersetzung bzw. inhaltliche Übertragung bleibt kontrollierbar,
- das Layout kann separat gepflegt werden,
- dieselbe Designlogik kann später auch auf andere PM-Texte angewendet werden.

## Aufbau des Skills
Die aktuelle Struktur in SharePoint ist:

```text
Skills/
└─ grauer-kasten/
   ├─ SKILL.md
   ├─ assets/
   │  └─ MS LOGO.png
   └─ preferences/
      └─ pm-de-grauer-kasten/
         └─ SKILL.md
```

## Rolle der einzelnen Bestandteile
### 1. `grauer-kasten/SKILL.md`
Das ist der Hauptskill.

Er definiert:
- den fachlichen Zweck,
- die Struktur der deutschen Pressemitteilung,
- die Stilregeln,
- den verpflichtenden Ablauf,
- die nachgelagerte Anwendung des Design-Skills.

Der Hauptskill sorgt also dafür, dass aus dem englischen Original ein sauber strukturierter deutscher PM-Text wird.

### 2. `grauer-kasten/preferences/pm-de-grauer-kasten/SKILL.md`
Das ist die Gestaltungsschicht.

Sie definiert:
- Typografie,
- Breite der Textspalte,
- den grauen Kasten,
- Linkfarbe,
- Position des Logos,
- die Pflicht, HTML und PDF zu erzeugen.

Diese Datei verändert nicht die Aussage des Inhalts, sondern nur dessen visuelle Umsetzung.

### 3. `grauer-kasten/assets/MS LOGO.png`
Dieses Asset enthält das Microsoft-Logo.

Es wird oberhalb der Überschrift eingebunden und bewusst separat gehalten, damit:
- das Logo austauschbar bleibt,
- Branding nicht hart im HTML verankert werden muss,
- spätere Varianten mit anderem Logo oder anderer Marke leichter möglich sind.

## Inhaltliche Umsetzung
Der Hauptskill verlangt für die deutsche Pressemitteilung exakt diese Struktur:

1. Überschrift
2. Thematischer Untertitel
3. Einleitungsabsatz
4. Bulletliste mit „Die wichtigsten Neuigkeiten im Überblick:“
5. Abschluss-Link zum englischen Original

Zusätzlich gelten inhaltliche Regeln:
- sachlich statt werblich,
- keine erfundenen Inhalte,
- keine Übertreibungen,
- Produktnamen und Fachbegriffe bleiben auf Englisch,
- kein freier Schlussabsatz außerhalb des Quellenlinks.

## Design-Umsetzung
Nach der inhaltlichen Erstellung greift der Design-Skill.

Er beschreibt den Zielstil so:
- Schrift: `Segoe UI`, systemnahe Sans-Serif-Fallbacks
- Headline: groß, dünn, linksbündig, dunkelgrau
- Textspalte: schmal, max. 660 px, zentriert
- grauer Kasten: Hintergrund `#f2f2f2`
- Bullets: mit fettem Lead-in
- Links: Microsoft-Blau `#0067b8`, unterstrichen
- Logo: oben sichtbar eingebunden

## Warum die amerikanische Originalnews zuerst kommt
Der Ausgangspunkt ist bewusst die englischsprachige Originalmeldung von Microsoft.

Der Gedanke dahinter:
- Das Original ist die primäre Quelle.
- Die deutsche Fassung soll keine freie Nacherzählung sein.
- Die deutsche Version bleibt inhaltlich nah am Original, wird aber in eine für Pressemitteilungen passende Struktur gebracht.
- Erst danach wird das gewünschte deutsche Erscheinungsbild aufgesetzt.

Kurz gesagt: **erst Quelle verstehen, dann sauber übertragen, dann gestalten**.

## Technischer Ablauf bei der Nutzung
1. Nutzer liefert URL oder Rohtext einer englischsprachigen Microsoft-Originalmeldung.
2. Der Hauptskill analysiert Kernaussage, Produkte, Funktionen, Anlass und Kontext.
3. Daraus wird eine deutsche Pressemitteilung in der vorgegebenen Struktur erzeugt.
4. Danach wird automatisch `preferences/pm-de-grauer-kasten/SKILL.md` als Designvorgabe angewendet.
5. Das Microsoft-Logo aus `assets/MS LOGO.png` wird eingebunden.
6. Aus derselben gestalteten Basis wird eine HTML-Datei erzeugt.
7. Zusätzlich wird eine PDF-Datei erzeugt.
8. Beide Dateien werden im Zielordner `/sites/CopilotCenter/MSGrauerKasten/output` gespeichert.

## Installationsanleitung
### Variante A: Auf derselben Site nachbauen
1. Öffne die Dokumentbibliothek `AgentAssets` und dort den Ordner `Skills`.
2. Lege einen Ordner `grauer-kasten` an.
3. Lege darin die Datei `SKILL.md` für den Hauptskill an.
4. Lege den Unterordner `preferences` an.
5. Lege darunter den Ordner `pm-de-grauer-kasten` an.
6. Lege dort eine zweite `SKILL.md` mit den Designregeln an.
7. Lege zusätzlich den Unterordner `assets` an.
8. Lade in `assets` die Datei `MS LOGO.png` hoch.
9. Stelle sicher, dass im Hauptskill auf diese beiden Bestandteile verwiesen wird:
   - `preferences/pm-de-grauer-kasten/SKILL.md`
   - `assets/MS LOGO.png`
10. Stelle sicher, dass als Ausgabeziel `/sites/CopilotCenter/MSGrauerKasten/output` verwendet wird oder passe den Pfad auf deine Zielumgebung an.

### Variante B: In anderer Umgebung übernehmen
Wenn der Skill in eine andere Site übernommen werden soll:
- gesamten Ordner `grauer-kasten` inklusive Unterordner kopieren,
- Zielpfade für Output prüfen,
- sicherstellen, dass die Asset-Datei mit übernommen wird,
- relative Verweise innerhalb des Skills unverändert lassen, sofern die Ordnerstruktur identisch bleibt.

## Wichtige Guardrails
- Inhalte dürfen nicht erfunden werden.
- Das Layout ersetzt nicht die inhaltliche Struktur.
- Das Logo soll aus dem separaten Asset kommen, nicht als fest codierte Fremdquelle.
- HTML und PDF gehören zusammen.
- Erfolg ist erst erreicht, wenn beide Formate erzeugt wurden.

## Download des Skills
Der Skill ist als Ordnerpaket aufgebaut. Für einen Download sollten diese Bestandteile gemeinsam übernommen werden:
- `grauer-kasten/SKILL.md`
- `grauer-kasten/preferences/pm-de-grauer-kasten/SKILL.md`
- `grauer-kasten/assets/MS LOGO.png`

Am einfachsten wird in SharePoint der komplette Ordner `grauer-kasten` heruntergeladen oder kopiert. So bleiben Skill-Datei, Design-Skill und Asset zusammen.

## Zusammenfassung
Die Lösung wurde so gebaut, dass sie klar modular ist:
- **Quelle**: englische Microsoft-Originalnews
- **Transformation**: deutsche Pressemitteilung
- **Design**: grauer-Kasten-Stil als separate Preference-Schicht
- **Branding**: Logo als eigenes Asset
- **Ausgabe**: HTML und PDF

Dadurch ist die Lösung nachvollziehbar, wartbar und bei Bedarf leicht übertragbar.
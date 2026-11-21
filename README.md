# MentiSeminar – Live-Abstimmung

Interaktives Abstimmungstool im Stil von Mentimeter für das **Seminar für Ausbildung und Fortbildung der Lehrkräfte Heidelberg**.
Die gesamte Anwendung steckt in einer einzigen Datei: [`index.html`](index.html) (HTML, CSS und JavaScript, ohne externe Abhängigkeiten).

## Funktionen

- **Drei Ansichten:** Editor (`#edit`), Präsentation (`#present`) und Teilnehmeransicht (`#vote`)
- **Sechs Fragetypen:** Multiple Choice, Wortwolke, Skala, offene Frage, Quiz mit Countdown, Ranking
- **Live-Ergebnisse** mit Animationen; Ergebnisse verbergen, Abstimmung sperren, zurücksetzen
- **Beitrittsansicht** mit großem QR-Code und 6-stelligem Teilnahme-Code
- **Bilder, PDFs und Dateien** zu jeder Frage (Anzeige auf der Folie und auf dem Handy, Download für Teilnehmende)
- **Export** der Ergebnisse als CSV/JSON, Import/Export der Präsentation als JSON
- Hell- und Dunkelmodus, responsiv, Tastaturbedienung, Screenreader-Unterstützung

## Ausprobieren

1. `index.html` herunterladen und per Doppelklick in Chrome, Edge oder Firefox öffnen.
2. Im Editor auf **▶ Präsentieren** klicken (öffnet einen neuen Tab).
3. Auf **📱 Teilnehmeransicht** klicken (gern mehrmals), Code eingeben und abstimmen.

Tastenkürzel in der Präsentation: `←`/`→` blättern, `Q` QR-Code, `H` Ergebnisse verbergen, `L` sperren, `F` Vollbild.

## Online bereitstellen (GitHub Pages)

1. Im Repository: **Settings → Pages**
2. Unter „Build and deployment“: Source **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → **Save**
3. Nach etwa einer Minute ist das Tool erreichbar unter
   `https://allerseitzcreator.github.io/MentiSeminar/`

Wird das Tool von dort geöffnet, verweist der QR-Code automatisch auf diese Adresse.

## Wichtige Einschränkung

Die aktuelle Version speichert alle Daten im Browser (`localStorage`) und synchronisiert nur **Tabs im selben Browser**.
Handys können die Seite über den QR-Code zwar öffnen, ihre Stimmen erreichen die Präsentation aber erst, wenn ein
Server angebunden ist (z. B. ein kleines PHP-Skript auf eigenem Webspace oder Firebase).
Die gesamte Datenlogik ist dafür im Modul `store` gekapselt; die Stellen für den Austausch sind im Code kommentiert.

Ohne Server gilt außerdem: Der Browser-Speicher fasst nur ca. 5 MB – Bilder, PDFs und Anhänge teilen sich diesen Platz.

# Apache207 – Show 100

Präsentation zum cinematischen Konzertfilm der 100. Arenashow (Tourfinale Hamburg, 12. Oktober 2026).
Deck by Leeroy – Flugmodus GmbH – For your eyes only.

## Öffnen

Die Präsentation ist eine statische Website. Sie braucht einen einfachen Webserver, weil die Video-Zuordnung aus `.video-slots.state.json` geladen wird. Ein Doppelklick auf `index.html` reicht nicht.

Lokal:

```bash
cd apache207-show100
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```

## GitHub Pages

1. Repository anlegen (am besten **privat**, das Material ist vertraulich) und alle Dateien hochladen, inklusive der Punkt-Dateien `.nojekyll` und `.video-slots.state.json`.
2. Settings → Pages → Source: „Deploy from a branch“, Branch `main`, Ordner `/ (root)`.
3. Nach ca. einer Minute unter `https://<user>.github.io/<repo>/` erreichbar.

Hinweis: GitHub Pages ist bei privaten Repos nur mit einem bezahlten Plan verfügbar. Alternativ Netlify oder Vercel (Ordner einfach hochladen).

## Bedienung

- Pfeiltasten / Leertaste: blättern
- Videos: Play-Button in der Mitte anklicken
- Drucken / PDF: Browser-Druckdialog, eine Folie pro Seite

## Struktur

```
index.html                 Präsentation (alle Folien)
support.js                 Laufzeit für die Folien
deck-stage.js              Folien-Steuerung (Skalierung, Navigation, Druck)
image-slot.js              Bildplätze
.video-slots.state.json    Welches Video auf welchem Medienplatz liegt
assets/                    Bilder und Videos
```

## Videos tauschen

Neue Datei nach `assets/videos/` legen, in `index.html` in der Liste `FILES` eintragen (z. B. `'Video 9': 'assets/videos/neu.mp4'`) und in `.video-slots.state.json` dem gewünschten Platz zuweisen:

```json
{ "songs": "Video 9" }
```

Plätze: `intro` (02), `show` (03), `idee` (04), `timeline` (06), `filming` (07), `songs` (08), `disclaimer` (09), `mood1`–`mood6` (10), `danke` (11).

Bild- und Videomaterial Dritter dient als interne Referenz. Rechte bei den jeweiligen Urhebern.

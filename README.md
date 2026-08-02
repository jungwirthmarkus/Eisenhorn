# Eisenhorn

Kleine Web-App für das Krafttraining am Eisenhorn. Zeigt beim Öffnen, wie das Horn
einzustellen ist, schlägt Sätze und Wiederholungen vor und protokolliert die Steigerung.

Alle Daten liegen ausschließlich lokal im Browser (`localStorage`). Es gibt keinen Server
und keinen Account. Wer die Seite öffnet, sieht nur eine leere App.

## Einrichten

1. Auf GitHub ein neues Repository anlegen, zum Beispiel `eisenhorn`. Sichtbarkeit **public**
   (GitHub Pages funktioniert im kostenlosen Tarif nur aus öffentlichen Repositories – im
   Repository liegt aber nur Code, keine Trainingsdaten).
2. Die vier Dateien hochladen: `index.html`, `manifest.json`, `sw.js`, `icon.png`.
3. Im Repository auf **Settings → Pages**. Unter *Source* `Deploy from a branch` wählen,
   Branch `main`, Ordner `/ (root)`, speichern.
4. Nach ein bis zwei Minuten ist die Seite unter
   `https://DEINNAME.github.io/eisenhorn/` erreichbar.

## Auf den Homescreen

Die Adresse in **Safari** öffnen, auf das Teilen-Symbol tippen, **Zum Home-Bildschirm**.
Danach startet die App im Vollbild ohne Browser-Leiste und funktioniert auch offline.

## Sicherung

Im Reiter **Mehr** exportierst du alle Einträge als JSON-Datei. Einmal im Monat reicht.
Die Datei enthält Trainingseinträge und Körpergewicht und lässt sich über denselben Reiter
wieder einlesen, etwa nach einem Gerätewechsel.

Wichtig: Löschst du das Icon vom Homescreen oder leerst du die Website-Daten in den
iOS-Einstellungen, sind die Einträge weg. Deshalb der Export.

## Ändern

Trainingsplan und Übungen stehen oben in `index.html` im Array `EX`:

```js
{ id:"knie", n:"Kniebeugen", w:"A", sets:3, lo:8, hi:12, url:"…", setup:"…" }
```

* `w` – `"A"` oder `"B"` für das Hauptprogramm, `"A+"` / `"B+"` für die Zusatzübungen
* `lo` / `hi` – Wiederholungsbereich; ab `hi` in allen Sätzen steigt der Widerstand
* `id` – nicht mehr ändern, sobald Einträge existieren, sonst verlierst du deren Verlauf

Neue Übungen einfach ergänzen. Bestehende Daten bleiben dabei erhalten.

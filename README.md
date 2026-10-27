# Wochenzettel – Essensplaner

Eine deutschsprachige, responsive Web-App zum Planen von Mahlzeiten für sieben Tage. Sie erstellt passende Wochenpläne, berechnet eine Einkaufsliste mit geschätzten Preisen und hilft dabei, das Wochenbudget im Blick zu behalten.

## Funktionen

- Wochenplan mit Rezepten und austauschbaren Gerichten
- Rezepte nach Ernährungsweise filtern: Alles, vegetarisch oder vegan
- Einkaufsliste mit Mengen, geschätzten Preisen und Abhak-Funktion
- Budget, Personenzahl und bevorzugte Geschäfte einstellen
- Gerichte als Favoriten speichern
- Einstellungen und Fortschritt lokal im Browser speichern
- Einen gespeicherten Wochenplan behalten und ihn zum Start jeder neuen Kalenderwoche automatisch erneuern
- Installierbare Web-App mit Offline-Grundfunktionen
- Mobilgeräte- und Desktop-Layout, inklusive hellem und dunklem Design

## Schnellstart

Die App braucht weder einen Build-Schritt noch zusätzliche Pakete.

1. Öffne `index.html` in einem Browser, um die App direkt auszuprobieren.
2. Für den Offline-Modus und die Installation muss die App über HTTPS oder lokal über `localhost` geöffnet werden. Service Worker funktionieren nicht zuverlässig direkt über `file://`.

Zum lokalen Testen mit Python unter Windows PowerShell:

```powershell
py -m http.server 8000
```

Rufe anschließend <http://localhost:8000> im Browser auf.

## Veröffentlichen

Lade den gesamten Projektordner mit den folgenden Dateien auf einen statischen Webhost hoch:

- `index.html` – Einstiegspunkt der App
- `manifest.webmanifest` – Installations- und App-Metadaten
- `service-worker.js` – Offline-Caching
- `favicon.svg` – App- und Browser-Icon
- `wochenzettel.html` – ursprünglicher Dateiname, weiterhin verwendbar

Der Ordner kann beispielsweise als statische Website auf GitHub Pages, Netlify oder einem vergleichbaren Hosting-Anbieter veröffentlicht werden. Es ist kein Server-Backend erforderlich. Nach dem Veröffentlichen öffnest du die HTTPS-Adresse; auf unterstützten Geräten kannst du die App über die Browserfunktion **Installieren** oder **Zum Startbildschirm hinzufügen** hinzufügen.

## Daten und Grenzen

- Pläne, Favoriten, Einstellungen und Einkaufs-Häkchen liegen im lokalen Speicher des jeweiligen Browsers und Geräts. Es gibt keine Konten oder geräteübergreifende Synchronisierung.
- Der Wochenplan wechselt automatisch am Montag der neuen lokalen Kalenderwoche. Dafür muss die App mindestens einmal in der neuen Woche geöffnet oder in den Vordergrund geholt werden; Änderungen und der letzte Plan bleiben bis dahin gespeichert.
- Die Preise sind Schätzungen und können von Laden, Region und aktuellen Preisen abweichen.
- Google Fonts werden nur bei bestehender Internetverbindung geladen. Ohne Verbindung werden Systemschriften verwendet.
- Für Hosting unter einem Unterpfad (zum Beispiel GitHub Pages) sind alle App-Dateien gemeinsam im selben Ordner abzulegen.
- Die Oberfläche passt sich an Handybildschirme an. Für die App-Installation auf dem Handy die HTTPS-Adresse im Browser öffnen und **Zum Startbildschirm hinzufügen** wählen.

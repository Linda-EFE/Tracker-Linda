# Tracker-Linda – Ernährungscoach

Eine kleine Web-App im Handy-Look. Sie stellt dir 13 Fragen und berechnet daraus deinen Kalorien- und Makroplan (Mifflin-St Jeor, Aktivitätsfaktor, Leitplanken für Mindestkalorien und Abnahmetempo). Am Ende erstellt sie einen Anweisungsblock für deine Claude-Projektanweisungen.

Alles steckt in einer Datei: `index.html`. Es gibt keinen Server und keine Installation. Die App läuft ohne Claude.

## Daten auf GitHub speichern (Handy und PC im Abgleich)

Code und Daten liegen getrennt:

- **`Tracker-Linda`** (dieses Repository, öffentlich): nur der Code der App.
- **`Tracker-Linda-Daten`** (privat): Hier speichert die App deine Antworten als `profil.json` im Branch `main`.

Jedes Gerät liest beim Öffnen den neuesten Stand.

Einmal pro Gerät einrichten:

1. Fine-grained Token anlegen: https://github.com/settings/personal-access-tokens/new
2. Bei **Repository access** „Only select repositories“ wählen und nur `Tracker-Linda-Daten` auswählen.
3. Bei **Permissions → Contents** „Read and write“ einstellen.
4. In der App oben rechts auf **Nur lokal** tippen, den Token einfügen und auf **Verbinden** tippen.

Der Token bleibt nur im Browser des jeweiligen Geräts gespeichert.

## Im Browser öffnen (GitHub Pages)

1. **Settings → Pages** öffnen und bei *Source* „Deploy from a branch“ wählen.
2. Branch `claude/stoic-archimedes-1050jp` und Ordner `/ (root)` wählen, dann **Save**.
3. Die App läuft unter https://linda-efe.github.io/Tracker-Linda/

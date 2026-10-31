# Tracker-Linda – Ernährungscoach

Eine kleine Web-App im Handy-Look. Sie stellt dir 13 Fragen und berechnet daraus deinen Kalorien- und Makroplan (Mifflin-St Jeor, Aktivitätsfaktor, Leitplanken für Mindestkalorien und Abnahmetempo). Am Ende erstellt sie einen Anweisungsblock für deine Claude-Projektanweisungen.

Alles steckt in einer Datei: `index.html`. Es gibt keinen Server und keine Installation. Die App läuft ohne Claude.

## Daten auf GitHub speichern (Handy und PC im Abgleich)

Die App speichert deine Antworten als Datei `daten/profil.json` im Branch `daten` dieses Repositorys. Den Branch legt sie beim ersten Speichern selbst an. Jedes Gerät liest beim Öffnen den neuesten Stand.

Einmal pro Gerät einrichten:

1. Auf GitHub: **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Bei **Repository access** „Only select repositories“ wählen und nur `Tracker-Linda` auswählen.
3. Bei **Permissions → Contents** „Read and write“ einstellen.
4. Token erzeugen und kopieren.
5. In der App oben rechts auf **Nur lokal** tippen, den Token einfügen und auf **Verbinden** tippen.

Der Token bleibt nur im Browser des jeweiligen Geräts gespeichert. Er wird nie ins Repository geschrieben.

**Halte das Repository privat.** Die Datendatei enthält deine Gesundheitsangaben.

## Im Browser öffnen

GitHub Pages geht bei privaten Repositories nur mit einem kostenpflichtigen GitHub-Plan. Kostenlos und privat geht es mit Cloudflare Pages:

1. Im Cloudflare-Dashboard: **Workers & Pages → Create → Pages → Connect to Git**.
2. `Linda-EFE/Tracker-Linda` auswählen.
3. Als Production branch `main` wählen. Framework: „None“, Build command leer lassen, Build output directory: `/`.
4. Unter **Settings → Builds → Branch control** die Preview-Builds abschalten (Preview branch: „None“). Dann baut das Speichern deiner Daten im Branch `daten` die Seite nicht jedes Mal neu.
5. Die App läuft dann unter `https://<projektname>.pages.dev`, auf dem Handy und am PC.

Lokal geht es auch: `index.html` doppelt anklicken.

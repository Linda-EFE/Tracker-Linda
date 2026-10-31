# Tracker-Linda – Ernährungscoach

Eine kleine Web-App im Handy-Look, die ohne weitere Dienste läuft.

1. **Interview:** 13 Fragen. Daraus berechnet die App deinen Kalorien- und Makroplan nach Mifflin-St Jeor mit Aktivitätsfaktor. Sie geht nie unter 1.200 kcal (Frauen) bzw. 1.500 kcal (Männer) und plant höchstens 0,75 kg Abnahme pro Woche.
2. **Plan:** Kalorien, Eiweiß, Kohlenhydrate und Fett pro Tag, die erwartete Veränderung pro Woche, das voraussichtliche Datum für dein Zielgewicht und drei persönliche Tipps.
3. **Tracker:** ein großer Kalorien-Ring für den Tag, drei Ringe für Eiweiß, Kohlenhydrate und Fett, ein Tagebuch mit allen Mahlzeiten und ein 7-Tage-Verlauf. Einträge kannst du ändern und löschen, auch für vergangene Tage. Sonntags zeigt die App einen Wochenrückblick mit genau einer Anpassung für die nächste Woche.

4. **Foto-Auswertung:** Foto aufnehmen oder kurz beschreiben, was du gegessen hast. Claude schätzt dann Portion, Kalorien und Makros, nennt seine Annahme und stellt bei Unsicherheit genau eine Rückfrage. Du prüfst die Werte und trägst sie ein.

Alles steckt in einer Datei: `index.html`.

## Foto-Auswertung einrichten

Die App nutzt dafür die Claude-Schnittstelle (API) von Anthropic. Die ist nicht im Claude-Abo enthalten und wird nach Nutzung abgerechnet, grob etwa 1 Cent pro Foto.

1. Auf https://console.anthropic.com ein Konto anlegen und unter **Billing** Guthaben aufladen.
2. Unter **API Keys** einen Schlüssel erstellen.
3. In der App oben rechts die Einstellungen öffnen und den Schlüssel bei **Claude-Schlüssel** einfügen.

Der Schlüssel bleibt nur im Browser des jeweiligen Geräts gespeichert. Er wird nie auf GitHub abgelegt.

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
2. Branch `main` und Ordner `/ (root)` wählen, dann **Save**.
3. Die App läuft unter https://linda-efe.github.io/Tracker-Linda/

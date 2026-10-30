# HohToolBox

Schnellzugriff auf die wichtigsten Uni-Links und eine kleine Offline-Notizfunktion, als Web-App fürs Smartphone.

> **Hinweis:** HohToolBox ist ein privates Hobbyprojekt eines Studierenden. Es steht in keiner Verbindung zur Universität Hohenheim und wird weder von ihr betrieben, unterstützt noch geprüft. Alle verlinkten Dienste und genannten Namen gehören ihren jeweiligen Betreibern bzw. Inhabern. Es handelt sich um ein nicht-kommerzielles Projekt, das in erster Linie für Freunde gedacht ist. Alle Angaben ohne Gewähr.

## Funktionen

- **Link-Übersicht:** Kacheln für die häufigsten Dienste (z. B. HohCampus, ILIAS, F.I.T., HohSearch, GPTalk) plus eine Liste weiterer Links (Mensa, Webmail, Semestertermine, Prüfungsamt, IT-Hilfe u. a.).
- **Notizen:** Einfache Notizen mit Titel, Suche und automatischem Speichern. Sie funktionieren auch offline, liegen ausschließlich lokal im Browser und lassen sich als JSON exportieren und wieder importieren.
- **Als App installierbar (PWA):**
  - Android/Chrome: eigener Installations-Button, der einmalig angeboten wird.
  - iOS/Safari: kurze Anleitung („Teilen → Zum Home-Bildschirm").
- **Update-Hinweis:** Erscheint eine neue Version, zeigt die App ein Banner mit „Neu laden". Die Seite wird nie ungefragt neu geladen.
- **Hell/Dunkel/Auto:** Umschaltbares Farbschema, das standardmäßig der Systemeinstellung folgt.
- **Offline-fähig:** Ein Service Worker legt die App im Cache ab; Netzwerk hat dabei Vorrang, sodass man online immer die aktuelle Version sieht.
- **Info & Feedback:** Eingebauter Dialog mit Disclaimer, Datenschutzhinweis, Versionsnummer und Link zum Melden von Problemen auf GitHub.

## Datenschutz

HohToolBox verwendet kein Tracking, keine Cookies zu Analysezwecken und lädt keine externen Skripte oder Schriften. Notizen und Einstellungen werden nur im lokalen Speicher (`localStorage`) deines Browsers abgelegt und nicht übertragen. Beim Aufruf sieht der Hosting-Anbieter (z. B. GitHub Pages) technisch bedingt Verbindungsdaten wie die IP-Adresse.

Da die Notizen nur lokal gespeichert sind, gehen sie beim Löschen der Website-Daten verloren. Sichere sie bei Bedarf über „Notizen → Exportieren".

## Installation und Nutzung

Die App ist eine statische Webseite ohne Build-Schritt oder Abhängigkeiten.

**Selbst hosten (z. B. GitHub Pages):**

1. Repository forken oder herunterladen.
2. Unter *Settings → Pages* den Branch auswählen und veröffentlichen.
3. Die Seite im Smartphone-Browser öffnen.

**Als App installieren:**

- **Android (Chrome):** Auf „App installieren" im Banner tippen oder Menü ⋮ → „App installieren".
- **iOS (Safari):** Teilen-Symbol → „Zum Home-Bildschirm".

## Anpassen

Die Links stehen in `index.html` im Skript-Block ganz oben als Listen `CORE` (Kacheln) und `MORE` (Liste), jeweils im Format `[Icon, Name, Beschreibung, URL]`.

## Dateien

| Datei | Zweck |
| --- | --- |
| `index.html` | Startseite, Link-Übersicht, Installationshilfe, Update-Hinweis, Info-Dialog |
| `notes.html` | Notizen-Seite |
| `sw.js` | Service Worker (Offline-Cache, Update-Mechanismus) |
| `manifest.webmanifest` | PWA-Manifest |
| `icon-192.png`, `icon-512.png` | App-Icons |

## Eine neue Version veröffentlichen

1. Dateien ändern.
2. `VERSION` in `index.html` und `CACHE` in `sw.js` hochzählen (sonst erkennt der Browser kein Update).
3. Hochladen bzw. pushen. Nutzer sehen beim nächsten Öffnen den Hinweis „Neue Version verfügbar".

## Feedback

Fehler, Ideen oder fehlende Links gern über den Reiter **Issues** in diesem Repository.

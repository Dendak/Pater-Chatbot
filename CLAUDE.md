# CLAUDE.md – Pater-Chatbot

## Zweck
Arbeitsblatt-Webseite „Chatbot-Werkstatt“ für den Unterricht (Privatgymnasium der Herz-Jesu-Missionare).
Teil 1: Schülergruppen führen ein Interview, nehmen es auf und erstellen mit Buzz (Whisper, offline) ein
Transkript im `F:`/`A:`-Format. Daraus soll in der nächsten Stunde ein Chatbot entstehen.

## Stack
- Eine statische HTML-Seite mit eingebettetem CSS und wenig Vanilla-JS, ohne Abhängigkeiten.
- JS merkt sich nur die Checkbox-Häkchen pro Gerät in `localStorage` (Schlüssel `auftrag-<id>`).
- Hell/Dunkel über `prefers-color-scheme` bzw. `data-theme`.
- Sprache der Seite und der Commits: Deutsch.

## Struktur
- `index.html` – die gesamte Seite (Abschnitte 0–4: Einstieg, Fragen, Aufnahme, Transkript, Sichern).
- `docs/POZNAMKY.md` – Arbeitsnotizen / offene Punkte / Verlauf.

## Befehle
- Kein Build, keine Tests, kein Paketmanager.
- Lokal ansehen: `index.html` im Browser öffnen (oder z.B. `python -m http.server` im Repo-Ordner).

## Deployment
- GitHub Pages (legacy) aus `main` / Root → https://dendak.github.io/Pater-Chatbot/
- Jeder Push auf `main` ist sofort live. Es gibt keine weiteren Branches, keine Workflows, keine `CNAME`.

## Vorsicht
- Live-Deploy: Push auf `main` = öffentlich sichtbar für Schüler:innen.
- Das Repo ist öffentlich: niemals Interview-Aufnahmen, Transkripte, Schülernamen oder andere
  personenbezogene Daten committen (die Seite selbst verlangt, dass Aufnahmen auf dem Schul-PC bleiben).
- Externe Einbettung: Abschnitt 0 bindet `https://fragnach.org/inge-oder-kurt/` per `<iframe>` ein.
- Keine API-Keys im Frontend ablegen – relevant, sobald der Chatbot (Teil 2) gebaut wird.
- Aktuell keine Geheimnisse, keine verschlüsselten Daten, keine `CNAME` im Repo.

## Arbeit über mehrere Geräte
- GitHub (`Dendak/Pater-Chatbot`) ist die Quelle der Wahrheit.
- Session-Start: `git pull`, dann diese CLAUDE.md und [docs/POZNAMKY.md](docs/POZNAMKY.md) lesen.
- Session-Ende: `docs/POZNAMKY.md` aktualisieren (Offen + Verlauf), committen, pushen.
- Größere/riskante Änderungen über Branch + Pull Request, weil `main` live deployt.
- Repo lokal unter `C:\Users\holub\code\Pater-Chatbot` – nie in OneDrive.

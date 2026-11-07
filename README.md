# teconas.github.io

Landingpages und Datenschutzerklärungen für die Apps & Spiele von teconas (u. a. für Google Play).
Wird per GitHub Pages (Jekyll, Theme `minima`) unter https://teconas.github.io veröffentlicht.

Diese Datei und `CLAUDE.md` werden **nicht** veröffentlicht (`exclude` in `_config.yml`).

## Struktur

```
_config.yml          zentrale Konfiguration: Site-Werte, Spieleliste (games), defaults, exclude
_layouts/            game.html (Landingpage), privacy.html (Datenschutzerklärung)
_includes/           header.html (Navigation aus games), draft-notice.html
index.md             Startseite, listet alle Spiele aus games
<slug>/index.md      Landingpage eines Spiels
<slug>/privacy.md    Datenschutzerklärung eines Spiels
```

## URL-Schema

| Seite                 | URL                                          |
|-----------------------|----------------------------------------------|
| Startseite            | `https://teconas.github.io/`                 |
| Landingpage           | `https://teconas.github.io/<slug>/`          |
| Datenschutzerklärung  | `https://teconas.github.io/<slug>/privacy/`  |

## Neues Spiel hinzufügen

1. Ordner `<slug>/` anlegen (lowercase, Bindestriche), z. B. `blitzer-royale/` als Vorlage kopieren.
2. In `_config.yml` unter `games` eintragen (`slug`, `name`, `description`, `draft: true`, später `play_store`).
3. In `_config.yml` unter `defaults` einen Block `path: <slug>` mit `game: <slug>` ergänzen.
4. `title` in `index.md` und `privacy.md` anpassen, alle `TODO`s abarbeiten (`grep -rn TODO <slug>/`).
5. `draft: true` entfernen, pushen, `https://teconas.github.io/<slug>/privacy/` in der Play Console hinterlegen.

## Lokale Vorschau

Benötigt Ruby + Bundler:

```bash
gem install github-pages
jekyll serve
```

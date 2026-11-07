# CLAUDE.md

## Zweck
GitHub-Pages-User-Site `teconas.github.io`: Datenschutzerklärungen und Landingpages für die Play-Store-Apps von teconas. Jekyll mit Theme `minima` (2.5.x auf GitHub Pages), kein eigenes Gemfile.

## Struktur und URLs
- `_config.yml`: einzige zentrale Stelle. Site-Werte (`title`, `author`, `owner`, `email`), Spieleliste `games` (`slug`, `name`, `description`, `draft`, `play_store`), `defaults`, `exclude`, `permalink: pretty`.
- `defaults`: `""` → Layout `game`, `lang: en`; `*/privacy.md` → Layout `privacy`, `lang: de`; je Spiel `path: <slug>` → `game: <slug>`.
- Layouts `game`/`privacy` holen das Spiel per `site.games | where: "slug", page.game` und zeigen bei `draft: true` den Entwurfshinweis.
- `_includes/header.html` überschreibt minima: Navigation aus `site.games`.
- `/privacy/` → `privacy.md` (Datenschutz der Website; eigenes Front Matter `layout: default`, `lang: de`; `*/privacy.md` greift im Root nicht).
- `/` → `index.md`, `/<slug>/` → `<slug>/index.md`, `/<slug>/privacy/` → `<slug>/privacy.md`.

## Neues Spiel hinzufügen
1. Ordner `<slug>/` mit `index.md` und `privacy.md` (Vorlage: Stub eines Entwurfs-Spiels oder Gliederung von `blitzer-royale/privacy.md`).
2. Eintrag in `games` (mit `draft: true`) und `defaults`-Block `path: <slug>` → `game: <slug>`.
3. Alle app-spezifischen Stellen als `TODO` markieren; vor Veröffentlichung `grep -rn TODO <slug>/ _config.yml` leer bekommen.
4. `draft: true` entfernen, Play-Store-Link eintragen.
5. User trägt `https://teconas.github.io/<slug>/privacy/` in der Play Console ein.

## Harte Regeln
- Veröffentlichte Datenschutztexte nur auf ausdrückliche Anweisung inhaltlich ändern (auch keine Tippfehler-Korrekturen). Kontaktdaten darin bleiben hart codiert, außer der gerenderte Text bleibt exakt identisch.
- URLs, die in der Play Console hinterlegt sind, dürfen sich nicht ändern (Ordnernamen, Dateinamen, `permalink`).
- `exclude` in `_config.yml` pflegen, wenn neue interne Dateien dazukommen. GitHub Pages rendert sonst auch Markdown ohne Front Matter. Jekyll-Standard-Excludes sind dort mit aufgeführt, weil die Liste sie überschreibt.
- Keine externen Ressourcen (Fonts, Skripte, CDNs), kein Tracking, keine Cookies, kein `google_analytics`.
- Keine `.nojekyll`-Datei.
- Zeilen, die mit einer Zahl und Punkt beginnen (z. B. Datum unter „Stand“), escapen: `7\. November 2026.` Sonst rendert Markdown eine Liste und die Zahl geht verloren.

## Deployment
- Nicht selbst committen oder pushen, das macht der User.
- Push auf den Default-Branch `main` = live (GitHub Pages baut selbst).
- Lokale Vorschau nur mit Ruby: `gem install github-pages` und `jekyll serve`. Auf diesem Rechner ist aktuell kein Ruby installiert; dann statisch prüfen (Front Matter, Liquid, Links, `exclude`).

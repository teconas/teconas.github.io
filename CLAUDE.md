# CLAUDE.md

## Purpose
GitHub Pages user site `teconas.github.io`: privacy policies and landing pages for the Play Store apps by teconas. Jekyll with theme `minima` (2.5.x on GitHub Pages), no Gemfile of its own.

## Language
Everything is English, except the content inside `blitzer-royale/` (the game and its privacy policy are German).

## Structure and URLs
- `_config.yml`: the single central place. Site values (`title`, `author`, `owner`, `email`), games list `games` (`slug`, `name`, `description`, `draft`, `play_store`), `defaults`, `exclude`, `permalink: pretty`.
- `defaults`: `""` → layout `game`; `*/privacy.md` → layout `privacy`; per game `path: <slug>` → `game: <slug>`; `blitzer-royale/privacy.md` → `lang: de`. Site `lang: en`.
- Layouts `game`/`privacy` look up the game via `site.games | where: "slug", page.game` and show the draft notice if `draft: true`.
- `_includes/header.html` overrides minima: navigation from `site.games`.
- `/privacy/` → `privacy.md` (website privacy policy; own front matter `layout: default`; `*/privacy.md` does not match the root).
- `/` → `index.md`, `/<slug>/` → `<slug>/index.md`, `/<slug>/privacy/` → `<slug>/privacy.md`.

## Adding a new game
1. Folder `<slug>/` with `index.md` and `privacy.md` (template: a draft game's stub or the outline of `blitzer-royale/privacy.md`).
2. Entry in `games` (with `draft: true`) and a `defaults` block `path: <slug>` → `game: <slug>`.
3. Mark all app-specific parts as `TODO`; before publishing, `grep -rn TODO <slug>/ _config.yml` must be empty.
4. Remove `draft: true`, add the Play Store link.
5. The user enters `https://teconas.github.io/<slug>/privacy/` in the Play Console.

## Hard rules
- Change the content of published privacy policies only on explicit instruction (not even typo fixes). Contact details in them stay hard-coded unless the rendered text stays exactly identical.
- URLs entered in the Play Console must not change (folder names, file names, `permalink`).
- Maintain `exclude` in `_config.yml` when new internal files are added. GitHub Pages otherwise renders Markdown without front matter too. Jekyll's default excludes are repeated there because the list replaces them.
- No external resources (fonts, scripts, CDNs), no tracking, no cookies, no `google_analytics`.
- No `.nojekyll` file.
- Escape lines starting with a number and a period (e.g. a German date under "Stand"): `7\. November 2026.` Otherwise Markdown renders a list and the number is lost.

## Deployment
- Do not commit or push yourself; the user does that.
- Push to the default branch `main` = live (GitHub Pages builds by itself).
- Local preview only with Ruby: `gem install github-pages` and `jekyll serve`. Ruby is currently not installed on this machine; then check statically (front matter, Liquid, links, `exclude`).

# teconas.github.io

Landing pages and privacy policies for the apps & games by teconas (e.g. for Google Play).
Published via GitHub Pages (Jekyll, theme `minima`) at https://teconas.github.io.

This file and `CLAUDE.md` are **not** published (`exclude` in `_config.yml`).

## Structure

```
_config.yml          central configuration: site values, games list (games), defaults, exclude
_layouts/            game.html (landing page), privacy.html (privacy policy)
_includes/           header.html (navigation from games), footer.html (email, website privacy), draft-notice.html
index.md             home page, lists all games from games
privacy.md           privacy policy of the website itself
<slug>/index.md      landing page of a game
<slug>/privacy.md    privacy policy of a game
```

## URL scheme

| Page                    | URL                                          |
|-------------------------|----------------------------------------------|
| Home                    | `https://teconas.github.io/`                 |
| Website privacy policy  | `https://teconas.github.io/privacy/`         |
| Game landing page       | `https://teconas.github.io/<slug>/`          |
| Game privacy policy     | `https://teconas.github.io/<slug>/privacy/`  |

## Adding a new game

1. Create a folder `<slug>/` (lowercase, hyphens), e.g. by copying `blitzer-royale/` as a template.
2. Add the game under `games` in `_config.yml` (`slug`, `name`, `description`, `draft: true`, later `play_store`).
3. Add a block `path: <slug>` with `game: <slug>` under `defaults` in `_config.yml`.
4. Adjust `title` in `index.md` and `privacy.md` and resolve all `TODO`s (`grep -rn TODO <slug>/`).
5. Remove `draft: true`, push, and enter `https://teconas.github.io/<slug>/privacy/` in the Play Console.

## Local preview

Requires Ruby:

```bash
gem install github-pages
jekyll serve
```

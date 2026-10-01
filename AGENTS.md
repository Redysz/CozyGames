# Agent notes — cozy_games_site

Plain static site, no build step. Intended for GitHub Pages (`.nojekyll` is present so
underscore-prefixed paths such as `games/magic_diamond_linker/` are served).

## Layout

```
index.html                              # landing page + game card list
games/<slug>.html                       # one page per game
games/<game_folder>/                    # that game's screenshots (webp)
assets/style.css                        # all styling, CSS variables at the top
assets/diamond.png, favicon.png         # cropped from magic_diamond_linker/assets/diamond_no_flash.png
```

## Preview

```bash
python -m http.server 8099   # from the repo root
```

## Conventions

- Muted purple palette; every colour comes from the `:root` variables in `style.css`.
  Do not hardcode colours in the HTML.
- Site language is English.
- Links that do not exist yet are `<span class="btn disabled">… coming soon</span>`,
  never dead `<a href="#">`. Swap them for `<a class="btn primary" href="…">` on release.
- Adding a game: new `games/<slug>.html` (copy `magic-diamond-linker.html` as the
  template), screenshots in `games/<folder>/`, and a `.card` block in `index.html`.

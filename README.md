# prathyaypgm-alt.github.io

Fatal's website: games, repos and questionable decisions.
Live at **https://prathyaypgm-alt.github.io**

## What's here

- `index.html` — the whole site (plain HTML/CSS/JS, no build step)
- `assets/img/` — game covers, favicon, social preview image
- `assets/tex/` — FatalCraft textures used for its card art
- `play/fatalcraft/` — FatalCraft compiled for the browser with [pygbag](https://github.com/pygame-web/pygbag)

## Adding a game

Copy one of the `<article class="game">` blocks in `index.html`, swap the art, text and links,
and set `data-tags` (`browser`, `puzzle`, `adventure`, `history`) so the filters pick it up.

To make a pygame game playable on the site:

1. Wrap the main loop in `async def main():` and add `await asyncio.sleep(0)` after `clock.tick(...)`,
   then call `asyncio.run(main())`.
2. Use `.ogg` for sounds.
3. Run `pygbag --build your_game_folder` and copy `build/web/` into `play/<game>/`.
4. Give the card a button with `data-play="play/<game>/index.html"`.

# PP7 Deacon's Quorum Arcade

A tiny static arcade site showing the games the PP7 deacons quorum made.
No build step, no backend: plain HTML/CSS/JS, deployed on Vercel.

```
index.html     home page (tile grid, built from games.js)
play.html      play page: play.html?g=<slug> wraps the game in a full-screen iframe
games.js       the list of games  <-- edit this to add a game
games/         one self-contained HTML file per game (games/<slug>.html)
shots/         one screenshot per game (shots/<slug>.webp or .png)
style.css      retro arcade styling
```

## Adding a new game

1. **Drop the game in `/games`.** Save the single-file HTML game as
   `games/<slug>.html`, where `<slug>` is lowercase-with-dashes, e.g.
   `games/space-lane-dodge.html`. If it uses other files (images, sounds), put
   them next to it and use relative paths.
2. **Add a screenshot in `/shots`.** Play the game, take a screenshot
   (about 3:2, e.g. 900x600), and save it as `shots/<slug>.webp` (or `.png`).
   Try to keep it under ~200 KB.
3. **Add an entry to `games.js`:**

   ```js
   { slug: "space-lane-dodge", title: "Space Lane Dodge", maker: "Drew", shot: "shots/space-lane-dodge.webp" },
   ```

   `maker` is optional (use `""` to hide the credit). Tiles appear in the
   order they are listed.
4. Commit and push to `main`. Vercel redeploys automatically.

To preview locally: `python3 -m http.server` in this folder, then open
http://localhost:8000.

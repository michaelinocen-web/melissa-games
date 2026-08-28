# Melissa's Game Hub 🎮💗

A collection of interactive learning games, built for Melissa. Fully self-contained — no build tools, no dependencies beyond two Google Fonts links, works on any device with a browser.

## What's in here

```
index.html            The home page — a hub showing all games as cards
kids.html              "Wiggly Earth" — plate tectonics game (flip cards, tap-to-erupt volcano, earthquake-proof buildings, Pangea time slider)
countries-flags.html   "Flags Around the World" — 5 levels x 10 countries, facts + guess-the-flag quiz, scores saved per level
universe.html          "The Universe & Planets" — space-themed, 8 explorable topics (Big Bang, star/planet birth, Earth's origin, the Sun, galaxies, star death), 9-question quiz
```

Opening `index.html` shows a hub of game cards. Tapping a card opens that game. Each game has a "🏠 Home" button on every card that returns to this hub.

## Publishing with GitHub Pages

1. Create a new repository on GitHub (e.g. `melissas-games`).
2. Upload all 3 files above directly into the root of the repo (drag-and-drop via "Add file → Upload files," or paste each file's code directly into "Create new file").
3. Go to **Settings → Pages** in the repo.
4. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
5. Save. The hub will be live within a minute or two at:
   `https://<your-username>.github.io/<repo-name>/`

That URL is the one to bookmark and share with Melissa — it opens straight to the hub.

## Adding a new game later

1. Add the new game's `.html` file to the repo (same way as above).
2. Open `index.html`, find the `GAMES` array near the top of the `<script>` section, and add one entry:

```js
{
  icon: "🎨",                 // any emoji
  title: "New Game Name",
  desc: "A one-line description of the game.",
  href: "new-game-file.html", // the filename you uploaded
  progressKey: null           // or a localStorage key string if the game saves scores
}
```

3. Commit the change. The new card appears on the hub automatically — no other changes needed.

## How scores are saved

`countries-flags.html` saves each level's last score to the browser's `localStorage` (a small amount of storage built into every browser, tied to that specific device/browser). The hub reads that same storage to show progress on its card. This means:
- Scores persist across visits on the same device/browser.
- Scores do **not** sync across different devices (e.g., phone vs. iPad) — each one keeps its own separate progress.

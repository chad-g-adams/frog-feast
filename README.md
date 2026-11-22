# Frog Feast

A multiplication game for the iPad. Hop the frog around the pond and eat every
lily pad whose answer equals the number at the top (for example, when the number
is 24, eat `4 × 6`, `8 × 3`, `12 × 2`, ...).

## How to play

- **Tap a lily pad** to hop there (or swipe to hop one square).
- **Tap the frog**, or the **Chomp!** button, to eat the pad it is sitting on.
- Eating a wrong answer costs a heart, and the game shows the correct answer.
- Eat all the right answers to finish the level. Three hearts per game.
- **Streaks:** right answers in a row are worth more each time (10, 20, 30,
  up to 50 points), and a mistake resets the streak.
- **Stars:** each level earns 3 stars for no mistakes, 2 for one mistake and
  1 otherwise. A level with fewer than 3 stars can be retried straight away.
- **New characters:** stars earned during a game unlock new animals to play as
  (4, 8, 13, 19, 26 and 34 stars). Switch on the level-complete screen or from
  the ☰ menu. Every new game starts again as the frog with zero stars.
- **Leaderboard:** when a game ends with a top-10 score, type a name (or tap
  a name used before) to save it. The **🏆 Leaderboard** button on the start
  screen shows the list. Scores are kept on the iPad only.
- On the start screen, choose the times tables (up to 5, 10 or 12) and whether
  snakes roam the pond. The **☰** button returns to that screen.
- With a keyboard: arrow keys to move, space to eat.

## Files

The game is three plain files, with nothing to install or build:

- `index.html` – the whole game
- `icon.png` – the home-screen icon
- `sw.js` – lets the game work without internet (only when hosted over HTTPS)

## Getting it onto the iPad

The iPad cannot run the game from a file sent by AirDrop or email (the Files
app shows web pages with scripts switched off), so the iPad needs to load it
from a web address in Safari. Pick one of the two ways below.

### Option A: from this computer, over home Wi-Fi (quickest)

The game works only while this computer is on and running the command below.

1. On this computer, in the game folder, run:

   ```
   python3 -m http.server 8000
   ```

2. Find this computer's Wi-Fi address with `hostname -I` (it looks like
   `192.168.0.77`).
3. On the iPad, connected to the same Wi-Fi, open **Safari** and go to
   `http://192.168.0.77:8000` (use your address).
4. Tap the **Share** button (the square with an arrow), then
   **Add to Home Screen**, then **Add**.

The Frog Feast icon now opens the game full screen. If the page does not load,
the computer's firewall may be blocking port 8000 (`sudo ufw allow 8000/tcp`).

### Option B: free web hosting (works anywhere, and offline)

Once the game is hosted on an `https://` address, the iPad saves a copy after
the first visit, and the game then works with no internet and without this
computer.

1. On this computer, go to <https://app.netlify.com/drop> and drag the game
   folder onto the page. (GitHub Pages or Cloudflare Pages work the same way.)
   Netlify gives you an address like `https://something.netlify.app`.
2. On the iPad, open that address in **Safari**.
3. Tap **Share**, then **Add to Home Screen**, then **Add**.
4. Open the game once from the new icon while online. After that it works
   offline.

The address is public, but it contains only the game. Nothing is collected;
settings and the best score stay on the iPad.

## Notes

- Best played in landscape. Use the iPad's rotation lock to stop it flipping.
- To stop a child leaving the game, turn on Guided Access (Settings →
  Accessibility → Guided Access), then triple-click the Home button in the game.

# Door Codes

A spooky math game in one HTML file. Every door in the hallway has a keypad lock, and the code is the answer to a math problem. Hide from Static when the lights flicker, fix the power before Grinny the animatronic gator reaches your door, pick the real door when Snapjaw the mimic shows up, sneak past Hush without a wrong code (it hunts by sound), help Mr. Bones the janitor with a counting word problem for a free item, snatch your gold back from Swipe the raccoon before he reaches the vent, freeze whenever Peeper turns to look, nail down planks faster than Munch the termite eats the floor, push the right floor button in Ding's elevator (sometimes it's an express), hook up train cars for Cinder the lost caboose, help Grimy (Grinny's girlfriend) plan a party and get her bow 🎀, which sends Grinny back to the stage once, and outrun the ink from Door 45 to the exit at Door 50.

Each run picks its cast: the plan for every ten-door block has fixed slots and either-or slots (Hush or Peeper, Static or Munch, Mr. Bones or Cinder, …), and every slot gets a door with at least one empty door between events.

- **Codes, by grade:** Grade 2 plus & minus, Grade 3 times tables, Grade 4 mystery numbers (everything from Grades 2–3 plus missing-number problems like `7 × ? = 56`, sharing the same fact mastery), or Grade 6–7 pre-algebra (negatives, order of operations, percents and ratios, one- and two-step equations, distributing, x on both sides). Pre-algebra adds a ± key; answers are whole numbers and can be negative. Grade 4 keeps the old `mix` id so existing saves land there.
- **Players:** each player has their own save. The first player keeps the original `doorcodes.v1` key, and later players use `doorcodes.v1.p2` and up. The Flex Board ranks everyone's best escape on the device.
- **Nightmare:** two hearts, monsters 30% faster, ranked above normal runs on the Flex Board.
- **Adaptive:** times tables start with 2s, 10s and 5s and unlock the next table once the newest one is solid. Plus & minus climbs from within-10 to two-digit numbers. Missed facts come back a few doors later.
- **Glimmer the firefly** draws a dot picture and a strategy after two misses. In pre-algebra she works the problem step by step.
- **Monster Files** is a page-turning book: one spread per character with a live photo, danger rating, survival tip and how many times you've seen it. Swipe, arrow keys or the page buttons. Badges are the second tab.
- **Grown-ups** screen: fact mastery grid, accuracy, daily counts, pick which tables to practise.

Progress lives in the browser's localStorage. All art and sound are drawn and synthesized in code (Canvas 2D + Web Audio), no assets.

## Run locally

```sh
bun server.ts                # http://127.0.0.1:4848
HOST=0.0.0.0 bun server.ts   # reachable from other devices on your network
```

Or open `public/index.html` in a browser.

## Deploy

Static assets on Cloudflare Workers:

```sh
npm install
npm run deploy
```

## Testing

`?debug` exposes `window.__dc` (`S`, `scene`, `genQuestion`, `hintFor`, `asking`, …). `?debug&test=static|grinny|hush|mimic|bones|train|swipe|peeper|munch|ding|cinder|grimy|shop|bonus|inky|win` starts a run straight into that event; add `&alg` to switch the current player to pre-algebra. In Ding's elevator, `window.__dc.lastFloor` is the right button.

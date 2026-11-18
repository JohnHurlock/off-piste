# Off Piste: website version

The whole game is one file: `index.html`. Host it anywhere that serves static files. No server code and no keys needed.

## Put it online (free)

### Option A: Netlify Drop (easiest, about 2 minutes)
1. Go to https://app.netlify.com/drop
2. Drag the whole `violet-hour-web` folder onto the page.
3. Netlify gives you a link like `https://something-random.netlify.app`. Make a free account when it asks, or the site is deleted after an hour.
4. Optional: in **Site configuration → Change site name**, pick a nicer name, e.g. `violet-hour-ski`.

To update the game later, open your site in Netlify, go to **Deploys**, and drag the folder in again.

### Option B: GitHub Pages
1. Make a new public repository on GitHub (for example `violet-hour`).
2. Upload `index.html` (**Add file → Upload files**).
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, then pick `main` and `/ (root)`.
4. After a minute the game is live at `https://<your-username>.github.io/violet-hour/`.

## Playing with friends
- On the title screen, type a name and press **New room**, then **Copy invite link** and send it to friends.
- Anyone who opens the link joins your room, so you all ski the same mountain live.
- You can also type the same room code into **Room code** and press **Join room**.
- Works in Chrome on Chromebooks, Windows, Mac, Android, and in Safari on iPhone and iPad.

## How multiplayer works
- Everyone in a room sends their position and pose about 12 times a second through two free public relays (MQTT brokers at broker.emqx.io and broker.hivemq.com) over a normal secure web connection. This works on school, office and phone networks, where direct peer-to-peer links are often blocked.
- The game sends to both relays, so a room keeps working if one relay is down or blocked.
- There is no host. Anyone can leave and the room carries on.
- Everyone gets the same mountain each day. It changes at midnight UTC.
- The title screen lists who is in your room and whether they are skiing or still in the lobby. A banner pops up when someone joins or leaves.

## Limits to know
- The relays are public. Anyone who knew your room code could see riders' positions and names, so don't use a real full name.
- The relays are free community services, so they can occasionally be slow or down.
- About 8 players per room is comfortable.
- Cost: hosting on Netlify or GitHub Pages is free. A custom domain such as `offpiste.com` is optional and costs roughly $10–20 a year.

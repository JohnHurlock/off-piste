# Violet Hour: website version

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
- Players connect straight to each other through WebRTC (peer-to-peer). The free public PeerJS service (`0.peerjs.com`) only introduces players to each other. Game traffic doesn't pass through a game server.
- The first person in a room hosts it and passes updates along. Each rider sends their position and pose 20 times a second.
- If the host leaves, the others take over within a few seconds.
- Everyone gets the same mountain each day. It changes at midnight UTC.

## Limits to know
- Some school and office networks block peer-to-peer connections. If friends can't connect on one network, try another, such as home Wi-Fi or a phone hotspot. Fixing this for every network would need a relay (TURN) server, which usually costs money.
- The PeerJS service is free and run by volunteers, so it can occasionally be slow or down.
- About 8 players per room is comfortable.
- Cost: hosting on Netlify or GitHub Pages is free. A custom domain such as `violethour.com` is optional and costs roughly $10–20 a year.

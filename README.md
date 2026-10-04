# 🛰️ Bot Hub

A one-page site that links to every bot dashboard and shows whether each bot is online.
Pure HTML — no build, no server. Runs on GitHub Pages for free.

## Put it on GitHub Pages (3 minutes)
1. GitHub → **New repository** → name it `bot-hub` → Public → Create.
2. **Add file → Create new file** → name `index.html` → paste the contents of `index.html` → Commit.
3. Repo **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
4. Wait ~1 minute. Your site is at `https://<your-username>.github.io/bot-hub/`.

## Add / change bots
Open `index.html`, scroll to the `BOTS` list near the bottom:
```js
{ name: 'MailDesk', emoji: '📬', desc: '…', url: 'https://ce30bbdyvw.apps.bot-hosting.cloud', colors: ['#f6a623', '#ff6b8b'] },
```
Copy a line, change the name/emoji/url/colours. `url` has no trailing slash. Commit — Pages updates by itself.

## Live stats
The page reads each bot's `/health`. Bots built after Oct 2026 send the CORS header that allows this and
show uptime / servers / open threads / storage. Older builds just show "Reachable" — update their `index.js`
(one line: `res.set('Access-Control-Allow-Origin', '*')` on the `/health` route) to get full stats.

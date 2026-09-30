# 🦆 Duck & Lemon Tycoon

A multiplayer idle/tycoon game for the browser. Pick and sell lemons, buy ducks, upgrade your lemon business through 15 stages, and rebirth for permanent multipliers. Includes a live leaderboard, online player list and chat.

Built with Node.js + WebSockets (`ws`). The server is authoritative, so players can't cheat from the browser.

## Run locally

Requires [Node.js](https://nodejs.org) 18+.

```bash
npm install
npm start
```

Then open http://localhost:3000 (open two tabs to test multiplayer).
On Windows you can also just double-click `start.bat`.

## Deploy for free on Render (permanent link)

1. Push this repo to GitHub.
2. On [render.com](https://render.com), sign in with GitHub.
3. Click **New > Blueprint**, pick this repo, and confirm (it reads `render.yaml`).
   - Or **New > Web Service** with Build Command `npm install` and Start Command `npm start`.
4. After it builds you get a link like `https://duck-tycoon.onrender.com`.

### Free-tier limits
- The service sleeps after ~15 minutes of no traffic, so the first visit afterwards takes about a minute.
- Free services don't keep files between restarts, so `saves.json` can reset. To keep saves, attach a persistent disk (paid plan), mount it at e.g. `/data`, and set the environment variable `DATA_DIR=/data`.

## Configuration
- `PORT` (default 3000) - set automatically by most hosts.
- `DATA_DIR` (default project folder) - where `saves.json` is stored.
- `public/config.js` - balance numbers (costs, income, rebirth scaling). Edit to make the game shorter or longer.

## Project layout
```
server.js          game server (WebSocket + static files + saves)
public/index.html  game client
public/config.js   shared balance config
render.yaml        one-click Render deploy
start.bat          Windows launcher
```

## License
MIT

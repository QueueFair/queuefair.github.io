# Group Queue Filter

Shuffle only the songs from people who are actually present — built for Spotify group playlists.

## Files

```
group-queue-filter/
├── index.html   — markup and structure
├── style.css    — all styling
├── app.js       — all logic (Spotify auth, API calls, queue building)
└── README.md    — this file
```

## Setup

### 1. Get a Spotify Client ID

1. Go to [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard)
2. Click **Create app**
3. Fill in any name/description
4. Set the **Redirect URI** to the URL where you'll host this (e.g. your Netlify URL)
5. Check **Web API** and save
6. Copy your **Client ID** from the app page

### 2. Host the files

This app uses OAuth and needs to be served over HTTPS — you can't just open `index.html` locally.

**Easiest option: Netlify Drop**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the entire `group-queue-filter` folder onto the page
3. Copy the URL Netlify gives you

Make sure that URL exactly matches your Redirect URI in Spotify (no trailing slash).

### 3. Add yourself as a user (Development Mode)

While your Spotify app is in Development Mode, only approved accounts can use it:

1. Go to your app in the Spotify Developer Dashboard
2. Click **Settings → User Management**
3. Add the Spotify email of anyone who will use this app (max 5 in dev mode)

### 4. Use it

1. Open your Netlify URL
2. Paste your **Client ID** and **Redirect URI** (your Netlify URL)
3. Click **Connect to Spotify** — approve the permissions
4. Your playlists appear — click one
5. Tap the people who are present tonight
6. Hit **Build Shuffled Queue** → **Play on Spotify Now**

## Notes

- Make sure Spotify is open and actively playing on your device before hitting Play
- The app reads who added each song directly from the playlist — no manual setup needed
- In Development Mode, max 5 Spotify accounts can be added as authorized users
- The access token expires after 1 hour — just reconnect if it stops working

# IPTV Web Player Pro

Web IPTV player based on the supplied `ir-iptv-playlist.m3u`.

## Features
- 184 channels from the supplied playlist
- 19 groups read from `group-title`
- Search
- Favorites stored in browser localStorage
- HLS playback via hls.js
- Previous/next channel
- Auto retry on fatal playback errors
- Fullscreen, volume, mute
- Keyboard controls: Arrow Up/Down and Space
- Railway-ready Dockerfile and health check

## Run
```bash
npm install
npm start
```
Open http://localhost:3000

## GitHub CLI
```bash
gh auth login
git init
git add .
git commit -m "Initial IPTV web player"
git branch -M main
gh repo create YOUR_USERNAME/iptv-web-player --public --source=. --remote=origin --push
```

## Railway
Create a Railway project from the GitHub repository. Railway detects the Dockerfile and uses `PORT` automatically.

## Important
The browser receives the stream URLs directly. The supplied playlist contains 184 HTTP/HTTPS HLS (`.m3u8`) URLs. Playback can still be blocked by the upstream server's CORS policy, geo/network restrictions, or a dead stream. A true VLC-like universal proxy/transcoding layer would require server-side FFmpeg/proxying and significantly more Railway bandwidth/CPU.

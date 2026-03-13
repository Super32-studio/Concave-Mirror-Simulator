# 🔬 Concave Mirror Lab — GitHub Pages Hosting Guide

## Files to upload to GitHub
```
concave_mirror_lab.html   ← main app (open on phone)
broadcaster.html          ← open on laptop to share webcam
```

---

## Step 1 — Create GitHub Repo

1. Go to https://github.com/new
2. Name it: `concave-mirror-lab`
3. Set to **Public**
4. Click **Create repository**

---

## Step 2 — Upload Files

1. Click **"uploading an existing file"** link
2. Drag both HTML files in
3. Click **Commit changes**

---

## Step 3 — Enable GitHub Pages

1. Go to repo **Settings** → **Pages** (left sidebar)
2. Under **Source** → select **Deploy from a branch**
3. Branch: **main** → folder: **/ (root)**
4. Click **Save**
5. Wait ~60 seconds → your site is live at:
   `https://YOUR_USERNAME.github.io/concave-mirror-lab/`

---

## Step 4 — How to Use Remote Webcam

### On your LAPTOP:
1. Open: `https://YOUR_USERNAME.github.io/concave-mirror-lab/broadcaster.html`
2. Click **START BROADCASTING**
3. Allow camera access
4. Note the **6-digit Room ID** shown on screen

### On your PHONE:
1. Open: `https://YOUR_USERNAME.github.io/concave-mirror-lab/concave_mirror_lab.html`
2. Go to **WEBCAM tab**
3. Tap **💻 LAPTOP WEBCAM (remote)**
4. Enter the **6-digit Room ID** from your laptop
5. Tap **CONNECT**
6. Your laptop webcam streams live to your phone! 🎉

---

## How it works
```
LAPTOP                         PHONE
  |                              |
  |---- webcam stream ---------->|
  |        via PeerJS            |
  |      (WebRTC p2p)            |
  |                              |
broadcaster.html         concave_mirror_lab.html
```

- **PeerJS** (free cloud) handles the connection handshake
- **WebRTC** does the actual video streaming peer-to-peer
- No data goes through any server after connection — direct laptop to phone
- Works from anywhere in the world as long as both have internet

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Error: peer-unavailable" | Laptop broadcaster not running, or wrong Room ID |
| No video on phone | Refresh broadcaster, get new Room ID, try again |
| Black screen | Click DISCONNECT, wait 5s, reconnect |
| Camera not starting on laptop | Allow camera in browser, try Chrome |

> **Important:** Both pages must be on HTTPS (GitHub Pages is HTTPS by default) for WebRTC to work.

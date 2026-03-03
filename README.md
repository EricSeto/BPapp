# BP Tracker PWA — Deployment Guide

## What You Have
A complete blood pressure tracking app with:
- **Camera capture** with on-device OCR (reads your Omron display automatically)
- **localStorage persistence** — data saves automatically, survives closing the app
- **Trend charts** with AHA reference lines
- **CSV export/import** for sharing with your care team
- **PWA support** — installs on your iPhone home screen as an app icon
- **Offline capable** — works without internet after first load

## Files
```
bp-pwa/
├── index.html      ← The complete app (single file)
├── manifest.json   ← PWA configuration
├── sw.js           ← Service worker (offline support)
├── icon-192.png    ← App icon (small)
└── icon-512.png    ← App icon (large)
```

## Deploy to Netlify (Free — 5 minutes)

### Step 1: Create a Netlify account
1. Go to **https://app.netlify.com**
2. Sign up with your email (free tier is all you need)

### Step 2: Deploy
1. Log in to Netlify
2. Look for **"Add new site"** → **"Deploy manually"**
3. **Drag and drop** the entire `bp-pwa` folder onto the upload zone
4. Wait 10-20 seconds — Netlify gives you a URL like `random-name-123.netlify.app`

### Step 3: (Optional) Custom site name
1. In Netlify, go to **Site settings** → **Change site name**
2. Choose something like `erics-bp-tracker` → URL becomes `erics-bp-tracker.netlify.app`

### Step 4: Add to iPhone Home Screen
1. Open **Safari** on your iPhone
2. Go to your Netlify URL (e.g., `erics-bp-tracker.netlify.app`)
3. Tap the **Share button** (square with arrow) at bottom of Safari
4. Scroll down and tap **"Add to Home Screen"**
5. Name it "BP Tracker" → Tap **Add**
6. A red heart icon appears on your home screen — tap it to launch full-screen

## Updating the App Later
1. Make changes to the files (or ask Claude to update them)
2. In Netlify: **Deploys** → **Drag & drop** the updated folder
3. The app updates automatically on your phone next time you open it

## Alternative: GitHub Pages (Also Free)
1. Create a GitHub account at github.com
2. Create a new repository (e.g., `bp-tracker`)
3. Upload all 5 files to the repository
4. Go to **Settings** → **Pages** → Source: **main branch** → Save
5. Your URL: `yourusername.github.io/bp-tracker`

## Data & Privacy
- All data is stored **locally on your device** in the browser's localStorage
- Nothing is sent to any server — the app is entirely client-side
- OCR processing happens **on your phone**, not in the cloud
- The Netlify hosting only serves the static files; it never sees your data

## Troubleshooting
- **OCR not detecting values?** Make sure the BP monitor screen is well-lit and in focus. The OCR works best with clear, high-contrast LCD displays. You can always correct values manually.
- **App not installing to home screen?** Must use Safari (not Chrome) on iPhone. The "Add to Home Screen" option only appears in Safari's share sheet.
- **Data disappeared?** If you clear Safari's website data, localStorage is wiped. Use CSV export regularly as a backup.

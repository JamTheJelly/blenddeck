# BlendDeck — installable app

BlendDeck runs as an installable web app (PWA) on Windows and Android. Once installed it has its own icon and window, and it works offline.

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The app |
| `manifest.webmanifest` | App name, icons and colors for installing |
| `sw.js` | Offline cache |
| `icons/` | App icons |

## 1. Put it online (free, one time)

Installing needs the files served over https. GitHub Pages is free:

1. Sign in at github.com and create a new **public** repository, for example `blenddeck`.
2. Click **Add file › Upload files** and drag in everything from this folder, including the `icons` folder. Commit.
3. Go to **Settings › Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute your app is live at `https://<your-username>.github.io/blenddeck/`.

## 2. Install it

**Windows (Chrome or Edge):** open your GitHub Pages link, then click the **Install** icon at the right end of the address bar.
- If you don't see the icon, use the menu instead. In Chrome: **⋮ › Cast, save and share › Install page as app**. In Edge: **… › Apps › Install this site as an app**.
- BlendDeck then appears in the Start menu, and you can pin it to the taskbar.

**Android (Chrome):** open the same link, then tap **⋮ › Install app** (on some phones it's called *Add to Home screen*). Chrome installs it as a real app: it shows up in your app drawer, opens without a browser bar, and works offline. On a phone it uses the mobile layout (challenges and stats).

## 3. Optional: an Android .apk file

If you want an actual .apk file (to sideload, or for the Play Store):

1. Go to pwabuilder.com and enter your GitHub Pages link.
2. Choose **Package for stores › Android** and download the package.
3. Copy the `.apk` to your phone and open it. Android will ask you to allow installs from that source.

No Android Studio is needed. The installable web app from step 2 already behaves like an app, so this step is only for people who specifically want an .apk.

## Your data

- Everything is saved **on each device**, in that browser's storage. The installed app on your PC and the one on your phone don't sync with each other, or with the claude.ai version.
- Use **Progress › Backup** to move data around. **Export backup** saves a `.json` file, and **Import backup** on another device (or in the claude.ai version) adds anything it doesn't already have. Nothing is overwritten.
- AI skill assessments, Claude's render feedback and the weekly challenge card only work in the claude.ai version. Your Sunday push notification still arrives either way.
- Render images are stored small (480 px) to fit in browser storage. That's roughly 150 renders. Export a backup now and then.

## Updating the app

1. Replace `index.html` in your GitHub repository with the new one.
2. Open `sw.js` and change `blenddeck-v1` to `blenddeck-v2` (then v3, and so on).
3. Commit. Installed copies pick up the update the next time they're opened while online.

## Quick test without hosting

Double-clicking `index.html` opens it in your browser, and challenges, guides and logging all work. It just won't install or cache offline until it's served over https.

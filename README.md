# MY-App-Drawers

My collection of small quality-of-life apps. Each app runs as a Claude artifact
on claude.ai; this repository keeps the source code as a backup and history.

## Apps

| App | What it does | Open it |
| --- | --- | --- |
| Tool Drawer | Home screen for all my apps, plus a shelf of ideas for the next ones | https://claude.ai/artifact/A92VzpAnvWpYDpC9RH5pdr |
| Hima Night Finder (暇) | Friends tap the nights they're free; it picks the best night and the fairest station to meet at | https://claude.ai/artifact/WS1vygPn35rgWtXZJbxpfV |
| Hima Night Finder, public web version | Same app for friends without a Claude account; runs on GitHub Pages with Firebase | https://elitefei1-gif.github.io/MY-App-Drawers/hima/ (after setup below) |

## Layout

```
apps/
  tool-drawer/index.html
  hima-night-finder/index.html
docs/                          ← served by GitHub Pages
  hima/index.html              ← public Hima (no Claude account needed)
  hima/firebase-config.js      ← paste Firebase settings here
  hima/firestore.rules         ← paste into Firebase → Firestore → Rules
```

## Notes

- The apps save data (plans, replies, drawer tiles) with Claude's built-in
  artifact storage. That only works when the page is opened on claude.ai.
  Opened from this repository or GitHub Pages, a page loads but can't save.
- The saved data itself lives on claude.ai, not in this repository.
- To add a new app: build it as an artifact, add its folder under `apps/`,
  add a row to the table above, and add a tile in Tool Drawer.

## Setting up public Hima (one time)

1. **Firebase project:** go to https://console.firebase.google.com, click
   *Create a project* (Google Analytics can be off).
2. **Database:** *Build → Firestore Database → Create database*, pick the
   `asia-northeast1 (Tokyo)` location, start in *production mode*.
3. **Rules:** open the *Rules* tab, replace everything with the contents of
   `docs/hima/firestore.rules`, click *Publish*.
4. **Web app settings:** *Project settings (gear) → Your apps → Web (</>)*,
   register an app (no hosting), and copy the `firebaseConfig` values into
   `docs/hima/firebase-config.js`.
5. **GitHub Pages:** in this repository, *Settings → Pages*, source
   *Deploy from a branch*, branch `main`, folder `/docs`, *Save*.
6. Open https://elitefei1-gif.github.io/MY-App-Drawers/hima/ and start a plan.

Anyone with a plan's link can view and reply, and nobody can browse the list
of plans. People's answers are tied to their browser, so clearing browser data
or switching phones starts a fresh row.

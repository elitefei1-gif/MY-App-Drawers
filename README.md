# MY-App-Drawers

My collection of small quality-of-life apps. Each app runs as a Claude artifact
on claude.ai; this repository keeps the source code as a backup and history.

## Apps

| App | What it does | Open it |
| --- | --- | --- |
| Tool Drawer | Home screen for all my apps, plus a shelf of ideas for the next ones | https://claude.ai/artifact/A92VzpAnvWpYDpC9RH5pdr |
| Hima Night Finder (暇) | Friends tap the nights they're free; it picks the best night and the fairest station to meet at | https://claude.ai/artifact/WS1vygPn35rgWtXZJbxpfV |

## Layout

```
apps/
  tool-drawer/index.html
  hima-night-finder/index.html
```

## Notes

- The apps save data (plans, replies, drawer tiles) with Claude's built-in
  artifact storage. That only works when the page is opened on claude.ai.
  Opened from this repository or GitHub Pages, a page loads but can't save.
- The saved data itself lives on claude.ai, not in this repository.
- To add a new app: build it as an artifact, add its folder under `apps/`,
  add a row to the table above, and add a tile in Tool Drawer.

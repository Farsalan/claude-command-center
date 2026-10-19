# Command Center

Personal productivity stack dashboard — Todoist, Notion, Google Calendar, Whimsical, Obsidian, and Fold, orchestrated by Claude.

Public snapshot of connection health. The interactive, truly-live version lives on claude.ai; this page is the public, bookmarkable view.

## How to deploy on GitHub Pages

1. Create a new repo on GitHub, e.g. `command-center`.
2. Upload the three files in this folder: `index.html`, `status.json`, `README.md`.
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", pick **Deploy from a branch**, select `main` branch, root folder, and save.
5. Wait ~1 minute. Your site will be live at `https://<your-username>.github.io/command-center/`.

## How the status stays fresh

A Claude scheduled task runs daily at 07:48 IST. It checks each connection and writes an updated `status.json` here (via a GitHub token). The dashboard reads `status.json` on each load and colors the nodes accordingly:

- Green ring = responded OK on the last check
- Red ring = failed on the last check
- Grey = no data yet (first run hasn't happened)

To enable the daily commit, Claude needs:
- Your GitHub username
- The repo name
- A fine-grained personal access token with write access to this one repo

Share those with Claude in a chat and the scheduled task will be updated.

## Files

- `index.html` — the dashboard (one file, no build step, no dependencies)
- `status.json` — the data the dashboard reads; overwritten daily by the scheduled task
- `README.md` — this file

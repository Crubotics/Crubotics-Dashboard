# Crubotics Team Dashboard

A shared project-management dashboard for the Crubotics robotics program, covering both the **Ranger** and **Navigator** teams — calendar, roles, tasks, attendance, inventory/budget, docs, and announcements.

**Live site:** https://crubotics.github.io/Crubotics-Dashboard/

## How it works

This is a single static `index.html` file (no build step, no frameworks) hosted for free on GitHub Pages. All shared data — events, roles, tasks, docs, announcements, attendance, and inventory — is stored in a Google Sheet and read/written through a small Google Apps Script Web App that acts as the backend.

```
Browser (this site)  →  fetch()  →  Google Apps Script Web App  →  Google Sheet
```

There's no login system. Anyone with the site link can view and edit team data — a Captain Mode PIN (set on first use, in the dashboard itself) locks down deleting items, but it isn't real authentication. Don't put sensitive personal information into it.

## Repo contents

| File | Purpose |
|---|---|
| `index.html` | The entire dashboard — markup, styles, and JavaScript in one file |

## Making changes

**If you're changing the dashboard itself** (this file): edit `index.html` directly on GitHub (pencil icon) or upload a replacement, commit, and GitHub Pages redeploys automatically within a couple of minutes.

⚠️ **Important:** near the top of the `<script>` section is:

```js
const SHEETS_API_URL = 'https://script.google.com/macros/s/.../exec';
```

This must always point to the team's deployed Apps Script Web App. If a new copy of this file ever shows a "Setup needed" message on load, this is the line to fix.

**If you're changing the backend** (how data is read/written): that code lives in the Google Sheet, not this repo — see **Extensions → Apps Script** in the Sheet, or the maintenance reference doc kept alongside it in Drive.

## Embedding elsewhere

The dashboard is designed to be embedded via iframe, e.g. in Schoology:

```html
<iframe src="https://crubotics.github.io/Crubotics-Dashboard/" width="100%" height="1800" style="border:none;"></iframe>
```

Adjust `height` as needed for the embedding page.

## Maintainers

Crubotics coaching staff. See the "Crubotics Dashboard – Maintenance Reference" document in the team Google Drive for full update instructions (Apps Script redeploys, GitHub file updates, etc.).

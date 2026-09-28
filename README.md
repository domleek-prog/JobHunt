# Job Hunt — Application Tracker

A fast, focused job application tracker in a single HTML file. No frameworks, no build step, no server. Open it in a browser and start tracking.

## Features

- **Position, company and status** for each application. The date applied is recorded automatically but kept out of the way.
- **Six colour-coded statuses:** Applied – Awaiting Response, Response Received, 2 Weeks – No Response, Interview Set, Offer Received and Rejected.
- **Auto-flag.** Anything still "Applied – Awaiting Response" 14 days after it was added moves to "2 Weeks – No Response" when the page loads.
- **Summary strip** with a count per status. Click a count to filter the list, and click it again to clear the filter.
- **Quick status changes.** Click a status pill to pick a new status from a dropdown.
- **Delete with confirmation**, shown inline on the row.
- **Newest first.** Rejected applications are dimmed so active ones stand out.
- **Export and import JSON** from the `⋯` menu, for backups or moving between browsers.
- **Responsive**, with a dark theme that works on desktop and phone.
- **Keyboard shortcuts:** `N` adds an application and `Esc` closes menus and dialogs.

## Usage

Open `index.html` in any modern browser, or use the hosted version.

### Deploying to Netlify

The repo is ready for Netlify, with no build step:

1. In Netlify, choose **Add new site → Import an existing project → GitHub** and pick this repo.
2. Keep the settings from `netlify.toml`: no build command, publish directory `.`.
3. Deploy. Each push to `main` redeploys automatically.

## Your data

Applications are saved in your browser's `localStorage`:

- Nothing is sent to a server.
- Data belongs to that browser on that device. A different browser, a private window or clearing site data starts empty.
- **Export regularly** from the `⋯` menu to keep a backup.

Importing a file **replaces** your current list after a confirmation prompt.

### Export format

```json
{
  "app": "job-tracker",
  "version": 1,
  "exportedAt": "2026-09-28T10:00:00.000Z",
  "applications": [
    {
      "id": "…",
      "position": "Product Designer",
      "company": "Acme Ltd",
      "status": "interview",
      "dateApplied": "2026-09-20T09:30:00.000Z"
    }
  ]
}
```

Valid `status` values: `applied`, `response`, `twoweeks`, `interview`, `offer`, `rejected`. Import also accepts a bare array of applications and full status labels such as `"Interview Set"`.

## Tech

One file of plain HTML, CSS and JavaScript. It uses [Inter](https://rsms.me/inter/) from Google Fonts and falls back to system fonts.

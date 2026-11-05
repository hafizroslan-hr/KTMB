# KTMB
KTMB Schedule

## Seremban Line Timetable

[`seremban-timetable/`](seremban-timetable/) is a departure-board style timetable for the KTM Komuter Seremban Line (Batu Caves ↔ Pulau Sebang): pick two stations to see the next train, the full day's departures, every stop, and a live on-board tracker.

- `index.html` is the page itself, exported from the claude.ai artifact.
- `data/timetable.json` is a snapshot of the timetable data (weekday from 27 Apr 2026 and 10 Nov 2026, weekend from 14 Nov 2026), exported 5 Nov 2026.

When the page runs on claude.ai it reads the live database, and editors can upload new KTM PDFs at `#admin`. Anywhere else, it loads `data/timetable.json` instead.

### Updating the timetable from this repo copy

1. Open the page and go to **Manage timetables** (`#admin`).
2. Upload the new KTM timetable PDF, check the preview, and save it. You can also make revisions live, delete them, and compare them.
3. Changes are saved **in your browser only** until you click **Export timetable.json**.
4. Replace `seremban-timetable/data/timetable.json` in the repo with the downloaded file and commit. Everyone then sees the update.

Visitors who upload a PDF only change their own browser's copy; the published timetable changes only when a new `timetable.json` is committed. To preview locally, serve the folder over HTTP (e.g. `python3 -m http.server` inside `seremban-timetable/`), because browsers block `fetch` from `file://`. To publish, enable GitHub Pages on this repo.

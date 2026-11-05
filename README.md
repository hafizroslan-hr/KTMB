# KTMB
KTMB Schedule

## Seremban Line Timetable

[`seremban-timetable/`](seremban-timetable/) is a departure-board style timetable for the KTM Komuter Seremban Line (Batu Caves ↔ Pulau Sebang): pick two stations to see the next train, the full day's departures, every stop, and a live on-board tracker.

- `index.html` is the page itself, exported from the claude.ai artifact.
- `data/timetable.json` is a snapshot of the timetable data (weekday from 27 Apr 2026 and 10 Nov 2026, weekend from 14 Nov 2026), exported 5 Nov 2026.

When the page runs on claude.ai it reads the live database, and editors can upload new KTM PDFs at `#admin`. Anywhere else, it loads `data/timetable.json` instead and the admin view is off. To preview locally, serve the folder over HTTP (e.g. `python3 -m http.server` inside `seremban-timetable/`), because browsers block `fetch` from `file://`. To publish, enable GitHub Pages on this repo.

To update the snapshot, edit `live` in `data/timetable.json` to point each service (`weekday`/`weekend`) at a revision `_id`, or add new revisions in the same format.

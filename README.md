# Equifest 2026 Planner

A mobile-first planner for the Equifest timetable (16–18 October 2026, Claudelands, Hamilton).
Plain HTML, CSS and JavaScript. No build step, no dependencies.

## Deploy on Render (free)

1. Put these files in the root of a new GitHub (or GitLab) repo.
2. In Render: **New > Static Site**, then pick the repo.
3. Leave **Build Command** empty and set **Publish Directory** to `.`
   (the included `render.yaml` sets the same thing if you use a Blueprint).
4. Click **Create Static Site**. Share the `*.onrender.com` link.

On each phone, open the link once with good reception, then use
**Share > Add to Home Screen**. The planner caches itself, so it still opens when
reception is patchy at the showgrounds.

## Updating times

All sessions live in `events.js`. Each one looks like:

    {"id":"fri-0-0845","day":"fri","start":"08:45","end":"09:45",
     "arena":"Omega Plus Arena","cat":"education","title":"...","who":"..."}

Edit the `start` or `end` (24-hour `HH:MM`), commit, and Render redeploys in a minute.
Sessions of 4 hours or more are marked `"dropin":true` and are ignored by the clash checker.
Keep `id` values unchanged so people's saved picks still match.

## Notes

- Data was transcribed from the official A1 timetable PDF. The organisers note that sessions are subject to change.
- Picks are saved on the device (localStorage). "Share plans" makes a link that loads both plans on another phone.
- Night show end times are not published, so calendar entries for them default to 2 hours.

# Laie Project Gantt Chart

## What This Is
A living Gantt chart for the Laie CLIMB Works opening readiness project. The site is deployed via GitHub Pages and auto-updates when changes are pushed to `main`.

## How to Update
All task data lives in `data.json`. To make changes, edit that file. The HTML reads it at load time.

### Common update patterns:

**Mark a task complete:**
Find the task in `data.json`, set `"status": "Complete"` and `"pctDone": 100`.

**Mark a task in progress:**
Set `"status": "In Progress"` and update `"pctDone"` to the current percentage (0-100).

**Add delay days:**
Set `"status": "Delayed"` (or `"Weather Hold"`), and set `"delayDays"` to the number of working days lost.

**Change dates:**
Update `"start"` and `"end"` fields (format: `YYYY-MM-DD`).

**Add a note:**
Set the `"notes"` field to any free text.

**Add a new task:**
Add a new object to the appropriate section's `tasks` array following the same format.

### Valid status values:
- `Pending` — not started
- `In Progress` — underway
- `Complete` — done
- `Delayed` — delayed (non-weather)
- `Weather Hold` — delayed due to weather

## After Making Changes
Commit and push to `main`. GitHub Pages will auto-deploy.

```
git add data.json
git commit -m "Update task status"
git push
```

## File Structure
- `index.html` — self-contained web app (HTML + CSS + JS, no build step)
- `data.json` — all task data (this is what you edit)
- `CLAUDE.md` — this file

# Switch log (job tracker)

A single-page learning hub and job-search tracker hosted on GitHub Pages at https://USERNAME.github.io/job-tracker/.

## How it's built
- The app is in `index.html`: HTML, CSS in one `<style>` block, vanilla JavaScript in one `<script>` block. No build step, no frameworks, no npm. Keep it that way.
- Curriculum content (tracks and topics; later problems, cases and prompts) is public and lives in `data/curriculum.json`, which the page loads with `fetch()`. It is edited on GitHub, so it must stay plain, valid JSON.
- Personal data (progress, notes, applications, logs) lives only in the browser's localStorage under the key `switch-log-v1` and never goes in the repo. The shape is `{version, owner, targets, plan, apps, prep, reviews, companies, learn}`.
- `learn` maps a topic id to `{status: 'learning'|'done', notes, updated, doneOn}`; no entry means not started.
- Planned work is in `BACKLOG.md`. Tick an item off when it ships.

## Data rules
- Never rename the storage key or remove fields without a migration in `merge()`; changing them would silently wipe the user's data.
- When the shape of the stored data changes: bump `SCHEMA`, note the new version in the comment above it, give new fields a default in `DEFAULTS`, and handle them in `merge()`, which is also where older shapes get migrated. A field missing from `merge()` is dropped on the next load.
- Export writes the whole state, so new fields are backed up automatically. Import must keep accepting every older backup.
- `merge()` keeps top-level fields it doesn't know, and the page never saves over data with a newer `version` than its own. Keep both: they stop a stale tab or an old cached copy from wiping newer data.
- Topic ids in `data/curriculum.json` are permanent, because progress and notes are keyed by them. Change titles freely; never change or reuse an id. Never delete progress for an id that the curriculum no longer lists.
- Every localStorage read and write is wrapped in try/catch. Keep that.
- Escape every user-entered string with `esc()` before putting it into HTML. Curriculum text counts as user-entered.

## Design rules
- Colours are CSS variables on `:root`, redefined for dark mode. Use the variables; no new hard-coded colours.
- Fonts: Spectral for headings and big numbers, Atkinson Hyperlegible for everything else.
- Yellow (`--hl`) means only "gap to close": NeetCode problems behind pace, and Learn topics whose week is over but aren't done. Don't use it for anything else.
- Sentence case everywhere. No all-caps labels, no arrows in button or link text.
- Must work at 390px wide with no horizontal scroll, and with keyboard only.

## Checking a change
- Serve the folder rather than opening the file: run `python3 -m http.server` in the repo and open http://localhost:8000. Browsers block `fetch()` from a page opened as a file, so the Learn tab can't load the curriculum that way (the other tabs still work).
- Test with an exported backup imported from Settings and backup, so real data still loads after the change.
- Never commit a backup JSON file: the repo is public and backups contain personal job-search data. `.gitignore` ignores JSON and CSV files at the repo root, but it doesn't stop files added through GitHub's "Upload files".

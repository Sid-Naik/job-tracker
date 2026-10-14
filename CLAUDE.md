# Switch log (job tracker)

A single-page job-search tracker hosted on GitHub Pages at https://USERNAME.github.io/job-tracker/.

## How it's built
- Everything is in `index.html`: HTML, CSS in one `<style>` block, vanilla JavaScript in one `<script>` block. No build step, no frameworks, no npm. Keep it that way.
- Data lives in the browser's localStorage under the key `switch-log-v1`. The shape is `{owner, targets, plan, apps, prep, reviews, companies}`; `merge()` fills in defaults for older backups.
- Never rename the storage key or remove fields without a migration in `merge()`; changing them would silently wipe the user's data.
- Every localStorage read and write is wrapped in try/catch. Keep that.
- Escape every user-entered string with `esc()` before putting it into HTML.

## Design rules
- Colours are CSS variables on `:root`, redefined for dark mode. Use the variables; no new hard-coded colours.
- Fonts: Spectral for headings and big numbers, Atkinson Hyperlegible for everything else.
- Yellow (`--hl`) means only "gap to close". Don't use it for anything else.
- Sentence case everywhere. No all-caps labels, no arrows in button text.
- Must work at 390px wide with no horizontal scroll, and with keyboard only.

## Checking a change
- Open `index.html` directly in a browser; there is no server.
- Test with an exported backup imported from Settings and backup, so real data still loads after the change.
- Never commit a backup JSON file: the repo is public and backups contain personal job-search data.

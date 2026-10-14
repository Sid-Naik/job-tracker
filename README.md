# Switch log

A single-page tracker for my job switch: daily prep sessions, the NeetCode 150, applications from wishlist to offer, target companies and a weekly review.

## Put it live on GitHub Pages

1. Create a **public** repository named `job-tracker`.
2. Upload `index.html` and this `README.md` (Add file → Upload files → Commit).
3. Go to **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute, open `https://<your-username>.github.io/job-tracker/` and bookmark it.

## Where the data lives

Everything you enter is saved in your browser's local storage on that device. Nothing is sent anywhere, so the public repo only exposes the code.

- **Back up every Sunday:** Settings and backup → Export backup (JSON). Keep the file in Google Drive or a private repo.
- **Move to another device:** export on the old one, then Import backup on the new one.
- Clearing site data or using a private window starts empty.

## Daily use

- **Prep log:** log each block — area, hours and a count (problems solved, topics finished, cases practised, mocks done, referral messages sent). Coding counts feed the NeetCode grid.
- **Applications:** add every application; update the status as it moves. The dashboard's "Chase these" lists anything applied more than 10 days ago with no update.
- **Companies:** build the 40-company target list, then use "Track application" to start an application from it.
- **Weekly review:** on Sunday, the page fills in the week's numbers; write what slipped and next week's top three, then save.
- **Settings:** weekly targets and plan dates are editable if the plan changes.

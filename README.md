# Time Management Videos (Auto-updating, ₹0)
Free static site on GitHub Pages that pulls YouTube RSS from approved channels (TEDx, universities, IITs, AIIMS, B‑Schools, authors) and lists kid-friendly time-management videos.

## Quick Start
1. **Create a new repo** and upload this folder.
2. In `scripts/fetch.mjs`, add more channel IDs to `CHANNELS` (keep a short `source` label).
3. Push to GitHub. Go to **Settings → Pages** → Source: *Deploy from a branch* → `main` → `/ (root)`.
4. Check **Actions** tab: the workflow `Update videos.json` will run every 3 hours (or run manually via *Run workflow*).
5. Your site: `https://<username>.github.io/<repo>/`

### How to find a Channel ID
- Open channel page → Right-click → **View page source** → search for `channelId` (starts with `UC`).

### Filters & Search
- Click chips (TEDx, Harvard, IIT…) to filter by `source`.
- Use the search box to match titles (e.g., "Pomodoro", "habit").
- Clicking the **title** opens the video on YouTube.

### Notes
- RSS does not include duration; we filter by *keywords only*. If you want a ≤20 min rule, we can add a free YouTube Data API step later.
- `videos.json` is appended and trimmed to the 400 newest items.

### Customize Look
- Fonts: Oswald (titles), Montserrat (headings), Poppins (body).
- Brand color: change `--teal` in `index.html`.

# My Watchlist 2.0

A local-first personal tracker for movies, anime and web series, with a clean multi-page layout and a compact navigation drawer.

## What's included
- **Dashboard:** library summary, quick stats, continue-watching shortcuts and recent additions.
- **My Library:** add, edit, delete, search, filter, sort, favourite and rate titles.
- **Continue Watching:** track season, episode and total episode progress, with one-tap progress updates.
- **Discover:** search TMDB, browse weekly trending titles and add metadata/posters/synopses to your library.
- **Recommendations:** suggestions based on favourited or highly rated TMDB titles.
- **Movie Journal:** dated watch entries with a rating, personal reflection and favourite scene/detail.
- **Collections:** create named lists and group titles into them.
- **Personal Insights:** genre breakdown, ratings, counts and estimated watch time.
- **Settings:** JSON backup and TMDB token management.
- Installable PWA shell with offline app files.

## Upgrade without losing your existing library
The app deliberately retains the original browser storage key `my-watchlist-v1` and the TMDB token key `my-watchlist-tmdb-token`. Replace the old project files with these updated files on the **same GitHub Pages URL and browser**. Your existing titles, posters and saved TMDB token should remain available. The new collections and journal use separate storage keys.

Before upgrading, export a JSON backup from the old version. Keep that backup somewhere safe.

## Run locally
Open `index.html` for a quick test. For service-worker/PWA testing, serve the folder over localhost or HTTPS. Example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Publish on GitHub Pages
1. Upload all project files to the repository root.
2. In **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/(root)`.
3. Open the published HTTPS URL. On Android Chrome, use **Install app** or **Add to Home screen**.

## TMDB connection and token safety
Discover, trending and recommendations use the TMDB API. The app reads the existing token from browser localStorage using `my-watchlist-tmdb-token`.

- If your previous app already had the token saved in this browser, the upgraded app reuses it automatically.
- Otherwise open **Settings → Manage token** (or Discover) and paste your TMDB **API Read Access Token** once. It is stored in this browser only.
- The token is intentionally **not embedded in the HTML, JavaScript, ZIP or GitHub repository**. A token hard-coded into a public static site can be read by anyone inspecting the source. The token is not a secret-safe credential when used in a browser.
- TMDB search/discovery requires an internet connection. Library records remain local.

This product uses the TMDB API but is not endorsed or certified by TMDB. See https://www.themoviedb.org/documentation/api/terms-of-use.

## Data and privacy
Titles, notes, journal entries, collections and uploaded posters are stored in this browser's localStorage. There is no account or cloud sync. Data does not automatically transfer between devices or browsers. Export backups regularly. Browser localStorage is not encrypted, so do not store sensitive information here.

## Notes about insights
Estimated watch time is an approximation: two hours per movie and 24 minutes per watched episode. It is not measured playback time.

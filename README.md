# My Watchlist

A cinematic, local-first entertainment tracker for movies, anime and web series.

## Features
- Add, edit, inspect and delete titles
- Movie, Anime and Web Series categories
- Yet to Watch, Currently Watching, Pending, Completed and Dropped statuses
- Poster image upload stored in this browser
- Personal rating, genre, priority, synopsis and review
- Season/episode progress and percentage bar
- Search, filters, sorting and favourites
- Library statistics and JSON backup export/import
- Installable PWA shell with offline caching

## Run
Open `index.html` for a quick test. For installation/offline caching, serve over localhost or HTTPS. For example: `python -m http.server 8000`, then open `http://localhost:8000`.

## Install on Android
Host this folder on an HTTPS static host (GitHub Pages, Netlify, etc.), open the URL in Chrome, then choose **Install app** or **Add to Home screen**.

## Local storage and privacy
All entries and poster images are stored in this browser's localStorage. There is no account, cloud sync, analytics or server upload. Export backups regularly. Clearing browser data, changing browsers or devices can erase the library. This is not encrypted storage, so do not put sensitive information in it.

## Limitations
No automatic movie metadata lookup; poster images are added by you. Episode progress is a simple title-level counter, not a detailed per-episode calendar. Google fonts are not required for core functionality; visual styling uses system fallback if offline.

## TMDB title search
The app can search TMDB for movie and TV titles and import the title, poster URL, release year, synopsis and genre names.
1. Create a free TMDB account and open https://www.themoviedb.org/settings/api.
2. Request API access and copy the **API Read Access Token** (the long Bearer token, not the short API key).
3. In My Watchlist choose **Search titles**, paste the token and select **Save token**.
4. Search for a title and press **Add** on the result. TV results are added as Web Series by default; edit the title to change the type to Anime if appropriate.
5. The token is saved in this browser's localStorage and is not included in the GitHub files. You can remove it by clearing the token field and saving/removing it in the search dialog.

TMDB search requires an internet connection. TMDB metadata and poster images are fetched directly from TMDB. Review TMDB's attribution and API terms before public distribution. This is an unofficial project and is not endorsed by TMDB.

# CineScope — React Movie & TV Explorer

A standalone React + Vite discovery website inspired by familiar movie catalogue and streaming interfaces, with its own name, layout, styling and interaction patterns. It uses the live TMDB API for movies, TV shows, trending titles, cast, recommendations and popular people.

## Pages and routes
- `/` Home: trending titles, top-rated movies and popular TV.
- `/movies` Movie catalogue with popularity/rating/now-playing/upcoming selections and genre filter.
- `/tv` TV catalogue.
- `/movie/:id` and `/tv/:id` Detail pages with overview, cast, recommendations and watchlist action.
- `/search?q=...` Multi-search for titles.
- `/people` Popular actors and creatives.
- `/genres` Genre discovery.
- `/watchlist` Locally saved titles (localStorage).

## Run in VS Code
1. Install Node.js (LTS).
2. Extract the ZIP and open the `cinescope` folder in VS Code.
3. Open Terminal > New Terminal.
4. Run `npm install` then `npm run dev`.
5. Open the localhost URL printed by Vite.

## Connect the free TMDB API
TMDB provides a free developer API for non-commercial projects, subject to its terms and attribution requirements. Create/sign in to a TMDB account, open account Settings > API, request a developer API credential, and copy the **API Read Access Token**.

1. Copy `.env.example` and rename the copy to `.env`.
2. Set `VITE_TMDB_TOKEN=your_actual_read_access_token`.
3. Stop and restart the dev server (`Ctrl+C`, then `npm run dev`).

Do not publish your token in a public repository. For a public deployment, proxy API calls through a backend rather than exposing credentials in browser code. See https://developer.themoviedb.org/docs/getting-started and https://developer.themoviedb.org/docs/faq.

The app shows a clear setup message until a token is configured. No movie data is fabricated as live API data.

## Attribution
This product uses the TMDB API but is not endorsed or certified by TMDB. TMDB data/images are used subject to TMDB's terms. This project is for educational/non-commercial use.


## Admin studio

Open `/admin` from the top navigation to manage a local CineScope editorial collection. You can create, edit, update, and delete custom movie or TV entries. These entries are saved in the current browser's `localStorage` and appear in the **Editor's picks** section on the homepage.

**Important:** this is a frontend-only academic demo. The admin page does not change TMDB's catalogue and localStorage is not secure authentication or a shared database. For a real production admin system, add a backend, database, and server-side authentication/authorization.


## Admin dashboard demo

Open `/admin` to reach the administrator sign-in page. Demo credentials:

- Username: `admin`
- Password: `CineScope2026!`

After signing in, the dashboard shows total curated content, movie count, TV show count, and the five most recently added entries. It also includes the existing add, edit, update, and delete content tools.

**Security note:** this is a frontend-only academic demonstration. The sign-in flag and content are stored in browser `localStorage`; the demo credentials are visible in the client code and do not provide real security. A production admin area needs server-side authentication, authorization, and a database. The admin-managed entries are separate from TMDB's catalogue and do not modify TMDB records.

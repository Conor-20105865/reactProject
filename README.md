# Movie Explorer App

A React-based movie discovery application powered by The Movie Database (TMDB) API.

The application allows users to browse movies, search for films and people, explore actor filmographies, manage favourites, write reviews, and organise movies into custom playlists.

## Features

### Movie Discovery

- Browse popular movies
- Explore top-rated movies
- Discover movies by genre and filtering options
- View detailed movie information
- Explore movie recommendations
- Read movie reviews retrieved from TMDB

### Search

- Search for movies, actors, and other people
- View movie and person results separately
- Navigate through paginated search results
- Open actor profiles and movie details

### Favourites

- Add movies to a favourites list
- Remove movies from favourites
- View favourite movies on a dedicated page

### Movie Reviews

- Write personal movie reviews
- View reviews associated with movies
- Access dedicated review pages

### Custom Playlists

- Create named movie playlists
- Add movies to playlists
- Remove movies from playlists
- Delete playlists
- Browse playlists using tabs

### Actor Information

- View actor biographies
- View birth dates and birthplaces where available
- Explore actor filmographies
- Browse movies associated with individual actors

## Technology Stack

| Technology | Purpose |
|------------|---------|
| React 19 | Frontend development |
| JavaScript | Application logic |
| Vite 7 | Development server and production builds |
| Material UI 7 | Interface components |
| React Router 7 | Client-side navigation |
| TanStack React Query 5 | API data fetching and caching |
| React Context API | Favourites, reviews and playlist state |
| React Hook Form | Form management |
| Lodash | Search input debouncing |
| TMDB API | Movie and actor information |

## Requirements

Before running the application, install:

- Node.js compatible with Vite 7
- npm
- A TMDB API key
- A modern web browser

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Conor-20105865/reactProject.git
cd reactProject
```

### 2. Install dependencies

```bash
npm ci
```

### 3. Configure the TMDB API

Create a `.env` file in the project root.

You can copy the provided `.env.example` file.

```bash
cp .env.example .env
```

On Windows, you can copy the file manually or use:

```powershell
Copy-Item .env.example .env
```

Open `.env` and add your TMDB v3 API key:

```dotenv
VITE_TMDB_KEY=your_tmdb_api_key_here
```

You can obtain API credentials from:

https://www.themoviedb.org/settings/api

The `.env` file is excluded from Git tracking.

Security note: Vite variables prefixed with `VITE_` are included in browser-side code. The TMDB API key used by this application must not be treated as a private server-side secret.

### 4. Start the development server

```bash
npm run dev
```

Open the local address displayed by Vite in your terminal.

## Available Commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Start the development server |
| `npm run build` | Generate a production build |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint checks |

## Application Routes

| Route | Purpose |
|-------|---------|
| `/` | Browse movies |
| `/movies/top-rated` | View top-rated movies |
| `/movies/favorites` | View favourite movies |
| `/movies/playlists` | Browse custom playlists |
| `/movies/:id` | View movie details |
| `/actors/:id` | View actor details |
| `/search` | Search movies and people |
| `/reviews/:id` | View a movie review page |
| `/reviews/form` | Add a movie review |

Unknown routes redirect to the home page.

## Project Structure

```text
reactProject/
├── public/
├── src/
│   ├── api/
│   │   └── tmdb-api.jsx
│   ├── components/
│   │   ├── cardIcons/
│   │   ├── castList/
│   │   ├── filterMoviesCard/
│   │   ├── movieCard/
│   │   ├── movieDetails/
│   │   ├── movieList/
│   │   ├── movieReview/
│   │   ├── movieReviews/
│   │   ├── pagination/
│   │   ├── reviewForm/
│   │   └── siteHeader/
│   ├── contexts/
│   │   └── moviesContext.jsx
│   ├── hooks/
│   ├── images/
│   ├── pages/
│   └── main.jsx
├── .env.example
├── .gitignore
├── package.json
├── package-lock.json
└── vite.config.js
```

## Application State

The application uses React Context to manage:

- Favourite movie IDs
- Personal reviews
- Custom playlists
- The currently selected playlist

These values are currently held in React application state.

They are not permanently saved to a database or browser storage, so refreshing or restarting the application may reset them.

TMDB data is fetched using TanStack React Query.

## API Integration

Movie and actor information comes from TMDB.

The application supports requests for:

- Popular movies
- Top-rated movies
- Upcoming movies
- Movie discovery and search
- Movie details
- Movie images
- Movie recommendations
- Movie reviews
- Genre information
- Actor details and filmographies

API requests are implemented in:

`src/api/tmdb-api.jsx`

## Known Limitations

- Favourites, playlists, and personal reviews are not persistently stored.
- A TMDB API key is required to retrieve data.
- The application depends on TMDB availability and API limits.
- API credentials used in browser-side requests are visible to clients.
- Some features may require additional error handling and validation.
- Automated application tests are not currently configured in the npm scripts.

## Potential Improvements

- Add persistent storage for favourites and playlists
- Support user accounts and authentication
- Save reviews to a backend database
- Add automated frontend tests
- Improve loading and error states
- Expand accessibility support
- Improve mobile responsiveness
- Add deployment documentation

## Acknowledgements

This project uses the TMDB API for movie and television metadata.

Movie information, posters, and related assets are provided by The Movie Database.

This project is not endorsed or certified by TMDB.

TMDB: https://www.themoviedb.org/

## Project Purpose

Movie Explorer was developed as a React application for practising component-based development, API integration, routing, state management, asynchronous data fetching, and interactive frontend design.

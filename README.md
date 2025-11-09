# Movies Frontend

A React single-page application for browsing movies, watching trailers, and contributing reviews. The app consumes a REST API to fetch movie metadata and allows visitors to submit their own feedback for each title.

## Backend Repository

The Backend for this project is available at: [Movies Backend](https://github.com/MarkOmelyanenko/movies-backend)

## Features

- **Movie carousel** powered by `react-material-ui-carousel` that highlights featured titles with backdrop art, posters, genres, and quick actions
- **Trailer playback** using `react-player` with deep links to YouTube videos
- **Review workflow** that retrieves existing reviews from the API and posts new reviews through an inline form
- **Responsive layout** built with Bootstrap, Material UI, and custom CSS so it works well on desktop and mobile devices

## Tech stack

- [React 18](https://react.dev/) with React Router for client-side routing
- [Bootstrap 5](https://getbootstrap.com/) & [React Bootstrap](https://react-bootstrap.netlify.app/) for layout components
- [Material UI](https://mui.com/) for the carousel container
- [Axios](https://axios-http.com/) for API communication

## Project structure

```
src/
├── API/axiosConfig.js       # Axios instance with the backend base URL
├── App.js                   # Top-level routes and data fetching
├── components/
│   ├── header/Header.js     # Navigation bar
│   ├── hero/Hero.js         # Movie carousel UI
│   ├── home/Home.js         # Home route wrapper
│   ├── reviews/Reviews.js   # Reviews route + review submission logic
│   ├── reviewForm/ReviewForm.js
│   └── trailer/Trailer.js   # Trailer playback route
└── index.js                 # React entry point & router setup
```

## Prerequisites

- Node.js 18+ and npm 9+
- A running Movies API backend. The frontend expects REST endpoints such as:
  - `GET /api/v1/movies`
  - `GET /api/v1/movies/:movieId`
  - `POST /api/v1/reviews`

## Configuration

The Axios client is configured in [`src/API/axiosConfig.js`](src/API/axiosConfig.js) with a default base URL of `http://localhost:8080/`. Update this value to match your backend host. If you prefer environment-based configuration, replace the literal string with `process.env.REACT_APP_API_BASE_URL` and define it in a `.env` file.

## Getting started

1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the development server:
   ```bash
   npm start
   ```
   The app runs on [http://localhost:3000](http://localhost:3000) and automatically reloads on code changes.
3. Build the production bundle:
   ```bash
   npm run build
   ```

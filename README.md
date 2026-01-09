# Klimate

**A simple weather web app that shows weather for your current location.**

> A lightweight React + TypeScript weather app (Vite) built with TanStack Query, shadcn/ui, Recharts and TailwindCSS. It detects your location (via the browser Geolocation API) and fetches current weather + basic forecast data from a weather API.

---

## Features

* Detects user location (latitude/longitude) using the browser Geolocation API
* Fetches current weather information and a short forecast for the detected location
* Clean responsive UI built with shadcn/ui + Tailwind CSS
* Data fetching, caching and background updates with TanStack Query
* Interactive weather charts using Recharts
* Built with TypeScript for safer, self-documenting code

---

## Tech stack

* React + TypeScript
* Vite (build tool)
* TanStack Query (data fetching & caching)
* shadcn/ui (component primitives)
* Recharts (charts)
* Tailwind CSS (styling)

---

## Requirements

* Node.js (v16+ recommended)
* npm or yarn
* A weather API key (e.g. OpenWeatherMap, WeatherAPI, or similar). Place this key in an environment variable as described below.

## Environment variables

Create a `.env` file in the project root (or use your environment manager) and add your weather API key. Example (if using OpenWeatherMap):

```
VITE_WEATHER_API_KEY=your_openweathermap_api_key_here
```

> The project expects the client-side key to be available as a Vite-prefixed variable (`VITE_...`). Adjust the variable name in the app code if a different name was used.

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/ankiit29/Klimate.git
cd Klimate
```

2. Install dependencies:

```bash
npm install
# or
# yarn
```

3. Create a `.env` file and add your API key as shown above.

4. Start the dev server:

```bash
npm run dev
# or
# yarn dev
```

Open `http://localhost:5173` (or the port Vite prints in console) to view the app.

---

## Available scripts

> These are the standard Vite/React scripts. If your `package.json` differs adjust accordingly.

* `npm run dev` — start the development server
* `npm run build` — build the production bundle
* `npm run preview` — preview the production build locally
* `npm run lint` — run linters (if configured)

---

## How it works (high-level)

1. On load, the app asks for Geolocation permission.
2. If granted, it obtains latitude and longitude, then uses TanStack Query to call the weather API.
3. Weather responses are cached by TanStack Query; charts are rendered with Recharts.
4. UI is composed from shadcn primitives and styled with Tailwind.

---

## Folder structure (typical)

```
Klimate/
├─ src/
│  ├─ components/       # Reusable UI components
│  ├─ hooks/            # Custom hooks (useWeather, useGeolocation, etc.)
│  ├─ pages/ or App.tsx  # App entry and routes
│  ├─ queries/          # TanStack Query functions
│  └─ styles/           # Tailwind / CSS
├─ index.html
├─ package.json
└─ vite.config.ts
```

---

## Deployment

This project builds into a static bundle and can be hosted on services such as Vercel, Netlify, GitHub Pages, or any static hosting provider. Make sure to set the `VITE_WEATHER_API_KEY` environment variable in your hosting provider's dashboard (do not commit keys to the repo).

---

## Troubleshooting

* **Location permission denied** — The app needs geolocation permission to auto-detect your location. If you deny permission, some apps offer manual location entry.
* **API errors / invalid API key** — Check that your `VITE_WEATHER_API_KEY` is correct and that your API plan allows the endpoints used.
* **CORS issues** — If the weather API blocks client-side requests, consider adding a small server-side proxy or switching to an API that permits browser access.

---

## Contributing

Contributions are welcome! If you'd like to improve Klimate:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "feat: ..."`)
4. Push to your branch and open a Pull Request

Please open issues for bugs or feature requests.

---

## Acknowledgements

Built with open-source tools and libraries. Thanks to the maintainers of React, Vite, TanStack Query, Recharts, shadcn/ui and Tailwind.

---


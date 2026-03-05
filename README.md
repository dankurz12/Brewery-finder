# Brewery Finder Web Tool

This project is a **minimal web application** that helps you discover top breweries near your current location. It uses the free [Open Brewery DB API](https://www.openbrewerydb.org/) to search for breweries within a few kilometres of your GPS coordinates and supplements the results with manually curated descriptions of some highly regarded Seattle taprooms.  The tool runs entirely in the browser, so there is no server to maintain.  It is designed to be mobile‑friendly and easy for beginners to deploy.

## 1. MVP definition

The minimum viable product (MVP) for this tool includes just three functions:

1. **Request the user’s geolocation** in the browser.  If permission is granted, the app obtains your latitude and longitude.  If not, it displays an error asking for location access.
2. **Query the Open Brewery DB API** using the `by_dist` filter to return breweries sorted by distance from your coordinates.  The app displays up to 10 breweries with their names, type (micro, brewpub, etc.), address and website.
3. **Enhance select breweries with extra context**.  For several top Seattle breweries (Hellbent, Halcyon, Project 9, Ravenna, Urban Family and Fair Isle), the app shows a short “vibe” description and highlights signature IPAs.  These descriptions come from a 2025 update to Eater Seattle’s guide to the city’s best breweries【222909148188953†L186-L197】【222909148188953†L208-L216】 and the tap list for Ravenna’s IPAs【871498723514603†L48-L115】.

The MVP intentionally omits ratings and live tap lists for every brewery because there is no reliable free API to provide that data.  Instead, it encourages users to follow the provided website links for up‑to‑date tap lists.

## 2. Technology stack

* **Frontend:** Plain HTML, CSS and vanilla JavaScript.  The code is contained in a single `index.html` file for simplicity and uses the browser’s `fetch()` API to call Open Brewery DB.  CSS is used sparingly to ensure the layout is responsive on mobile phones.
* **Data source:** [Open Brewery DB](https://www.openbrewerydb.org/).  This free API provides brewery names, addresses, coordinates and websites without requiring an API key.  Requests are made directly from the browser, and CORS is enabled by default.
* **Hosting:** [GitHub Pages](https://pages.github.com/) is used to deploy the static site.  GitHub Pages is free for public repositories and automatically serves the `index.html` file over HTTPS.  Alternative free hosts such as Netlify or Vercel work equally well.

This stack keeps the project beginner‑friendly; there is no backend, no build tooling and no databases to configure.

## 3. Running the code locally

1. **Clone or download** this repository to your computer.
2. Open `brewery_app/index.html` in a web browser.  On a desktop, you can simply double‑click the file.  On a mobile phone, you may need to use a file manager app to navigate to the file and open it.
3. Click the “Locate Me & Find Breweries” button.  Grant the browser permission to access your location.  The app will call the Open Brewery DB API and display a list of nearby breweries.  For the featured Seattle breweries, additional text highlights the taproom vibe and a signature IPA【222909148188953†L186-L197】【222909148188953†L247-L256】.

If your browser blocks geolocation from local files, you can serve the file via a simple local HTTP server.  For example, run `python3 -m http.server` in the `brewery_app` directory and visit `http://localhost:8000` in your browser.

## 4. Deploying to GitHub Pages

Follow these steps to publish the app for free:

1. **Create a new GitHub repository.** Name it whatever you like (e.g., `brewery-finder`).  Make it public if you want to use GitHub Pages for free.
2. **Add the project files.** Copy the contents of the `brewery_app` folder into the root of your repository.  Commit and push the files (`index.html` and `README.md`) to GitHub.
3. **Enable GitHub Pages.**  In your repository, go to **Settings → Pages**.  Under “Source,” choose the `main` branch and root (`/`) folder, then save.  GitHub will build and deploy your site.  After a minute or two, a URL in the form `https://YOUR_USERNAME.github.io/YOUR_REPO/` will be displayed.
4. **Visit your site on mobile.**  Share the GitHub Pages URL with friends or bookmark it on your phone.  Because the app is responsive and uses the Geolocation API, it will work seamlessly on mobile devices.
5. 

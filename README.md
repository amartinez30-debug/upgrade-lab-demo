# Upgrade Lab — Personal iPad Pitch Prototype

This is an independent, Tesla-inspired demonstration prototype, **not an official Tesla app**. The app should be pitched to management using fictional customer data only. It does not place orders, connect to Tesla internal systems, or validate promotional offers.

## Preview locally on your Mac
1. Unzip this folder.
2. Open `index.html` in Safari, or serve the folder locally with `python3 -m http.server 8000` and visit `http://localhost:8000`.
3. Network access is needed for mapping, the VIN API and EPA lookup. Some browser restrictions may block cross-site requests. A live website served over HTTPS generally works better than opening `index.html` as a file.

## Publish via GitHub Pages (free public prototype)
1. Make a new GitHub repository, for example `upgrade-lab-demo`. **Do not put customer information or Tesla confidential materials in it.**
2. Upload the **contents** of this folder to the repository root. `index.html` must be at the repository root.
3. Open repository `Settings` → `Pages` → `Build and deployment` → `Deploy from a branch` → select `main` and `/(root)` → `Save`.
4. Visit `https://YOUR-GITHUB-USERNAME.github.io/upgrade-lab-demo/`. Deployment may take a few minutes.
5. On your personal iPad, open that HTTPS link in **Safari**, tap **Share** → **Add to Home Screen** → turn on **Open as Web App** → **Add**. It will launch as an app-like website.

## Safe manager demo (3 minutes)
- Step 1: enter a **fictional** gas-car or older-Tesla scenario.
- Step 2: set weekly mileage, fuel price, and no-home-charging mode to show public charging comparisons.
- Step 3: show one illustrative new-Tesla lease and finance case. Separate the advertised monthly payment from upfront costs, taxes, fees and eligibility conditions.
- Step 4: present the upside of a transparent cost comparison, then ask to pilot with leadership and IT approval.

## Technical notes
- The tool uses inline HTML, CSS, and JavaScript, plus Leaflet via an external CDN.
- NHTSA, EPA, OpenStreetMap/geocoding and charging-station lookups are external services; availability and browser CORS rules may vary. They do not supply guaranteed live pricing, charging tariffs, financing offers or trade-in values.
- This demo does **not** include authentication, server-side storage, analytics, live Tesla integrations, inventory APIs or order tracking.
- It intentionally does **not** register an offline service worker: charging availability and financial offers should not be presented as current from a potentially stale offline cache.
- Do not collect real customer VINs, home/work addresses, loan details or other personal information before Tesla security/privacy approval. Address searches and VIN lookups send the entered identifiers to outside lookup providers.
- Do not deploy onto a Tesla-owned or managed device, use Tesla systems, scrape proprietary endpoints, or use Tesla marks as an official-branded application without authorization.

## Next development milestone
Move this proof of concept into React + TypeScript with source-controlled components, automated formula tests, a secure server for approved APIs, offer expiration timestamps, and role-based permission handling if a pilot is approved.
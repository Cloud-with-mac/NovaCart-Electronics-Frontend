# NovaCart Electronics — Azure Static Web Apps frontend

A polished responsive HTML/CSS/JavaScript frontend. No Node.js, npm, or build step required.

## Run locally
Open `index.html` with VS Code Live Server (recommended) or a local HTTP server such as `python -m http.server 5500`, then visit http://localhost:5500.

## Connect to the backend
Edit the public `config.js` to set `API_BASE_URL`. Current default is the NovaCart backend URL provided in this conversation. The frontend requests `GET /api/products` and recognizes common JSON shapes: arrays, `{products:[...]}`, `{data:[...]}` and `{data:{products:[...]}}`. If your backend response differs, update the `normalize()` or `extractItems()` functions in `app.js`.

Do not put private credentials, secrets, or API keys into frontend files. Configure CORS on the Azure backend to allow the frontend's Azure Static Web Apps hostname (and your local testing origin).

## Deploy to Azure Static Web Apps
Push all files at the repository root to GitHub. In Azure, create a **Static Web App** connected to that repo. Use app location `/`, API location blank, output location blank (static HTML without compilation). The generated GitHub Actions workflow deploys the site.

## Features / limitations
Live API catalogue, search, dynamic categories, sorting, cart stored in browser localStorage, responsive layout and polished CSS artwork. **Checkout is disabled** until verified order/payment APIs are integrated. API compatibility has not been verified against the deployed service from this offline workspace. Prices are displayed as GBP by default; adjust currency and locale in `config.js` to match your backend's actual pricing data.

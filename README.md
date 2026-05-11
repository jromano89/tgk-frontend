# TGK Front

Static TGK Wealth demo front end for the advisor and investor portals.

There is no build step and no project-level npm dependency. The app is plain HTML, CSS, and browser JavaScript.

## Hosted Backend

The default backend is configured in `config.js`:

```text
https://backend-tgk.up.railway.app
```

The front end uses that hosted service even when running locally. To test against a local backend without editing files, add `?backendUrl=http://localhost:3000` to the URL.

Backend docs:

- `https://backend-tgk.up.railway.app/api/docs`
- `https://backend-tgk.up.railway.app/api/docs.json`
- `https://backend-tgk.up.railway.app/api/health`

## Local Development

From this repo root:

```bash
python3 -m http.server 8080
```

Then open:

- `http://localhost:8080/`
- `http://localhost:8080/advisor/`
- `http://localhost:8080/investor/`

Opening `index.html` directly from the filesystem is not supported.

## Railway

Deploy this repo as a static site from GitHub. Railway's static hosting flow supports zero-configuration static sites, so this repo intentionally has no `package.json`, build command, or start command.

If the backend URL changes, update `BACKEND_URL` in `config.js` and redeploy the static site.

## Seed Demo Data

The optional seed script remains here because it populates data for this demo front end. It requires Node 18+ for built-in `fetch`.

```bash
TGK_SEED_BASE_URL=https://backend-tgk.up.railway.app \
TGK_SEED_APP_SLUG=tgk-wealth \
node scripts/seed-demo-api.js
```

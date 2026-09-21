# BnB Juices — Financial Ledger

A single-page, installable financial ledger and dashboard for BnB Juices. Track sales, orders, ingredient costs, delivery, electricity, equipment, and other income/expenses — all stored locally in the browser (no backend required). Amounts default to **Ghana Cedis (GH₵)**, editable in Settings.

## Files

| File | Purpose |
|---|---|
| `index.html` | The app itself — a self-contained HTML/CSS/JS dashboard. |
| `manifest.json` | Web App Manifest — lets browsers/phones "install" this as an app. |
| `icon-192.png`, `icon-512.png` | App icons referenced by the manifest. |
| `.github/workflows/deploy.yml` | GitHub Actions workflow that publishes this repo to GitHub Pages on every push to `main`. |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing and serve files as-is. |

## Hosting it on GitHub Pages

1. Create a new GitHub repository (public, or private with GitHub Pages enabled on your plan).
2. Push these files to the repository's `main` branch:
   ```bash
   git init
   git add .
   git commit -m "Initial commit — BnB Juices ledger"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**, and under "Build and deployment" set **Source** to **GitHub Actions**. (The included workflow handles the rest — no manual build step needed.)
4. Push to `main` (or re-run the workflow from the **Actions** tab) to trigger a deploy. Your site will be live at:
   ```
   https://<your-username>.github.io/<your-repo>/
   ```

## Installing it as an app

Once hosted, visit the site on:
- **Android (Chrome)** — tap the menu → "Install app" / "Add to Home screen".
- **iOS (Safari)** — tap Share → "Add to Home Screen".
- **Desktop (Chrome/Edge)** — click the install icon in the address bar.

The manifest sets the app to launch full-screen with its own icon and the ledger's dark green theme color.

## Notes

- All data is stored in the browser's `localStorage` on the device it's used on — nothing is sent to a server, and nothing syncs between devices.
- The currency symbol can be changed anytime in the app's Settings panel; it currently defaults to `GH₵`.

# Nibe F470 myUplink dashboard (GitHub Pages)

Files:
- `index.html`    – the dashboard
- `callback.html` – OAuth redirect target; forwards `?code=...` to `index.html`
- `.nojekyll`     – tells Pages to serve files as-is

## Deploy
1. Create a GitHub repo (e.g. `nibe-dashboard`) and upload these files to the root.
2. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`.
3. Wait a minute. Your site will be at `https://<username>.github.io/nibe-dashboard/`.

## Register the myUplink app
At https://dev.myuplink.com/apps create an application with:

- **Callback URL:** `https://<username>.github.io/nibe-dashboard/callback.html`

The callback URL cannot be edited after creation, so make sure it is exact (including `https://` and the repo name).

## Use
Open `https://<username>.github.io/nibe-dashboard/`, paste Client ID and Secret, click **Authorize**.

## Security notes
- The repo is public, so never commit your Client Secret. It is entered in the browser and kept in localStorage only.
- Anyone with access to your browser profile can read it from localStorage.

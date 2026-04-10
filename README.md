# Deus.iA — Support site (GitHub Pages)

Static support page for the Deus.iA iOS app, intended as the App Store Connect **Support URL** ([Guideline 1.5 — Safety](https://developer.apple.com/app-store/review/guidelines/#safety)).

## Live site (after publish)

User-facing URL (replace with your GitHub user and repo name):

`https://<user>.github.io/<repo>/`

Example: if the repo is `github.com/acme/deus-ai-support`, the page is:

`https://acme.github.io/deus-ai-support/`

Use that exact URL in **App Store Connect → App Information → Support URL**.

## Repository contents

| Item        | Purpose |
| ----------- | ------- |
| `index.html` | Single-page support: contact, FAQ (English). Edit email and copy before launch. |
| `app-ads.txt` | Same content AdMob expects ([setup guide](https://support.google.com/admob/answer/9363762)). This repo keeps a copy; **AdMob does not read this project path** — see AdMob section below. |
| `.gitignore` | Keeps local/editor noise out of the repo. |

### AdMob / app-ads.txt (Google’s rules)

Follow [Set up an app-ads.txt file for your app](https://support.google.com/admob/answer/9363762). Summary that affects this setup:

- **iOS:** Add your developer website in the **Marketing URL** field in App Store Connect (AdMob uses the store listing’s developer website).
- **Where Google looks:** The crawler requests `https://<hostname>/app-ads.txt` (and `http://…`), using the **hostname only** — not the full path of your store URL. Example from Google: if the site is `https://example.com/game`, it still checks `https://example.com/app-ads.txt`.

So if your listing points at `https://<user>.github.io/<repo>/`, the hostname is **`<user>.github.io`**. AdMob checks:

`https://<user>.github.io/app-ads.txt`

A file only at `https://<user>.github.io/<repo>/app-ads.txt` does **not** match that rule. To comply while staying on GitHub Pages, use one of:

1. **User site repo** `https://github.com/<user>/<user>.github.io` — put `app-ads.txt` at the **root** of that repository so it is served at `https://<user>.github.io/app-ads.txt`, **or**
2. **Custom domain** on a site you control at the **apex** (e.g. `https://deusai.example`) and publish `https://deusai.example/app-ads.txt`, **or**
3. **Firebase Hosting** (Google documents this option in the same help article).

Keep the line in `app-ads.txt` exactly as AdMob shows (publisher ID + `DIRECT` + certification authority ID). After publishing to the correct URL, use **Check for updates** in AdMob; verification can take up to 24 hours.

No build step: static HTML + inline CSS only.

## Publish

1. Create a **public** repository on GitHub and push this folder as the repo root.
2. **Settings → Pages:** Source **Deploy from a branch**, branch `main`, folder **`/ (root)`**.
3. Wait for the first deploy (GitHub shows the live URL on the Pages settings page).
4. Set App Store Connect **Support URL** to your live `https://<user>.github.io/<repo>/` URL.

## Edit before going live

- Update the contact email and FAQ text in `index.html`.

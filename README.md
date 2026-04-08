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
| `.gitignore` | Keeps local/editor noise out of the repo. |

No build step: static HTML + inline CSS only.

## Publish

1. Create a **public** repository on GitHub and push this folder as the repo root.
2. **Settings → Pages:** Source **Deploy from a branch**, branch `main`, folder **`/ (root)`**.
3. Wait for the first deploy (GitHub shows the live URL on the Pages settings page).
4. Set App Store Connect **Support URL** to your live `https://<user>.github.io/<repo>/` URL.

## Edit before going live

- Update the contact email and FAQ text in `index.html`.

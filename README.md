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
| `app-ads.txt` | [IAB app-ads.txt](https://iabtechlab.com/ads-txt/) for **Google AdMob** validation. Must stay in sync with the **Support URL** (or Marketing URL) domain in App Store Connect. |
| `.gitignore` | Keeps local/editor noise out of the repo. |

### AdMob / app-ads.txt (iOS)

After Pages deploy, the file must be reachable at:

`https://<user>.github.io/<repo>/app-ads.txt`

In **App Store Connect**, the **Support URL** (or the developer site URL AdMob uses) must be the **same site** — e.g. `https://<user>.github.io/<repo>/` — so Google’s crawler looks under that host/path. If validation still fails, Google may be resolving only the hostname (`*.github.io`); in that case use a **custom domain** on this Pages site and set that URL in the store, then keep `app-ads.txt` at `https://your-domain.com/app-ads.txt`.

Re-check validation in AdMob after publishing; propagation can take a few minutes.

No build step: static HTML + inline CSS only.

## Publish

1. Create a **public** repository on GitHub and push this folder as the repo root.
2. **Settings → Pages:** Source **Deploy from a branch**, branch `main`, folder **`/ (root)`**.
3. Wait for the first deploy (GitHub shows the live URL on the Pages settings page).
4. Set App Store Connect **Support URL** to your live `https://<user>.github.io/<repo>/` URL.

## Edit before going live

- Update the contact email and FAQ text in `index.html`.

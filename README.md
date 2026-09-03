# Formula Flip PWA

Formula Flip is a standalone, installable formula flashcard app. It stores decks and cards in the browser on the current device and does not connect to ChatGPT Sites.

## Included files

- `index.html` — complete app interface and functionality
- `manifest.webmanifest` — installable app settings
- `sw.js` — offline caching and PWA support
- `icons/` — app icons for browsers and installed devices
- `.nojekyll` — tells GitHub Pages to serve the files directly

## Publish with GitHub Pages

1. Create a new public GitHub repository, such as `formula-flip`.
2. Upload everything inside this folder to the repository root.
3. Open the repository's **Settings**.
4. Select **Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select the `main` branch and `/ (root)`, then save.
7. Wait for GitHub to provide the public address.

The resulting address will normally look like:

`https://YOUR-USERNAME.github.io/formula-flip/`

## Install the app

Open the published address in a supported browser and select **Install app** or **Add to Home Screen** from the browser menu.

## Important data note

Decks, cards, and study history use browser `localStorage`. They remain on the same browser and device but do not synchronize across devices. Data from the ChatGPT-hosted Formula Flip will not automatically transfer because it belongs to a different website address.


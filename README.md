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

Decks, cards, study history, and any reference images you attach to a formula are stored in the browser's **IndexedDB** (not `localStorage`), so there's much more headroom for images without filling up tiny storage quotas. Everything still stays on the same browser and device only — nothing syncs across devices, and nothing is uploaded anywhere. If this is an update over an older copy of Formula Flip that used `localStorage`, your existing decks/cards/history are automatically migrated into IndexedDB the first time you open the updated app.

Data from the ChatGPT-hosted Formula Flip will not automatically transfer because it belongs to a different website address.

## What changed in this revision

- **Nested parentheses in equations are fixed.** The equation renderer now parses `frac()`, `sqrt()`, `^()` and `_()` recursively instead of with regular expressions, so expressions like `frac((P1 - P2), (ρ × g))` or even `frac(frac(P,ρ), (g × h))` render correctly. The quick-insert toolbar (x², x³, xᵃ, xₐ, √, a/b, π, α, β, θ, ρ, Δ, Σ, μ, λ, ×, ÷, ±) is unchanged.
- One small behavior change from the old parser: the hardcoded `hf` → h<sub>f</sub> special case has been removed, since it was exactly the kind of one-off regex patch this fix was meant to get away from. Type `h_(f)` to get a subscripted h with f — the general subscript syntax now covers it.
- **Reference images.** When adding or editing a formula, there's now a "Reference image" field — upload a diagram, textbook figure, handwritten solution, or screenshot. Images are resized and compressed in the browser before saving, and shown as a thumbnail in the formula list and under the answer during review.
- **Storage moved to IndexedDB** for decks, cards, history, and images, so large images won't bump into `localStorage`'s small quota.


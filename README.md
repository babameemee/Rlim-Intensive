# Decision Clarity Intensive — deploy package

This is a **static build**: plain HTML, no JavaScript framework, no build step.
Upload the contents of this folder to the repo root that Cloudflare Pages serves.

    index.html          landing page
    thank-you.html      post-booking page (Calendly redirect target)
    _headers            cache rules for Cloudflare Pages
    assets/logo.webp
    assets/richard.webp
    assets/signature-light.webp

## Important: replacing the previous upload

The old build loaded a file called `support.js` and `.png` images. **Delete these
from the repo** — they are no longer referenced:

    support.js
    assets/logo.png
    assets/richard.png
    assets/signature-light.png

## The video

The page loads it from your R2 bucket:
`https://pub-2d2dc6036f1346409841abab96401232.r2.dev/richard-intensive.mp4`
To change it, search `index.html` for `richard-intensive.mp4`.

When the site moves to Richard's Cloudflare account, re-upload the video to his
R2 bucket and replace that URL with his public bucket URL.

## Calendly

Booking links point to `calendly.com/rlimleadership/decision-clarity-intensive`.
In Calendly → that event → Confirmation page, set the redirect to
`https://yourdomain.com/thank-you.html`.

## What changed for speed

- Removed the React runtime (`support.js`) — it was render-blocking for ~3 seconds
- Images converted to WebP: Richard's photo went from 444 KB to 40 KB
- Google Fonts now load asynchronously instead of blocking the first paint
- Intrinsic width/height on every image, so nothing reflows as they arrive
- `_headers` gives images a one-year immutable cache

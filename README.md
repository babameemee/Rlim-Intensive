# Decision Clarity Intensive — deploy package

Upload the **contents of this folder** to your GitHub repo root, then connect the repo
to Cloudflare Pages (Framework preset: **None**, Build command: *blank*, Output directory: `/`).

## Files

    index.html          → the landing page
    thank-you.html      → post-booking page (set as Calendly redirect URL)
    support.js          → required runtime; must sit next to the HTML files
    assets/logo.png
    assets/richard.png
    assets/signature-light.png

## You still need to add

    assets/richard-intro.mp4          ← your ~1:45 intro video (required for the video block)
    assets/richard-intro-poster.jpg   ← optional still frame shown before play

Drop them into `assets/` with exactly those names. No code changes needed.

## After deploying

1. Point your domain/subdomain at the Pages project.
2. In Calendly → Decision Clarity Intensive → Confirmation page, set the redirect to
   `https://yourdomain.com/thank-you.html`
3. `thank-you.html` carries `<meta name="robots" content="noindex">` — leave it there.

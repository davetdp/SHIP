SHIP — Sea Hawk Intelligence Portal (marketing site)
=====================================================

CONTENTS
  index.html          The marketing page (entry point)
  source-assets/
    js/               head-script.js + main.cinematic.js (the scene/map/chat engine)
    images/           logos, AISHA orb, vessel art, intro poster frame
    fonts/            Inter / Space Grotesk / IBM Plex Mono (self-hosted woff2)
    video/            ship-intro.mp4  (the intro walkthrough, ~25 MB, no audio)

IMPORTANT — must be SERVED over HTTP, not opened via file://
  The page loads the fonts, JS, images and video with relative paths, and
  browsers block some of those when a file is opened directly from disk.
  Serve the folder instead. From this folder:

      python3 -m http.server 8000

  then open  http://localhost:8000/

HOW TO EMBED IN AN EXISTING SITE
  Option A — iframe (simplest, fully isolated):
      Host this folder anywhere static (S3, Netlify, Vercel, an internal
      server) and drop it into your page:
          <iframe src="https://your-host/path/" style="width:100%;height:100vh;border:0"></iframe>

  Option B — copy the files in:
      Copy index.html + the whole source-assets/ folder into your project,
      keeping them side by side. If index.html lives in a subfolder, the
      relative source-assets/ paths still work as long as the two stay
      together. Rename index.html if it collides with your own.

NOTES
  * All data shown (revenue, P&L, vessel positions, etc.) is MOCK data for
    demonstration only — this is a marketing/demo page, not the live portal.
  * The live portal is linked from the page's "Open the live portal" button.

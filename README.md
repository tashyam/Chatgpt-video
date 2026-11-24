# ToonForge 3D Studio

A free, mobile-accessible procedural 3D cartoon short maker. This is a browser-based prototype and does not require a backend, API key, subscription, or account.

## What it does
- Turns a story into a simple storyboard (local sentence splitting and keyword-based scene classification).
- Creates a procedural 3D cartoon character and simple environments with Three.js.
- Animates the character and camera.
- Adds captions to the rendered frames.
- Records the result in the browser as a WebM video.
- Accepts an optional local narration audio file.

## Important limitations
This is not a full generative-AI video model. It does not create arbitrary detailed character art, advanced skeletal animation, automatic dialogue/lip-sync, or AI-generated voice. The scene planner is rule-based. The visual output is a stylized prototype.

Rendering happens on the device. Long videos, high resolution, and older phones may run out of memory or overheat. Start with 30 seconds. Keep the tab open during rendering. Export is WebM, not MP4.

Three.js is loaded from jsDelivr, so an internet connection is needed when opening the app. Browser support for WebGL and MediaRecorder is required. Current Chrome on Android is recommended.

## Run on Android
1. Download and extract the ZIP.
2. Upload `index.html` to a public GitHub repository.
3. In the repository, open Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch.
5. Select `main` and `/ (root)`, then Save.
6. Wait for GitHub Pages to publish. Open the displayed `https://USERNAME.github.io/REPOSITORY/` link in Chrome.
7. Use the story box, tap Generate scenes, then Preview animation and Render & export video.

You can also test locally by opening `index.html` in a browser, but some Android file managers may block ES module imports. GitHub Pages is the recommended route.

## Project files
- `index.html` — complete single-page app.
- `README.md` — setup, usage and limitations.

## License
MIT. Three.js is separately licensed under MIT; see https://github.com/mrdoob/three.js


## Build 1.1 export fix
- Uses codec detection and prefers VP8 for wider Android WebM compatibility.
- Checks that canvas capture provides a video track.
- Reports MediaRecorder startup and finalization errors in the page.
- Shows an explicit Download WebM video link after successful recording instead of relying only on an automatic download.
- Adds a finalization delay so the last encoded chunk can be flushed.

After replacing `index.html` in GitHub, allow Pages to redeploy and hard-refresh the site in Chrome. Test without narration first.

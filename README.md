## NETFLIX CLONE — static landing pages

This repository contains a small static Netflix-style landing page and a simple billing/plans demo. It's a front-end-only project (HTML, CSS and vanilla JS) intended for learning, prototyping, or demonstration purposes.

### What project contain

- The project is a static website (no backend). Primary files:
  - `Index.html` — Main landing / home page (hero, feature sections, FAQ, footer).
  - `Style.css` — Global styles used by `Index.html` and other pages.
  - `net.html` — Plan selection / billing demo (interactive plans, payment form, receipt).
  - `billing.html` — Another copy of the billing/plans demo (same purpose).
  - Media assets: `img1.jpg`, `img.png`, `st img.jpg`, `device-pile-in.png`, `tv.png`, `videoframe 1.png`, `videoframe 2.png`, `logo.svg`, `video 1.m4v`, `video 2.m4v`, etc.

Files present at root (partial):

```
billing.html
Index.html
net.html
Style.css
logo.svg
img1.jpg  (background hero image)
tv.png
device-pile-in.png
video 1.m4v
video 2.m4v
...other image assets
```

### Quick overview of features

- Responsive-ish layout using CSS flexbox (several feature sections named `tv1`, `tv2`, etc.).
- Hero section with email input button (no backend, button is static).
- Video elements embedded and autoplaying (muted + loop).
- Billing/plan demo (`net.html` / `billing.html`) contains a small JS app that:
  - Lets users select a plan (Basic/Standard/Premium)
  - Choose a payment method (Card / UPI)
  - Shows a receipt and allows printing

### How to run / preview locally

Since this is a static project you can open pages directly in your browser, but for best results run a simple local HTTP server so media (especially video) loads consistently.

Recommended options (PowerShell-friendly):

1) If you have Python 3 installed (recommended):

```powershell
python -m http.server 8000
Start-Process http://localhost:8000/Index.html
```

2) If you have Node.js installed and prefer a tiny server (http-server):

```powershell
npm install --global http-server
http-server -c-1 -p 8000
Start-Process http://localhost:8000/Index.html
```

3) Quick direct open (no server):

```powershell
Invoke-Item .\Index.html
```

Notes:
- Serving over HTTP is preferable for consistent media/video playback and to avoid cross-origin file restrictions in some browsers.

### Development notes & known issues

- Filenames contain spaces (e.g. `video 1.m4v`). Spaces in asset filenames can cause awkward URLs; consider renaming to `video-1.m4v` for reliability.
- `Index.html` references `Style.css` — ensure you open the file from the project root so relative paths resolve.
- There is no form validation or backend. The email input and "Get Started" button on the hero are static.
- `billing.html` and `net.html` are very similar; you can consolidate to one file to avoid duplication.


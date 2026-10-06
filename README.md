# mesyuarat

Full-page wrapper for the SMK Meradong **Kehadiran Mesyuarat** Google Apps Script web app.

It embeds the Apps Script `/exec` URL in an iframe, which suppresses the
"This application was created by a Google Apps Script user" bar that Google adds
when the web app is opened directly. Google only draws that bar in the top-level
window; inside a frame it is not drawn.

Live link : https://ingsiong-dev.github.io/mesyuarat/
Live app  : https://script.google.com/macros/s/AKfycbxMrSa4fScEFGyjSXQqUIQZX-FFDhotbjg-8LmLNiGtC_tH2wPAfdb4ZzYU7GJ97lTU0A/exec
Source    : Apps Script project `1TEf0Ls11UZhU0rvJ6fK43vaBAQu0ahHWvmWqc-uZbYVC_HRWqew5UfSm` (version 14)

## What the splash shows

The page is still nothing but the iframe - the wrapper exists to suppress the
Google bar, so it must not steal any of the app's space. What changed is the
loading state: a branded card (crest, system name, indeterminate meter,
"Developed by Koh Ing Siong") on a soft green gradient, instead of a white page
with a blue spinner. The loading wording is ENGLISH ("Preparing..."), at his
request - the app itself stays in Malay. If the app is slow the status line says
so after 6 s and a **Try again** button appears after 12 s; the overlay is always
cleared after 20 s.

## Updating

Edit `index.html`, then:

```powershell
git add -A
git commit -m "Update wrapper"
git push
```

GitHub Pages rebuilds automatically in about a minute.

## Notes

- The Apps Script app must keep `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)`
  in `doGet()`, otherwise browsers refuse to frame it.
- The original `/exec` link still works and is unchanged; it just keeps the Google bar.
- This repository is public because GitHub Pages on a free account requires a public repo.

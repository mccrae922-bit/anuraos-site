AnuraOS - local copy
====================

This is the anura.pro site itself, saved locally: ~270 files.
It is NOT a single HTML file, because AnuraOS needs its own files
(a background worker, script files, fonts, wallpapers and app folders).
Opening index.html by double-clicking will not work - the browser blocks
the background worker on file:// pages.

Run it with any static web server, for example:

    cd <this folder>
    python3 -m http.server 8000

then open http://localhost:8000 in Chrome.

To put it online for free, upload these files to a GitHub repo and turn on
Settings -> Pages -> Source: Deploy from a branch (or GitHub Actions) and
point it at the folder that holds index.html.

Notes
-----
- Linux emulation is not included: it needs ~1 GB of virtual disk images.
  The two /x86images helper files were left out of this zip to keep it
  under 25 MB; the Linux installer in Settings will report an error if you
  try to use it, everything else works.
- Deploying: this folder works as-is on Netlify (drag the zip onto
  app.netlify.com/drop) or Vercel (vercel.com/drop). The _headers file
  (Netlify) and vercel.json (Vercel) set the headers the OS expects.
- Three small repairs were needed to run it off a normal server; they are
  marked "local mirror shim" in index.html, lib/Boot.js and anura-sw.js.

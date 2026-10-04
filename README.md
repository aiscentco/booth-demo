# SISÓNE booth competition: demo preview

A single-file demo (`index.html`, no build step) with three parts: the NFC tap, the guest page and the booth screen.

## Put it on GitHub Pages
1. Create a new repository on GitHub.
2. Upload `index.html` to the repository root (Add file, Upload files, Commit).
3. Settings, Pages, Source: "Deploy from a branch", branch `main`, folder `/ (root)`, Save.
4. After a minute the demo is live at `https://<your-user>.github.io/<repo>/`.

Notes
- A Pages site is public to anyone with the link, and `index.html` contains SISÓNE's product photos. The page asks search engines not to index it, but keep the link private. Delete or unpublish it after the meeting if needed.
- Useful links once live:
  - `.../?view=guest` opens only the guest page (this is what an NFC sticker would open; add `&src=nfc` to label the source).
  - `.../?view=booth` opens only the booth screen, ready for full screen.
- Sharing the Story to Instagram and saving the image only work on the live site, opened on a phone. On iPhone and Android the share sheet lets the guest pick Instagram, then Story.

## Still to connect (your part)
In the `<script>`, find `CONFIG` and `submitEntry`:
- `CONFIG.endpoint`: your backend URL. The page will POST `{ email, friend, consent, source, ts }` and expects `{ code }` back.
- `CONFIG.discountCode`: set a shared code, or leave null and return unique codes from the backend.
- Replace the placeholder QR on the booth screen and the privacy-policy line on the email step.
- Instagram cannot confirm a follow or a posted Story, so those two steps are on the honour system.

## Second page: how the contest works
`how-it-works.html` is a separate animated walkthrough (tap, follow, snap, Story, email, draw, what the brand keeps). On Pages it lives at `https://<your-user>.github.io/<repo>/how-it-works.html`. Arrow keys, swipe or the dots move between slides; it also plays on its own.

## Third page: the winner reveal
`winner.html` is the full-screen draw for the booth screen, on the light animated background. Press the button or space to run it. Options in the link: `?clean=1` hides the button, `?winner=@name` shows a fixed winner, `?entries=@a,@b,@c` replaces the example names. Press R to reset.

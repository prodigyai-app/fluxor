# Fluxor — Revision Console

A free, self-contained web app for exam revision: flashcards, exam-style multiple-choice questions with worked explanations, embedded video lessons, a progress dashboard, and an avatar rewards scheme. It covers GCSE Biology, Chemistry, Physics and Combined Science (AQA), GCSE Computer Science (OCR), GCSE Maths Foundation & Higher (Edexcel), and A-Level Physics (OCR A).

Everything lives in a single `index.html` file — no server, no database, no build step. Progress is saved to a downloadable `.fluxor` file that you can re-load on any device.

---

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The entire app. This is all you strictly need. |
| `qr.html` | A QR-code & link maker. Open it, paste your live site address, and download a QR code (PNG or SVG). Runs entirely in the browser. |
| `404.html` | A friendly "page not found" screen that links back to the app. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is (recommended). |
| `LICENSE` | MIT license — free to use and adapt. |
| `README.md` | This file. |

---

## How to host it on GitHub Pages

You have two options. **Option A** needs no software installed — just a web browser.

### Option A — Upload through the GitHub website (easiest)

1. **Create a free GitHub account** at https://github.com if you don't have one.
2. Click the **+** in the top-right → **New repository**.
3. Give it a name, e.g. `fluxor`. Leave it **Public**. Click **Create repository**.
4. On the new repository page, click **uploading an existing file** (the link in the "Quick setup" box), or go to **Add file → Upload files**.
5. **Drag in all the files from this folder** (`index.html`, `404.html`, `.nojekyll`, `LICENSE`, `README.md`).
   - If the `.nojekyll` file is hard to drag (some systems hide dot-files), you can skip it — the app still works.
6. Click **Commit changes**.
7. Go to the repository's **Settings** tab → **Pages** (in the left sidebar).
8. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **`main`** branch and the **`/ (root)`** folder, then click **Save**.
9. Wait about 1–2 minutes. Refresh the Pages settings screen and your site URL will appear at the top:

   ```
   https://YOUR-USERNAME.github.io/fluxor/
   ```

That link is your live app. Share it with anyone.

### Option B — Command line (if you use git)

```bash
# inside this folder
git init
git add .
git commit -m "Add Fluxor revision app"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/fluxor.git
git push -u origin main
```

Then do steps 7–9 from Option A to switch Pages on.

---

## Custom domain — fluxor.prodigyai.uk (set up for this build)

This package already contains a `CNAME` file set to **fluxor.prodigyai.uk**, so once it's in your GitHub Pages repo you only need to add one DNS record at GoDaddy:

1. Sign in to **GoDaddy → My Products → DNS** for prodigyai.uk.
2. Add a record:
   - **Type:** CNAME
   - **Name / Host:** `fluxor`
   - **Value / Points to:** `prodigyai-app.github.io`  (the account root — *not* the `/fluxor` path)
   - **TTL:** default (1 hour) is fine
3. Save. DNS usually propagates within minutes to an hour.
4. In the repo, go to **Settings → Pages** and tick **Enforce HTTPS** once the option appears (GitHub issues the certificate automatically after DNS resolves).

The site will then serve at **https://fluxor.prodigyai.uk** — the address bar stays on your domain, and the old `prodigyai-app.github.io/fluxor` address redirects to it. Use a CNAME record (not an A record) for a subdomain like this.

To use a different domain instead, change the contents of the `CNAME` file to that domain and point its DNS the same way.

---

## Video lessons

Science topics embed Cognito playlists directly. GCSE Maths (Foundation and Higher) links each topic to the matching free **Maths Genie** lesson page, which opens on mathsgenie.co.uk in a new tab alongside practice questions and worked solutions. Open any maths topic and choose the **Videos** tab.

## Transfer progress between devices

Fluxor can move a student's progress from one device to another with no account and no server. On the first device, open the progress bar and choose **Transfer out** — it shows a QR code (and a copyable code) holding the compressed progress. On the second device, choose **Transfer in** and either scan the QR with the camera or paste the code. The progress, rewards and badges arrive directly; nothing is uploaded anywhere.

The downloadable `.fluxor` file remains the durable backup; the QR handoff is the quick way to hop between devices.

## Making a QR code and a short link

Once your site is live and you have its address (e.g. `https://YOUR-USERNAME.github.io/fluxor/`):

- **QR code:** open `qr.html` (it deploys alongside the app at `https://YOUR-USERNAME.github.io/fluxor/qr.html`, or just double-click the file locally). Paste your address, pick a size, and download a PNG or SVG. Great for posters, worksheets, or the board.
- **Short link:** paste your address into a free redirect service such as TinyURL or is.gd and choose a custom ending (e.g. `tinyurl.com/my-revision`). Paste that short link back into `qr.html` if you'd rather the QR points at the short version.
- **Cleanest of all:** set a custom domain under **Settings → Pages** so the address itself is short.

Always scan or click the finished code/link once to test it before sharing widely.

---

## Updating the app later

Replace `index.html` with a new version (drag-and-drop **Add file → Upload files** again, or `git add . && git commit && git push`). GitHub Pages redeploys within a minute or two.

> **Tip:** if you don't see the update, do a hard refresh (Ctrl/Cmd + Shift + R) to clear the browser cache.

---

## Notes

- **No tracking, no ads, no accounts.** All progress stays on the user's device unless they choose to download their `.fluxor` save file.
- Works offline once loaded. You can also just open `index.html` by double-clicking it locally, without any hosting at all.
- Best viewed in any modern browser (Chrome, Edge, Firefox, Safari) on desktop, tablet or phone.

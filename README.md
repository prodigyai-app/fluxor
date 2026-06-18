# Fluxor — Revision Console

A free, self-contained web app for exam revision: flashcards, exam-style multiple-choice questions with worked explanations, a progress dashboard, and an avatar rewards scheme. It covers **GCSE Physics (AQA)**, **A-Level Physics (OCR A)**, and **GCSE Maths Foundation & Higher (Edexcel)**.

Everything lives in a single `index.html` file — no server, no database, no build step. Progress is saved to a downloadable `.fluxor` file that you can re-load on any device.

---

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The entire app. This is all you strictly need. |
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

## Using a custom domain (optional)

If you own a domain (e.g. `revise.example.com`):

1. In the repository **Settings → Pages → Custom domain**, type your domain and **Save**.
2. With your domain provider, add a **CNAME record** pointing your subdomain to `YOUR-USERNAME.github.io`.
3. Tick **Enforce HTTPS** once it becomes available.

GitHub will create a `CNAME` file in your repo automatically — leave it there.

---

## Updating the app later

Replace `index.html` with a new version (drag-and-drop **Add file → Upload files** again, or `git add . && git commit && git push`). GitHub Pages redeploys within a minute or two.

> **Tip:** if you don't see the update, do a hard refresh (Ctrl/Cmd + Shift + R) to clear the browser cache.

---

## Notes

- **No tracking, no ads, no accounts.** All progress stays on the user's device unless they choose to download their `.fluxor` save file.
- Works offline once loaded. You can also just open `index.html` by double-clicking it locally, without any hosting at all.
- Best viewed in any modern browser (Chrome, Edge, Firefox, Safari) on desktop, tablet or phone.

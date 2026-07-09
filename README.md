# Lumen — deployment package

This folder is the production build of Lumen (lumen-gi), ready for GitHub Pages.

## Test before deploying (30 seconds)

Double-click **Preview Lumen.command**. A Terminal window opens, and your
browser loads the site at http://localhost:5173 — byte-for-byte the same
files you're about to upload. Things worth clicking through:

- Switch conditions and languages (EN/ES toggle, top right).
- Scroll to a condition's "Understand" section → the review-status card
  with the References panel.
- The footer's "About & policies" links (six pages).
- The contact form at Contact & feedback — a test submission will arrive
  at https://formspree.io/forms and your email.

When you're done, close the Terminal window to stop the preview.

## How to deploy (5 minutes, no command line)

1. Go to https://github.com/new and create a repository named `lumen`
   (public, no README).
2. On the empty-repo page, click **"uploading an existing file"**.
3. Drag these files into the upload area and click **Commit changes**:
   `index.html`, the `index-*.js` and `index-*.css` files,
   `portrait-*.jpg`, and `.nojekyll`. (`README.md` and
   `Preview Lumen.command` are for you — no need to upload them, though
   it's harmless if you do.) The build is flat on purpose — there are no
   subfolders to preserve, so a simple file drag always works.
4. In the repo, go to **Settings → Pages**.
5. Under "Build and deployment", set Source to **Deploy from a branch**,
   choose branch **main** and folder **/ (root)**, then **Save**.
6. Wait ~1 minute. Your site is live at:
   **https://YOUR-USERNAME.github.io/lumen/**

## Notes

- **Contact form:** the feedback form at `#/contact` submits to Formspree
  (form "Lumen feedback", endpoint `https://formspree.io/f/xeebbbed`,
  notifications to p.deipthan@gmail.com; free tier = 50 submissions/month).
  Manage it at https://formspree.io/forms. The endpoint lives in
  `FORMSPREE_ENDPOINT` in `lumen-gi/src/components/FeedbackForm.tsx`; if it
  is ever emptied, the form falls back to opening the visitor's email app.
- **Naming the GI reviewer:** when a board-certified gastroenterologist has
  formally reviewed the content, set `reviewedBy` in
  `lumen-gi/src/data/provenance.ts` (per condition) and update the team entry
  in `lumen-gi/src/data/pages.ts`, then rebuild. Until then the site honestly
  shows "formal gastroenterology review in progress."

- `.nojekyll` is required — it stops GitHub from running the files through
  Jekyll. If you drag-and-drop and it's missing (hidden files are easy to
  skip), create it in the repo: Add file → Create new file → name it
  `.nojekyll` → commit.
- To update the site later: rebuild (`npm run build` in the lumen-gi
  project), then upload the new files over the old ones.
- Source code lives in the separate `lumen-gi` project folder — this is
  just the compiled output.

Contact: deprabak@ttep.edu

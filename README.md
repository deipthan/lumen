# Lumen — deployment package

This folder is the production build of Lumen (lumen-gi), ready for GitHub Pages.

## How to deploy (5 minutes, no command line)

1. Go to https://github.com/new and create a repository named `lumen`
   (public, no README).
2. On the empty-repo page, click **"uploading an existing file"**.
3. Drag **everything inside this folder** (index.html, the assets folder,
   .nojekyll) into the upload area and click **Commit changes**.
4. In the repo, go to **Settings → Pages**.
5. Under "Build and deployment", set Source to **Deploy from a branch**,
   choose branch **main** and folder **/ (root)**, then **Save**.
6. Wait ~1 minute. Your site is live at:
   **https://YOUR-USERNAME.github.io/lumen/**

## Notes

- `.nojekyll` is required — it stops GitHub from running the files through
  Jekyll. If you drag-and-drop and it's missing (hidden files are easy to
  skip), create it in the repo: Add file → Create new file → name it
  `.nojekyll` → commit.
- To update the site later: rebuild (`npm run build` in the lumen-gi
  project), then upload the new files over the old ones.
- Source code lives in the separate `lumen-gi` project folder — this is
  just the compiled output.

Contact: deprabak@ttep.edu

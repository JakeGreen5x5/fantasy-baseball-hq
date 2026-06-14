# Fantasy HQ — Site Setup Guide

This folder is a ready-to-host website. It uses plain HTML/CSS — no build tools,
no installs needed.

## Folder structure

```
index.html              <- homepage
assets/css/style.css    <- all styling
2026/
  index.html             <- 2026 season page (team grid)
  blue-wahoo/
    index.html           <- Blue Wahoo report list
    week-12.html          <- Week 12 report
    bw_simple.png, bw_standings.png
  space-cowboys/
    index.html
    week-12.html
    sc_simple.png, sc_standings.png, sc_saves.png
  pelicans/
    index.html
```

## How to put this on GitHub Pages (free)

### Step 1: Create the repository
1. Go to github.com and sign in to your new account.
2. Click the **+** icon top-right -> **New repository**.
3. Name it something like `fantasy-hq` (or `yourusername.github.io` if you
   want it at the root of your GitHub URL with no extra path).
4. Set it to **Public**. Don't add a README/gitignore (we already have files).
5. Click **Create repository**.

### Step 2: Upload these files
1. On the new repo page, click **uploading an existing file** (a link in the
   "Quick setup" box).
2. Drag the ENTIRE contents of this folder (index.html, assets/, 2026/) into
   the upload box. Make sure the folder structure is preserved — GitHub's
   drag-and-drop usually keeps folder paths if you drag the folders themselves.
3. Scroll down, click **Commit changes**.

### Step 3: Turn on GitHub Pages
1. In your repo, click **Settings** (top right of repo).
2. In the left sidebar, click **Pages**.
3. Under "Build and deployment" -> "Source", choose **Deploy from a branch**.
4. Branch: select **main** (or **master**), folder: **/ (root)**. Click **Save**.
5. Wait 1-2 minutes. Refresh the page — GitHub will show you a URL like:
   `https://yourusername.github.io/fantasy-hq/`

That's your live site. Any time you want to add a new weekly report:
1. Add the new HTML file (copy an existing week's file as a template, change
   the content and filename, e.g. `week-13.html`).
2. Add a new `<li>` entry to that team's `index.html` report list pointing to
   the new file.
3. Upload/commit the changes the same way (or use GitHub's "Edit" pencil icon
   on individual files for small changes — no re-upload needed).

## Adding next season (2027)

1. Duplicate the `2026/` folder, rename it `2027/`.
2. Update team records/rosters inside it.
3. Add a new tab in the `year-tabs` nav of every page:
   `<a href="../2027/index.html">2027</a>` (adjust relative path depth as needed).

## Future ideas (not built yet)
- A "Players" or "Rankings" tab at the top level (sibling to `2026/`).
- Fantrax / NFBC data — could get their own top-level tabs once you're ready,
  same pattern as the year tabs.
- If this grows large, a static site generator (like Eleventy or Hugo) could
  reduce repetition, but plain HTML is totally fine for this scale.

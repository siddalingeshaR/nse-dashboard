# NSE Dashboard — Cloud Setup Guide

Your dashboard will run entirely in the cloud (free). GitHub fetches the data
every evening and hosts the dashboard as a website you can open on any device —
your phone, your Mac, anywhere. Your Mac no longer needs to be involved.

---

## What you're setting up

- **GitHub Actions** runs `fetch_data2.py` every day at **8:00 PM IST** on GitHub's servers
- The fresh data is saved automatically
- **GitHub Pages** hosts your dashboard at a public URL
- You bookmark that URL on your Samsung Z Fold 6

No terminal needed. This is all done through the GitHub website with clicks.

---

## STEP 1 — Create a free GitHub account

1. Go to **https://github.com/signup**
2. Enter your email, a password, and a username (e.g. `srikanth-nse`).
   - Your username becomes part of your dashboard URL, so pick something clean.
3. Verify your email. Done — it's free.

---

## STEP 2 — Create a new repository

1. Once logged in, click the **+** icon (top-right) → **New repository**
2. Repository name: **nse-dashboard**
3. Set it to **Public** (required for free GitHub Pages)
4. Do NOT check "Add a README" (we have our own files)
5. Click **Create repository**

You'll land on an empty repo page. Keep it open.

---

## STEP 3 — Upload the files

On the empty repo page:

1. Click the link **"uploading an existing file"** (in the quick-setup text),
   or go to **Add file → Upload files**.
2. Open the `nse-cloud` folder I gave you on your computer.
3. **Drag ALL the contents** into the upload box — including the hidden
   `.github` folder. Easiest way: select everything inside `nse-cloud`
   (fetch_data2.py, docs folder, .github folder) and drag them in together.
   - If the `.github` folder won't drag, see the note at the bottom.
4. Scroll down, click **Commit changes**.

Your files are now on GitHub.

---

## STEP 4 — Turn on GitHub Pages (the website)

1. In your repo, click **Settings** (top menu).
2. Left sidebar → **Pages**.
3. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/docs**
   - Click **Save**.
4. Wait ~1 minute. The page will show:
   **"Your site is live at https://YOURNAME.github.io/nse-dashboard/"**

That link is your dashboard. Open it on your phone. Bookmark it.

---

## STEP 5 — Turn on the daily auto-fetch

1. In your repo, click the **Actions** tab.
2. If it asks to enable workflows, click **"I understand my workflows, enable them"**.
3. You'll see **"Daily NSE Data Fetch"**. Click it.
4. Click **Run workflow → Run workflow** to do a first fetch right now
   (don't wait until 8 PM for the first one).
5. It takes a few minutes. When the green check appears, your real data is live.
   Refresh your dashboard URL — the 1,681 stocks will be there.

From now on it runs automatically every day at 8:00 PM IST. You do nothing.

---

## Daily use

- Open your bookmarked URL on your phone or Mac: it always shows the latest data.
- The data refreshes every evening on its own.
- To check when it last updated, look at the "Last fetched" line at the top of
  the dashboard.

---

## To trigger a manual refresh anytime

Repo → **Actions** → **Daily NSE Data Fetch** → **Run workflow**.
A few minutes later the dashboard shows fresh numbers.

---

## Note: if the `.github` folder won't upload by dragging

The `.github` folder is hidden on some systems. If dragging doesn't work:

1. On the GitHub repo page: **Add file → Create new file**
2. In the filename box, type exactly:
   `.github/workflows/daily-fetch.yml`
   (typing the slashes creates the folders automatically)
3. Open the `daily-fetch.yml` file I gave you in TextEdit, copy all of it,
   paste it into the GitHub editor.
4. Click **Commit changes**.

Then upload the rest (fetch_data2.py and the docs folder) normally.

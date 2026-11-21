# Time Doodle: put it online for free (GitHub Pages)

You get a free web address like `https://YOUR-USERNAME.github.io/timetable/`. No domain to buy.
GitHub Pages only hosts files, so the live updates are stored in a free Firebase database. Do Part 1 first.

## Part 1. Create the database (Firebase, free)

1. Go to https://console.firebase.google.com and sign in with a Google account.
2. **Add project**, name it `shared-timetable`, turn Google Analytics off.
3. Left menu: **Build > Realtime Database > Create Database**. Pick a region near you. Choose **locked mode**.
4. Open the **Rules** tab, delete everything, paste the contents of `firebase-rules.json`, click **Publish**.
5. Click the gear icon > **Project settings > General**. Under **Your apps** click the web icon `</>`, register an app, and copy the `firebaseConfig` values.
6. Open `index.html` in a text editor. Find `PASTE YOUR FIREBASE SETTINGS HERE` and replace the five placeholder values. If `databaseURL` is missing, copy it from the top of the Realtime Database page.

These settings are not secret. The rules file is what protects the data.

## Part 2. Publish on GitHub Pages

1. Create a free account at https://github.com if you don't have one.
2. Click **New repository**. Name it `timetable`, keep it **Public**, click **Create repository**.
3. Click **uploading an existing file**, drag in `index.html`, then click **Commit changes**.
4. Go to **Settings > Pages**. Under **Build and deployment** choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
5. Wait about a minute and refresh the Pages screen. Your link appears at the top. Open it, join, then send the link to your friends.

## Changing the page later

1. On GitHub open `index.html`, click the pencil icon, edit, and click **Commit changes**.
2. Wait about a minute, then refresh the site with Ctrl+Shift+R (Cmd+Shift+R on Mac).

Where to change things inside `index.html`:
- **Colors:** the `:root{...}` lines at the top of the `<style>` block (`--accent`, `--free`, `--busy`, `--all`). The dark-mode set is the next line.
- **Fonts:** the Google Fonts `<link>` in the head, and the `font-family` lines (`Caveat Brush` for titles, `Patrick Hand` for text).
- **Timetable background:** the CSS block marked `animated paper-and-doodles background`. Remove the `animation:` lines to make it still, or change `opacity` to make it softer.
- **Brushes (Work, Sleep, ...):** the `BR` list in the script.
- **Countries and time zones:** the `COUNTRIES` list in the script.

## Notes

- Anyone with the link can edit any column. That is fine for friends, so don't post the link publicly.
- Plans are stored by each person's own local hour, so daylight saving changes are handled automatically.
- To delete your data, use **Remove my column** in the page, or delete entries in the Firebase console.
- The free Firebase plan is far more than this page needs.

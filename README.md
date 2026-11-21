# Time Doodle

A lightweight, real-time collaborative timetable for coordinating schedules with friends across different time zones. Paint your daily routine onto a shared board, share the link, and instantly see when everyone is free.

**Live App:** https://YOUR-USERNAME.github.io/timetable/

## Features

- **Real-Time Sync:** Changes appear live for everyone viewing the board using Firebase Realtime Database.
- **Automatic Time Zone & DST Conversion:** Schedules are stored in each person's local hour, automatically adjusting for time zone differences and daylight saving shifts.
- **Brush Presets:** Quickly block out time using color-coded brushes (Work, Sleep, Free, Busy) and switch between light and dark themes.
- **Zero-Friction Access:** No sign-ups required—just open the link, add your column, and share it with your group.
- **Easy Cleanup:** Remove your own column anytime directly from the interface.

## Run Your Own Copy

If you want to host your own private instance of Time Doodle:

### 1. Set up Firebase
1. Create a new project in the [Firebase Console](https://console.firebase.google.com) (Google Analytics is not needed).
2. Navigate to **Build > Realtime Database > Create Database**, select your region, and start in **locked mode**.
3. Open the **Rules** tab and apply your database security rules (from `firebase-rules.json`), then click **Publish**.
4. Go to **Project settings > General**, register a new **Web app** (`</>`), and copy the `firebaseConfig` object.

### 2. Configure & Deploy
1. Open `index.html` and locate `PASTE YOUR FIREBASE SETTINGS HERE`.
2. Replace the placeholder keys with your `firebaseConfig` values (grab `databaseURL` from the top of your Realtime Database dashboard if it isn't included).
3. Push `index.html` to a public GitHub repository.
4. Go to **Settings > Pages**, set the source to **Deploy from a branch** (`main` / `/ (root)`), and save. Your live link will be ready in about a minute.

## Customization

All styling and configuration live directly inside `index.html`:
- **Theme Colors:** Edit the CSS variables (`--accent`, `--free`, `--busy`, `--all`) inside `:root` at the top of the `<style>` tag (dark mode variables follow right below).
- **Typography:** Swap the Google Fonts `<link>` in `<head>` and update the `font-family` rules (`Caveat Brush` for headings, `Patrick Hand` for body text).
- **Background:** Modify `opacity` or remove `animation:` inside the `animated paper-and-doodles background` CSS block.
- **Brushes & Regions:** Update the `BR` array to change brush labels/colors, or edit `COUNTRIES` in the `<script>` tag to adjust available time zones.

## Privacy Note

Anyone with your board's URL can view and edit columns on that board, so only share your live link directly with the people you are planning with.

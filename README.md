📅 Jellyfin Calendar Tab
A custom tab for Jellyfin that opens a "Coming Up" popup directly on the home screen — styled with a glassmorphism effect to match the Ultrachromic theme.

✨ Features
Integrated UI: Calendar icon tab placed next to Bookmarks, Watchlist, etc.

Glassmorphism Popup: Click opens a sleek overlay over the home screen — no page navigation.

Smart Date Range: Automatically shows only the next 7 days from today.

Series Focus: Always loads series posters (not episode thumbnails) for a cleaner look.

Direct Navigation: Click on a card opens the series detail page instantly.

Easy Exit: Close via the ✕ button or ESC key.

Themed: Specifically designed to match the Ultrachromic / Kaleidochromic visual style.

📸 Screenshots
Home Screen Integration
Calendar Popup View
<img width="1440" height="900" alt="Bildschirmfoto 2026-03-31 um 16 15 03" src="https://github.com/user-attachments/assets/ef18ed8b-43d4-494b-8cb5-b412060245a5" />

<img width="1440" height="900" alt="Bildschirmfoto 2026-03-31 um 15 52 04" src="https://github.com/user-attachments/assets/a34047f4-7d50-4aa4-86ba-cafe36635489" />

📋 Requirements
Jellyfin Server 10.8+

Plugin: Custom Tabs — required for the tab button to appear.

🚀 Installation
Step 1 — Create the Custom Tab ⚠️ Required
The Custom Tab plugin is required. Without it, the tab button will not appear on the home screen.

Open the Jellyfin Dashboard.

Go to Plugins → Custom Tabs.

Click Add Tab and fill in:

Display Text: Calender ← must be spelled exactly like this (the script looks for this string).

HTML Content: Leave completely empty.

Save.

⚠️ The tab name must be Calender. The JavaScript searches for a tab button whose text contains calend — if you rename it, the script will not find the trigger.

Step 2 — Add the JavaScript
Go to Jellyfin Dashboard → General → JS Injector.

Paste the full contents of calendar.js into the Custom JavaScript field.

Save and reload the page.

📁 Files
File	Description
calendar.js	Main script — tab patching, popup logic, API calls.
custom.css	Full CSS including Ultrachromic imports and tab icon styles.
README.md	This documentation.
⚠️ Important Logic & Known Issues
Empty Days: If a specific day (e.g., Thursday) has no scheduled releases in your library, that heading will be skipped and not displayed at all.

Missing Data: If the Jellyfin API provides no data/items for the entire 7-day range, the calendar will remain empty or not show items for those specific dates.

API Filtering: The Shows/Upcoming API ignores MinPremiereDate / MaxPremiereDate parameters in some versions, so the script loads up to 500 items and filters them client-side.

Scope: The tab only appears on the Home Screen, not on library subpages (Series, Movies, etc.).

📄 License
MIT — free to use and modify.

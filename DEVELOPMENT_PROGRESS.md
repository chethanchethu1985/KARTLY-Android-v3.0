# KARTLY (Smart Grocery & Pantry Management) - Android - Development Progress

Current package: Version 3.0 (versionName 3.0.0, versionCode 30). App name on the phone: KARTLY. Designed by CB.

## Milestones
| # | Milestone | Status |
|---|---|---|
| M1 | v2.4 base: signing key, 8 s splash, stray symbol fix, compact layouts, partial-purchase aids | DONE |
| M2 | v3.0: KARTLY branding (English + Kannada), new cart logo (icon, splash, header), light green/yellow theme from the logo, animated splash with Designed by CB + version at the bottom, Designed by CB footer, tab and button renames (Add Items, Available Items, Shopping List, Shopped), pencil-style background art (groceries / medicines / stationery) at about 13% opacity, critical partial-purchase fix, UI review and polish | DONE (tested in headless Chromium at phone size; APK build not run here) |
| M3 | Device test of the built APK, fixes | PENDING (needs user feedback from the phone) |
| M4 | Bill photo reading and Kannada translation for names outside the catalog (needs decision: own API key vs offline) | PENDING |
| M5 | Signed release APK instructions | PENDING |

## Critical fix in 3.0
After a partial purchase the item stays in the shopping list for the remainder, and the old Available Items filter hid every item that was still in the shopping list, so the bought part looked missing. Available Items now shows an item whenever its stock is above zero, with a tag "Pending N in shopping list". Verified: planned 10, bought 4 -> Available Items shows 4, Shopping List keeps 6.

## Review notes (3.0)
- No horizontal overflow on any tab at 390 px; no JavaScript errors in the browser sweep.
- Expiry popup now waits until the splash screen is gone.
- Flows verified: add item, move to shopping list, partial and full purchase, medicine stock days-left, add stock, shopped, stationery add/edit/delete.
- Splash: logo and glow animation, name, Kannada line, English and Kannada descriptions; progress bar for 8 s; Designed by CB and Version 3.0 at the bottom.
- Background art strength is the CSS opacity in `body::before` (0.13). Change it to adjust.

## Known issues and notes
- Installing 3.0 over 2.3.1 is not possible (different signing key). Export a backup in the old app, uninstall, install 3.0, restore. From 3.0 on, all builds use signing/grocery-debug.keystore and update in place. Keep that file in the repository.
- Bill photo reading is not available in the Android build yet.
- APK build and phone testing for 3.0 not yet done.

## Resume rule
New session: read this file and continue from the first milestone not marked DONE.

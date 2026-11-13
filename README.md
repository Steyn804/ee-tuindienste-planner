# E&E Tuindienste · Day Planner

Plan landscaping work: clients, a day/week/month calendar, the most efficient driving order for each day, routes in Google Maps, and printable PDFs.

## How it's put together
| File | What it is |
|---|---|
| `index.html` | The whole app (screens, route planner, map pin picker, PDFs) |
| `config.js` | Firebase settings for the shared database |
| `firestore.rules` | Who may use the data (list of email addresses) — paste into Firebase |
| `manifest.webmanifest`, `icons/`, `sw.js` | Lets the app be installed on phones/computers and work offline |

Clients and bookings live in **Firebase Firestore**, not in these files, so updating the app never touches the data.

## Updating the app
Ask Claude for the change and say the repo is `ee-tuindienste-planner`. Claude edits the files and commits them here; GitHub Pages republishes automatically within a minute or two. Installed apps pick up the new version the next time they're opened (close and reopen once if needed).

## Adding or removing a person
1. Firebase console → Authentication → Users → **Add user** (email + password).
2. Firebase console → Firestore Database → **Rules** → add their email to the list → **Publish**.

## Installing on a device
- **iPhone/iPad (Safari):** open the site → Share → *Add to Home Screen*.
- **Android (Chrome):** open the site → ⋮ menu → *Install app* / *Add to Home screen*.
- **Computer (Chrome/Edge):** click the install icon at the right of the address bar.

## Maps
Pin picking uses OpenStreetMap (© OpenStreetMap contributors) and Nominatim search. Routes open in Google Maps.

# Travel Journal

The app lets users record and organise travel-related information - notes, photos, and visited locations - and keeps everything accessible without an internet connection. Data is stored locally on the device and synced to a remote server when connectivity is available.

## Chosen Technical Direction

- **Language:** Kotlin
- **UI framework:** Jetpack Compose (Material 3)
- **Minimum SDK:** 26
- **Target SDK:** 37
- **Build system:** Gradle (Kotlin DSL)

## Screens

- **Home:** shows aggregate statistics since the user started using the app (how many trips taken, countries visited, media files stored) and the list of recent visits.
- **Journal:** lets the user select a date and view or add notes recorded for that day.
- **Map:** shows saved locations, lets the user build a "Future visits" list, and calculates the approximate straight-line distance from the current device location to a saved place.

## Offline behaviour

- The user can still create, view, and edit entries with no signal.
- Location can be entered manually if GPS is unavailable.
- GPS does not inherently require a network connection, though acquiring a position may be slower or unavailable in some conditions - the app handles that case.
- Unsynced notes and media are pushed to the server once connectivity is restored.

## The data

- **What records does the app create or collect?** The app both creates and stores text and multimedia files in an organized and easy-to-follow manner.
- **Where does data come from?** User input and location, camera.
- **Where does data need to go?** The data is stored both locally and on a remote server for sync and backup.

## Mobile-computing framing

- **What must persist on the device:** Notes and associated multimedia files that have not yet been backed up.
- **What crosses the network:** The locally stored travel information goes to a server if it has not been backed up yet (when the connection allows it); if the user requests it, the local data can be synced with the one present within the server (in case of information loss on the device).
- **What must still work with no signal:** The user can still create, view, and edit entries. They can enter a location manually and use already stored locations. GPS also does not inherently require a network connection, though obtaining a position may be slower or unavailable in some conditions. The app must handle that case gracefully.
- **Computations' placement:** The location computations are determined on demand, based on the current latitude and longitude. For a saved entry that has coordinates, the app calculates its straight-line geographic distance from the actual location (e.g., using Android's distance utilities or the Haversine formula). These calculations are small, do not need a server, and can work offline. An on-demand location request is favored over continuous tracking to limit battery use and unnecessary data collection. The tradeoff is that location may be unavailable or stale, and manually entered coordinates may be inaccurate.

## Quick Start

1. Clone the repository.
2. Open the project in Android Studio.
3. Connect a physical device or start an emulator running API 26 or higher.
4. Build and run the `app` module.

## Repository Layout

- `app/`: Android application module.
- `app-idea.md`: initial application concept and scope definition.
- `reflection.md`: prototype reflection and gap analysis.
- `AI-USE-LOG.md`: log of AI-assisted development sessions.

## Team members

- Arpășanu Emilia-Oana - SSA2
- Eremia Silvia - SSA2
- Mogodeanu Claudiu - SSA2
# Mobile Computing project

- **App name:** Travel journal
- **One-line pitch:** The app lets the user keep their holiday itinerary and memories organized, anywhere, anytime
- **The problem:** Most of the time travellers use multiple solutions in order to store the important info and they get mixed up or unaccesible when the network connection is lost
- **Target users:** People who are always on-the-go and need need to keep track of their travel details while using transportation with limited access to the Internet (airplane, train, etc.)

## The prototype scope

- **Core screen(s):** The main app page shows the global statistics since the moment the user started using it (how many trips have been taken, how many countries have been visited so far, how many memories have been stored - pictures, videos, etc.) and the list of the latest visits; at the bottom of this screen lies the main menu, from where the user can select the "Journal" and "Map" pages to navigate to. The "Journal" screen lets the user select a certain day and visualize the notes that were written then, with the ability to add new ones. The "Map" section show the exact places the user visited, offer nearby suggestions to go to based on the current location and lets create a "Future visits" list; optionally, the user can see the approximate straight-line distance from the current device location to a preffered place
- **The main data that the app works with:** Files created in a given place (photos, videos) and notes about the trip
- **Stored data information:** title, date, location, notes' content, pictures, videos

## The data

- **What records does the app create or collect?** The app both creates and stores text and multimedia files in an organized and easy-to-follow manner
- **Where does data come from?** User input and location, camera
- **Where does data need to go?** The data is stored both locally and on a remote server for sync and backup

## Mobile-computing framing

- **What must persist on the device:** Notes and associated multimedia files that have not yet been backed up
- **What crosses the network:** The locally stored travel information goes to a server if it has not been backed up yet (when the connection allows it); if the user requests it, the local data can be synced with the one present within the server (in case of information loss on the device)
- **What must still work with no signal:** The user can still create, view, and edit entries. They can enter a location manually and use already stored locations. GPS also does not inherently require a network connection, though obtaining a position may be slower or unavailable in some conditions. The app must handle that case gracefully
- **Computations' placement:** The location computations are determined on demand, based on the current langitude and longitude. For a saved entry that has coordinates, calculate its straight-line geographic distance from the actual location (e.g., using Android's distance utilities or the Haversine formula).
These calculations are small, do not need a server, and can work offline. We favor an on-demand location request instead of continuous tracking to limit battery use and unnecessary collection. The tradeoff is that location may be unavailable or stale, and manually entered coordinates may be inaccurate
# Prototype reflection: where AI stopped

## What AI did well

The use of AI helped prototype the main screens (home and journal notes) while populating the UI elements with sample data in order to easily visualize the app concept.

## What broke when you stressed it

Go through the checks from Part 4 and record what actually happened.

- **Rotate the device:** For the journal notes screen the rotation determined the newly added notes to disappear due to the lack of view models
- **Kill and reopen the app:** Nothing new was saved
- **Two people editing the same data:** The data is local on the device and only the current user can edit it

## What is missing for production

| Gap in the prototype | Lab that fixes it |
|---|---|
| No separation of UI and logic; state resets | Lab 4 (architecture) |
| No data from a real server | Lab 5 (networking) |
| Nothing is saved on the device | Lab 6 (persistence) |
| Does not work offline; no background sync | Lab 7 (offline-first, WorkManager) |
| Dependencies wired by hand | Lab 8 (dependency injection) |
| No tests; nothing stops a broken change | Lab 9 (testing, CI) |
| No mobile-computing concept beyond a UI | Lab 10 (integrated concept) |

## One sentence

In your own words: what is the difference between what AI gave you today and a production app, and why
can AI not simply close that gap for you?

> A production app includes all critical functionalities and at the moment AI only produced a mock version of what we should have in the end; furthermore, it lacks statefullness, a main requirement for a smooth user experience while creating data 
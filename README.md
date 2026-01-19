# ITUNA-CAMPUS - Realtime demo (Firebase Realtime Database)

This branch adds a minimal realtime demo (chat + presence) using Firebase Realtime Database.

Setup steps
1. Create a Firebase project at https://console.firebase.google.com/.
2. In Project settings -> General -> Add web app. If you already provided the project's web config, it's already in `index.html`.
3. In Build -> Realtime Database, create a database (choose a location). For quick testing use "Start in test mode" then configure rules for production later.
4. Optionally enable Firebase Authentication -> Sign-in method -> Anonymous (used by the demo).
5. Open `index.html` in a browser (or deploy to Firebase Hosting).

Security notes
- The `databaseURL` in `index.html` may be auto-detected, but if realtime connections fail, double-check the Realtime Database URL in your Firebase console and update the `databaseURL` property in `firebaseConfig`.
- Test mode DB rules are open. Before going to production, update rules to restrict write/read only to authenticated users or protected paths.

What I added in the demo
- Anonymous auth to provide a uid
- Presence: stores `/presence/{uid}` and removes it on disconnect
- Realtime messages: writes to `/messages` and listens with `onValue` for realtime updates

Next steps I can do for you
- Add Firestore alternative instead of Realtime DB
- Add authentication UI (email/password, Google sign-in)
- Add Firebase Cloud Functions for server-side validation or enrichment
- Deploy to Firebase Hosting and set up CI/CD

Commit: feat: add Firebase Realtime Database demo (chat + presence)
Branch: feat/realtime-firebase

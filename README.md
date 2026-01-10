# ITUNA-CAMPUS - Realtime demo (Firebase Realtime Database)

This branch adds a minimal realtime chat + presence demo using Firebase Realtime Database.

Quick start
1. If you haven't already, create a Firebase project at https://console.firebase.google.com/.
2. In the Firebase console enable Realtime Database (Build → Realtime Database) and create a database.
   - Note the database URL (it looks like `https://<your-project>-default-rtdb.firebaseio.com`). If you used the Firebase web setup to add a web app, the config will include `databaseURL`.
3. In Authentication → Sign-in method enable Anonymous sign-in (used by the demo).
4. If needed, update the `databaseURL` in `index.html` to match your database URL.
5. Open `index.html` in a browser (or serve it) and test sending messages. Messages are written to `/messages` and presence to `/presence/{uid}`.

Security
- For quick testing you can set Realtime Database rules to test mode, but do not leave them open in production.
- Example production rules that require authentication for writes/reads:

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

What I changed
- Added `index.html` with a realtime chat and presence demo using Firebase Realtime Database.
- The Firebase config in `index.html` was filled with the values you provided; you may need to add the `databaseURL` from your Firebase console if it's different.

Next steps I can do for you
- Create a pull request with these changes.
- Add authentication UI (email/password, Google sign-in).
- Harden Realtime Database rules and add Cloud Functions for server-side validation.

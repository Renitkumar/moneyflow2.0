# MoneyFlow 2.0

Firebase + Vercel finance app.

Important deployment steps:
1. Deploy the included `firestore.rules` to Firebase Firestore.
2. Deploy `api/admin.js` and `api/user.js` with the project on Vercel.
3. Set Vercel environment variables: ADMIN_UID, FIREBASE_PROJECT_ID, FIREBASE_CLIENT_EMAIL, FIREBASE_PRIVATE_KEY, ADMIN_SELF_DELETE_PASSCODE.
4. The user transaction delete passcode is assigned/changed by the admin from Admin Panel.
5. User transaction deletion is performed through `/api/user?action=deleteTransaction`; users cannot delete directly through Firestore rules.


## Vercel deployment note
No functions runtime is pinned in vercel.json. Vercel auto-detects api/*.js as Node.js Functions. package.json pins Node 24.x.

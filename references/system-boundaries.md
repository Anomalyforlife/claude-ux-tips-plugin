# Client/server boundary, offline, and onboarding

## 3. The most common dark patterns (to avoid)


- **Confirm shaming**: "no" options worded to make you feel guilty.
- **Hidden costs**: low initial price, extra costs hidden at checkout.
- **Roach motel**: one-click signup, deliberately complicated cancellation.


## 65. What really happens when the user clicks "buy"


- The browser validates the form locally before sending any network request — instant feedback is the frontend's job.
- The backend **always** revalidates everything: client input is never trustworthy.
- Stock, price, and payment are verified server-side; the database write happens in a single atomic transaction (all or nothing commit).
- The UI redraws based on the real data returned by the server, not on a prediction.
- Only "lightweight" actions (like, rename) can afford optimistic UI — a payment must always show the real spinner.


## 80. Onboarding: the first minute decides everything


- Get the user to their first "aha moment" in as few steps as possible, deferring advanced configuration to later.
- A tour with too many tooltips in sequence gets dismissed without being read: prefer 1-2 contextual hints at the right moment.
- Ask only for the data strictly necessary to get started; the rest of the profile gets completed progressively (progressive disclosure).
- Show sample data/content (seed data) instead of a totally empty state, so the user immediately understands what to do.


## 83. Offline-first: continuing to work without a network


- Always distinguish "offline" from "slow request": an explicit banner ("you're offline") prevents the user from mistaking the disconnection for a bug.
- Actions performed offline should be queued locally and synced on reconnection, not simply lost or blocked.
- Clearly show which data is already available from cache (and potentially outdated) versus what's missing.
- In case of conflict between offline changes and updated server data, ask the user how to resolve it instead of silently overwriting.
- A service worker with cache-first for static assets keeps the app usable even on an unstable connection.

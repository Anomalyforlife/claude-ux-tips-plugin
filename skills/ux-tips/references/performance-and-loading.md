# Perceived performance, loading, and waiting

## 19. Skeleton screen: details that make the difference


- A spinner communicates "wait", a skeleton communicates "it's coming" — it reduces anxiety.
- The shimmer must move in the **reading direction** (left→right), the opposite feels "wrong".
- Don't use generic rectangles: match the skeleton's shape to the real content (circle for avatar, short lines for names).
- Next level: **optimistic UI** — show the action's result immediately and roll back only if the server errors.


## 24. How to choose the right loading state


- **Skeleton**: when you know the shape of the content and the wait exceeds 300ms.
- **Spinner**: short waits (<3s) when you don't know the duration.
- **Progress bar**: when you know the percentage (upload, installs over 3s).
- **Optimistic UI**: for actions that succeed 99% of the time (like, save) — show immediately, roll back if it fails.
- Under 300ms show nothing: a flash of loading reads as a bug.


## 52. When to validate a form field (timing matters more than the rule)


- Validating only on submit forces the user to discover 10 errors all at once, all in red.
- Validating on every keystroke punishes the user mid-word (e.g., email "invalid" on the first letter).
- **On-blur validation** (when the user leaves the field) is the right compromise.
- After a first error, switch to live validation on that field to confirm the fix in real time.
- A green check is as much feedback as a red error — don't just flag what's wrong.


## 53. UX writing: words matter as much as layout


- "Submit" says nothing; "Create my free account" communicates the benefit.
- A useful error suggests the solution ("this email is already in use, want to sign in?") instead of just flagging the problem.
- An empty state is the best opportunity to teach the first action to take.
- The placeholder is not a label: it disappears as soon as the user types, leaving them without context.
- Write like a person, not like a server ("operation failed" is never something anyone says in real life).


## 54. Optimistic UI: when to pretend it's already done


- Under 400ms an action is perceived as instant; beyond that, a spinner looks like a malfunction even if everything is fine.
- Update the interface immediately and sync in the background, with rollback on error.
- Works well for actions that are 99% reversible (like, save, bookmark).
- **Never** apply it to payments, transfers, or non-reversible actions — there, show the real state, even if it's "please wait".


## 62. Checklist for a quick UX audit of AI-generated interfaces


- Automatically generated interfaces often replicate the database schema 1:1 (12 columns, delete next to edit) instead of thinking about the user.
- Always ask: who will use this page, and what's the worst mistake they could make?
- Destructive actions must be protected (confirmation via typing), search should often be the primary action.
- Specify every state (loading, empty, error, success, offline, partial) before writing code, not after.
- On an already-live interface, a systematic audit should produce a list of fixes ordered by severity, not generic advice.


## 63. Auto-save: a reliable state, not just an icon


- Use a debounce (e.g., 800ms pause in typing) before saving, not on every keystroke.
- Communicate the state with a text pill (typing/saving/saved/offline/error) — the user trusts this indicator more than the feature itself.
- While offline, queue changes locally with a badge showing the count, and flush the queue in order upon reconnection.
- With multiple tabs open on the same document, don't silently overwrite: merge or explicitly warn.
- If the user tries to close with unsaved changes, block the close with a browser warning.


## 72. Skeleton vs. real content: avoiding layout shift


- The skeleton's dimensions must exactly match those of the final content (row height, image width) or you get a visual jump (CLS).
- Always reserve space for images/iframes with `aspect-ratio`, never let the layout "jump" when the asset loads.
- Web fonts need a fallback with similar metrics (`font-display: swap` + system font) to avoid shifting the text on load.
- Dynamic banners and notifications should be inserted with a height animation, not a simple "pop" that pushes the content below.


## 82. Long lists: virtualization and perceived performance


- Beyond a few hundred items, render only the rows visible in the viewport (windowing) — a DOM with thousands of nodes slows down scroll and interaction.
- Keep a buffer of rows above/below the viewport (overscan) to avoid white flashes during fast scrolling.
- If rows have variable height, measure and store the real heights instead of estimating them: a wrong estimate makes the scrollbar "jump".
- Preserve scroll position when new items are added at the top (e.g., chat, feed), otherwise the user loses their reading point.
- Data fetching should be paginated in parallel with virtualization: never load the entire dataset just to render part of it.


## 85. Micro-copy for long waits: don't leave the user in the dark


- Beyond 5-10 seconds, replace a generic spinner with progressing status messages ("preparing your data…", "almost done…").
- If the duration is known (e.g., file processing), show an estimated time instead of an indefinite wait — even if approximate, it reduces anxiety.
- Vary the message if the wait runs longer than expected ("this is taking longer than usual, hang tight") instead of repeating the same text.
- Always offer an explicit way out for very long waits (cancel, continue in the background and notify on completion).
- The language of waiting messages must stay human and reassuring, never technical ("processing" beats "processing job #4471").

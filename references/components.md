# UI components (form, nav, data, overlay)

## 15. The principle of proximity (Gestalt)


- Nearby elements are perceived as connected, distant ones as separate — the brain does this automatically.
- Group elements by **function** (e.g., navigation, actions, settings), not by equal spacing.
- In forms, group fields by context (personal data, address, payment) instead of aligning them all the same way.
- Good spatial grouping eliminates the need for graphic dividers.


## 22. Empty state: the wasted first impression


- An empty screen without an illustration communicates "something is broken" — even a small illustration changes everything.
- Write the copy in a human tone, not like an error log.
- Always offer a **clear primary action**, not just a "refresh".
- Distinguish the 4 types of "empty": first use, no results, error, filter with no match — each deserves a different design.
- The empty state is an onboarding opportunity, not just a fallback.


## 23. The rules of toast notifications


- **Position**: bottom-right on desktop, top on mobile — never in the center (it blocks interaction).
- **Timing**: info 4s, warning 7s, errors stay until the user dismisses them — a fixed timer for all of them is a bug.
- **Stacking**: max 3 visible, new ones push old ones with "spring" physics.
- **Always dismissible**: close button or swipe — otherwise it's a modal in disguise.
- **Color coding**: icon + colored border, not just the background (6% of users can't distinguish by color alone).


## 25. The 5 rules of a well-made dropdown


- Clear trigger: arrow, hover state, minimum 44px target.
- **Automatic flip** upward if there's no room below — never cut off the last item.
- Keyboard navigation required: arrows, enter, escape.
- Beyond 10 items add search; beyond 100, virtualize the list.
- Animate the opening under 150ms — fast enough to feel instant.


## 26. The rules of a tooltip that doesn't annoy


- Wait 300ms before showing it — instant tooltips just generate noise.
- Always use an arrow connecting the tooltip to its trigger.
- Flip it near screen edges so it isn't cut off.
- It must be dismissible in multiple ways: mouse out, escape, focus out, tap outside.
- Maximum 300px wide, one sentence — it's a hint, not documentation.


## 27. The 6 states of a form field (most apps implement only 2)


- **Default**: label always visible outside the field, never only in the placeholder.
- **Focus**: ring with minimum 3:1 contrast (the classic blue glow often fails accessibility).
- **Error**: color + icon + message — a red border alone is invisible to 12% of colorblind users.
- **Success**: green check inside the field, not a separate toast.
- **Disabled**: grayscale background (not just 50% opacity) + cursor not-allowed.
- **Loading**: internal spinner, disabled field — prevents the double-submit bug.


## 28. How to choose the right navigation pattern


- **Tab bar**: mobile only, max 3-5 main destinations.
- **Sidebar**: desktop only, for hierarchical content or more than 5 sections.
- **Hamburger**: only for secondary content — 40% of users click hidden menus less.
- **Command palette (Cmd+K)**: for power users, not as primary navigation for new users.
- **Breadcrumb**: only if the hierarchy exceeds 2 levels.


## 29. 5 fixes for error states that don't frustrate the user


- Distinguish the type of error (validation, network, server, permissions) — each deserves a different visual pattern.
- Always offer a way out: retry, refresh, contact.
- The surface depends on severity: inline for recoverable errors, toast for transient ones, modal only when you need to block everything.
- Use human language ("connection lost, reconnecting") instead of technical messages.
- Inline validation prevents 80% of errors before they happen.


## 34. Search as a system (5 components)


- The placeholder must concretely describe what can be searched (e.g., "search by name, SKU, or brand").
- Show **recent searches** when the input is focused instead of an empty field.
- Autocomplete should sort results by relevance/clicks, not alphabetically.
- Navigate results by keyboard (arrows, enter, escape).
- On zero results, suggest alternatives instead of a dead end.


## 35. Date range picker: from 6 clicks to 1


- Offer presets for 90% of cases (today, yesterday, last 7/30 days, last quarter).
- Show a preview of the range as the user hovers, before the second click.
- Show two months side by side for ranges that span different months.
- On mobile use a fullscreen bottom sheet, not a popover — vertically scrollable calendar.


## 36. A tab system without visual jumps


- The underline beneath the active tab must **slide**, never teleport.
- With more than 8 tabs, don't wrap to a new line: horizontal scroll with edge fade to indicate more content.
- Navigate by keyboard (arrows, home, end).
- On mobile: segmented control under 5 tabs, bottom sheet above — never just resize the desktop version.


## 37. Multi-step form: how to split a long form


- The brain processes 3 fields well at a time; 12 in a row cause cognitive fatigue/abandonment.
- Always show a progress indicator (bar, dots, step labels).
- Group fields by **context** (personal data, shipping, payment), not by arbitrary count.
- Validate each step immediately, not only at the end — an error in step 1 shouldn't surface at step 4.
- Save state at each step: losing the form once means losing the user forever.


## 38. Which surface to use for each type of notification


- **Toast**: minor events, auto-closes in 4s (add undo for destructive actions).
- **Banner**: persistent information, stays until the user dismisses it.
- **Modal**: only when a mandatory decision is needed before continuing — often overused.
- **Badge**: passive notification, stays until it's viewed.
- Choose the surface based on the **severity of the content**, not out of habit.


## 39. Anatomy of a believable toggle switch


- Proportions matter: rail width = 2× knob diameter.
- Animate multiple properties together (rail color, knob position, shadow, text) over ~250ms ease-out, not an abrupt snap.
- It must work with the keyboard (spacebar) with a visible focus ring and screen reader announcement.
- For a server request: show the flip immediately, spinner in the knob, rollback if the server rejects it.


## 40. UX of drag-and-drop in kanban-style boards


- Give 3 clear signals when an item is "grabbed": cursor change, visual lift, background fade.
- Drop zones must communicate first: insertion line on a column, highlight on a zone.
- Choose the snap based on the layout: structured columns → snap; free canvas (Figma) → free.
- After an unwanted drop, show a toast with **undo** — 5 seconds to cancel avoids user panic.


## 41. How to design an honest star rating


- The star fill should already react on hover, not only on click.
- Preview (hover) and selection (click) should be kept as two separate layers to avoid flicker.
- Don't round a 4.4 up to 5 full stars: show the real fraction with a partially filled star.
- Animate the fill with a small stagger (~30ms) between stars instead of a simultaneous pop.
- Pair the stars with a continuous ring that summarizes the average value at a glance.


## 43. Slider: details that seem small but aren't


- Extend the clickable area well beyond the thin line — the entire row should respond to drag.
- Visually fill the whole area to the left of the thumb to communicate the value before it's even read.
- If the values are discrete (volume, rating, price), snap to steps instead of an imprecise continuum.
- Show the exact value above the thumb during drag, then make it disappear.
- Also support keyboard input (arrows, home/end).


## 44. Live formatting of a credit card number field


- Group digits into blocks of 4 as the user types, not at the end.
- Recognize the brand from the first digit and immediately show the logo (Visa, Mastercard...).
- Keep the cursor position correct when automatic spaces are inserted.
- Don't flag an error on the first digit typed — validate on blur, not on keystroke.
- Automatically clean up pasted numbers with dashes/spaces instead of rejecting them.


## 45. Chip filters: a system, not a list of buttons


- Each chip has 3 states (idle, active, disabled) — if "active" looks too similar to "idle" the filter seems broken.
- Update the result count immediately on each tap, never silently.
- Always offer a "clear all" button when filters are stacked.
- On mobile, scroll chips horizontally with edge fade instead of wrapping.
- Keep active filters "pinned" at the top so it's clear why the list narrowed.


## 46. OTP/code input with multiple boxes


- Support pasting a complete code: automatically distribute it across all boxes.
- Automatically move to the next box on each digit, go back with backspace on an empty box.
- Treat the boxes as a single value internally, not as separate states.
- On mobile force the numeric keyboard and take advantage of SMS code autofill.
- Wrong code: shake, reset, focus on the first box — never silent feedback.


## 47. Command palette (Cmd+K): how to make it feel instant


- Use fuzzy matching (e.g., "STG" finds "Settings") with highlighting of matched letters.
- Group results (recent, actions, pages) instead of a flat list.
- Navigate entirely by keyboard: arrows, enter, escape.
- If empty, show recent commands instead of a blank screen.
- Commands requiring async data should show an inline loader, without blocking the whole palette.


## 48. Pagination: why "offset" breaks and "cursor" doesn't


- Offset pagination (skip N) breaks if the data changes — duplicated or skipped rows.
- Use **cursor**-based pagination (after this ID) for a stable list even with changing data.
- Choose the right pattern: numbered to jump to a page, "load more" for manual control, infinite scroll for feeds.
- With many pages, truncate the links (1 ... 499 500 501 ... 1000), always keeping the first and last reachable.
- Save the scroll position when returning from a detail view, and put the page in the URL to make it shareable.


## 49. File upload: communicating status honestly


- A drop zone must visibly react to drag-over (border, glow, text change) before the drop.
- Show percentage and estimated time, not just a generic spinner.
- If the upload fails at 90%, offer an inline retry that resumes from the file already uploaded, never from scratch.
- Show thumbnail, type, and size of the file as visual proof of what was received.
- With multiple uploads, each file has its own progress and retry — one failure shouldn't block the others.


## 50. Password strength: coach, not judge


- Real strength comes from length/entropy, not just the number of required symbols.
- Show the requirements checklist **while** the user types, with live checkmarks, not after submit.
- Use a strength bar that grows gradually instead of a binary judgment.
- Don't block pasting the password and offer a "show password" toggle.
- Offer automatic generation of a strong password with one tap.


## 51. Modern color picker: OKLCH instead of HEX


- OKLCH (lightness, chroma, hue) is more human-readable than hexadecimal.
- Save recent swatches and palettes for quick access.
- Check **contrast in real time** at the moment of choice, not in a later review phase.
- Show transparency over a checkerboard, not just a white background, to avoid misleading about actual alpha.
- From a single hue, automatically generate the entire tint/shade scale for the design system.


## 56. Undo instead of confirmation: a more human pattern


- A "are you sure?" penalizes everyone for one person's mistake; **undo** gives a second chance without friction.
- Treat deletion as a state (soft delete, 30 days in trash), not as an irreversible event.
- Reserve explicit confirmation only for truly irreversible actions (e.g., GitHub requires typing the repo name).
- An undo stack (like Figma's Cmd+Z) is more powerful than a single toast.
- Even a small delay before sending (e.g., Gmail, 10s) can prevent costly mistakes.


## 58. Context menu: a system, not a random list


- The menu must measure available space and flip/mirror to always stay within the viewport.
- Group actions by intent with dividers (e.g., rename/duplicate together, delete isolated in red at the bottom).
- For submenus, keep the menu open as long as the cursor stays within a virtual triangular area ("hover intent").
- Support keyboard navigation: arrows, letter to jump to an action, escape to close one level at a time.
- On mobile, long-press opens the same set of actions in a bottom sheet.


## 59. Destructive actions: hold-to-delete instead of "are you sure?"


- A loading ring during a prolonged press (~300ms) effectively replaces a confirmation dialog.
- Name the action in the button itself ("Delete project"), not a generic "yes/no".
- Never position a destructive button where muscle memory clicks automatically.
- Use red only for destruction: overusing it (e.g., on "logout") devalues it and makes "delete" feel less dangerous.
- A cooldown (e.g., 14 days before actual deletion) is a last line of defense.


## 60. UX of real-time multiplayer (shared cursors)


- Interpolate remote cursor positions so they move smoothly instead of "teleporting" between server updates.
- Assign a stable color to each user (hash of the ID) to make them recognizable at a glance.
- Show avatars of people present even before anyone speaks/acts.
- Visually lock an element being edited by another user to prevent conflicts (two people editing the same shape).
- Clicking a collaborator's avatar and following their viewport effectively replaces a screen share.


## 61. Inline editing: when text becomes an input


- Signal that text is editable with a subtle hover (pencil, light tint), don't leave it indistinguishable.
- The swap between static text and input must keep identical font, size, and padding — a single pixel off breaks the illusion.
- Enter confirms, escape cancels — also define what blur does (save or discard) and be consistent across the app.
- Update the UI optimistically right away, roll back showing the reason if the server rejects it.
- The more inline editing you offer, the higher the risk of accidental errors: calibrate based on the cost of a mistake.


## 64. Settings page: organizing it as a system


- Adapt the interaction to the "blast radius": toggles apply immediately, identity fields require explicit save/cancel.
- Group by task, not as a flat list — hide advanced options behind an extra click.
- Add internal search: power users search instead of scrolling through dozens of options.
- Visually flag each setting changed from default, with a quick way to reset it.
- Destructive actions should be isolated at the bottom, with confirmation via typing the name.


## 69. Disabled button: when it hides more problems than it solves


- A disabled button leaves the tab order: screen readers and keyboard navigation skip it without explanation.
- A tooltip on a disabled element often never triggers, because pointer events are disabled.
- Better to keep the button always active: on click, validate and highlight missing fields, moving focus to the first one.
- Always distinguish "disabled" from "loading": during a request the button should remain focusable and show a spinner, not disappear into gray.


## 70. Multiple checkboxes: correctly handling bulk selection


- The header checkbox has 3 states (checked, empty, partial) — removing the "partial" state makes the user lose track of what's selected.
- "Select all" often only selects visible rows: explicitly state the total number ("select all 247 matching rows"), updated based on active filters.
- Shift-click to select a range is expected behavior on desktop.
- The selection should be kept in app state, not in the visible rows — otherwise it's lost when changing pages.
- For bulk deletions, show the count in the action button instead of a confirmation modal, and offer undo for a few seconds afterward.


## 71. Data tables: beyond rows and columns


- Make the header and first column `sticky` when the table scrolls, so the user never loses context.
- Align numbers to the right and text to the left — the eye compares digits faster in a column.
- Zebra striping only helps with dense rows (>8): on few rows it's just visual noise.
- Column resizing should be saved per user, otherwise the same configuration is repeated every session.
- Sorting and filtering should go in the URL (query params), so the view is shareable and survives a refresh.


## 76. Breadcrumb and hierarchy: communicating "where am I" without ambiguity


- The last item (current page) shouldn't be clickable — it's already obvious where the user is.
- On narrow screens, truncate the middle levels with an expandable "…" instead of wrapping or shrinking the font.
- Each level must reflect the real navigation hierarchy, not the technical URL (slug, ID).
- Always pair the breadcrumb with a clear page title: the breadcrumb alone isn't enough to orient the user.


## 78. Rich text editor: the decisions nobody notices until they're wrong


- The toolbar must show the active state (bold pressed if the cursor is on bold text), not stay static.
- Pasting from Word/Google Docs must strip superfluous markup (fonts, spaces, empty spans), not carry it over as-is into the document.
- Standard keyboard shortcuts (Cmd+B, Cmd+I) must always work, even if the toolbar is hidden.
- The character/word count should update in real time but with debounce, so it isn't recalculated on every keystroke for long texts.

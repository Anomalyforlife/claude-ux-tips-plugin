# Accessibility, touch, and mobile

## 55. Focus state and keyboard accessibility


- `outline: none` without a replacement is an accessibility problem, not just an aesthetic one.
- A visible ring (2px, offset, adequate contrast on every background) is necessary for people navigating by keyboard.
- Use `:focus-visible` to show the ring only to keyboard users, not to mouse clicks.
- Focus order must follow the DOM, not the visual layout — watch out for reordering via CSS.
- Modals must trap focus inside them and return it to the trigger on close.
- An invisible but keyboard-reachable skip link lets users skip navigation.


## 57. Swipe gestures on mobile: communicating with haptic feedback


- A swipe has two thresholds: a short one reveals the buttons, a longer one crosses the "commit" point.
- During the gesture the row should resist like an elastic; at the commit point the icon "snaps" and the resistance disappears.
- Associate a direction with a consistent meaning (right = safe action, left = destructive) — never invert them.
- Gestures are invisible to new users: show a "peek" (partial preview) on first use to teach them.
- Even a quick swipe that deletes immediately should offer a brief undo.


## 68. Hover on touch devices: a common bug


- Mobile browsers "simulate" hover on the first tap, and the actions remain visible until the user touches elsewhere.
- Check the device type with media queries (`hover` and `pointer: coarse`), not user-agent sniffing.
- On mobile, move actions hidden behind hover into the card itself, into a swipe, or into a bottom sheet.
- Hover should reveal extra information, never contain the only way to reach a primary action.
- Touch targets must be at least 44px, even if the visual icon is smaller — widen the hit area, not the icon.


## 73. Mobile bottom sheet: a modal that respects the thumb


- It must be draggable to dismiss (drag-to-dismiss), not only via an X at the top, which is often out of thumb reach.
- Use multiple snap points (peek, half-screen, fullscreen) instead of a single fixed height.
- A small horizontal "grabber" at the top visually communicates that it's draggable.
- The content below must remain visible and slightly dimmed, never completely hidden, to preserve context.
- If the content exceeds the available height, only the inner area scrolls — the header with the actions stays fixed.


## 74. Contrast and readability: beyond the minimum WCAG ratio


- The 4.5:1 ratio is a minimum, not a target: for long text aim higher to reduce visual fatigue.
- Text over images requires an overlay (dark gradient) or a contrast check verified point by point, not a fixed value.
- Font size affects perceived contrast: large text (18px+ bold) tolerates a lower minimum ratio (3:1).
- Don't rely on color alone to distinguish states (links, errors): always add a second signal (underline, icon, weight).


## 75. Reduced motion: animations that respect user preferences


- Always respect `prefers-reduced-motion: reduce` — disable parallax, autoplay, and large transitions, not just slow them down.
- Replace position-based animations with simple fades when the user has requested reduced motion.
- Animations essential for understanding a state change (e.g., drag-and-drop) should be kept but shortened, not removed entirely.
- Always test with the preference enabled at the OS level, not just by reading the code.


## 79. Push notifications and permissions: timing is everything


- Don't ask for notification permission on first launch: the user declines because they haven't yet understood the value.
- Ask for permission right after an action that demonstrates the benefit (e.g., after setting a reminder).
- If permission is denied, don't ask again right away — explain where to re-enable it from settings when it's really needed.
- Segment notifications by type (the user can disable marketing but keep security ones).

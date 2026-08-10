# UI psychology, micro-interactions, and motion

## 1. Micro-interactions that bring an interface to life


- Use **"ease-out" easing**, not linear: linear movement feels robotic.
- Always give **immediate feedback** on tap: silence generates user anxiety.
- Apply the principle of **anticipation** (squash-and-stretch, from Disney 1937): a small "wind-up" before the main action makes it feel more natural.


## 2. Making an app feel faster (without actually changing its speed)


- **Skeleton screens**: show the layout before the content, not a blank screen.
- **Optimistic UI**: show the action's result immediately without waiting for the server's response.
- **Psychological progress bar**: make it start fast and slow down at the end — the user remembers the quick start.


## 4. The psychology of color in UI


- **Simultaneous contrast**: the same gray looks different depending on the background — context matters more than the absolute value.
- **Pop-out effect**: gray out everything except one element to guide the eye (don't color everything).
- **Color temperature**: red = urgency, blue = trust, green = success — use color as communication, not decoration.


## 6. The psychological mechanisms that make apps "addictive"


- **Variable rewards**: unpredictable content in the feed keeps the user scrolling (slot machine effect).
- **Zeigarnik effect**: incomplete tasks (progress bars, unseen stories) stay in memory until completed.
- **Loss aversion**: losing a streak hurts more than gaining one feels good — used to retain the user.
- **Social reciprocity**: a received like pushes users to reciprocate, keeping the app open longer than planned.


## 7. How apps eliminate every "exit point"


- **Pull-to-refresh**: the same gesture/uncertainty as a slot machine lever.
- **Infinite scroll**: eliminates the "keep going or stop?" decision typical of a "next" button.
- **Autoplay**: removes the natural pause after a video, preventing the moment of exit.


## 8. Every CSS property is a psychological decision (Stripe button case study)


- Background color = emotional tone (e.g., purple = trust).
- Rounded border-radius = perception of friendliness.
- Soft box-shadow = perception of premium/floating.
- Micro-hover (slight scale up) = communicates interactivity.


## 9. Why we prefer rounded corners to sharp ones


- **Sharp corners** activate the amygdala (evolutionary association with danger: thorns, claws).
- **Rounded corners** communicate safety and "you can touch this without getting hurt".
- Hence the historical evolution of buttons/cards toward increasingly softer shapes in digital products.


## 10. 3 psychological tricks for pricing cards that convert


- **Anchoring**: show the crossed-out high price first, the discounted price then looks like a deal.
- **Social proof**: a "most popular" badge removes decision doubt.
- **Loss aversion**: write "save 40%" instead of "pay less" — people fear losing more than they enjoy gaining.


## 12. Optical corrections that designers apply "by eye"


- Triangles/play buttons should be shifted toward the **visual centroid**, not the geometric bounding box.
- A circle must be ~13% larger than a square to appear the same size (the brain reads area, not pixels).
- In nested corner radii: `inner radius = outer radius - gap`, otherwise the corners look "squished".
- White text on a dark background appears "heavier" (irradiation illusion) — slightly reduce the font-weight in dark mode.


## 13. Fitts's Law applied to mobile design


- The time to reach a target depends on **distance** and **size**.
- Put primary actions **within thumb reach**, not at the top if the app is mobile.
- Moving the primary CTA a single time can raise the tap rate from 12% to 34% (cited example).
- Contextual menus, FABs, inline editing: all reduce the distance to the target to nearly zero.


## 17. How to create believable depth with shadows


- Combine 3 layers: tight **contact shadow** at the base, soft **elevation glow** behind, slight perspective shift.
- Color the glow with the brand color (e.g., purple on a purple app, blue on fintech) instead of using neutral gray.
- Shadow should be treated as part of the design system, not as an afterthought.


## 20. Applying the golden ratio (1.618) to design


- Scale spacing by multiplying by 1.618 (8 → 13 → 21 → 34...) for a natural rhythm instead of arbitrary padding.
- Divide the layout 61.8% / 38.2% (content on the large part, actions on the small one).
- Apply the same ratio to the typographic scale (body 16 → subheading 26 → heading 42 → display 68).
- Used by Apple, Stripe, Linear, and Airbnb in their layouts.


## 30. The right durations for each type of animation


- **Entrances**: 200-300ms (faster feels broken, slower feels heavy).
- **Exits**: 150-200ms, faster than entrances.
- **Feedback** (hover, press, toggle): under 100ms.
- **Attention** (errors, notifications): 500-800ms with bounce.
- **List stagger**: 50ms per item is the sweet spot.


## 31. The serial position effect applied to nav and landing pages


- People remember the **first** and **last** items of a sequence best (U-shaped memory).
- In nav: logo/brand at the start, conversion CTA at the end — middle items get forgotten.
- On landing pages: strongest value prop at the opening, strongest social proof at the close.
- Don't hide key content in the middle of the sequence — it's the "dead zone" of memory.


## 32. The Zeigarnik effect in onboarding


- Incomplete tasks stay in active memory longer than completed ones.
- An onboarding checklist with 1-2 uncompleted items pushes the user to come back and finish it.
- A 100% progress bar gets forgotten, an 80% one "chases" the user.
- Only works on tasks the user genuinely wants to complete — on irrelevant content (e.g., marketing emails) it only generates friction.


## 33. The peak-end rule


- The brain remembers an experience based on the **peak moment** and the **ending**, not the average.
- A flow of identical duration is remembered much better if it ends with a moment of delight (e.g., success animation) instead of just stopping.
- Design intentional peaks (aha moment, positive confirmation) — one delight beats five neutral interactions.
- Warning: if an almost-perfect flow ends with an error, the user will only remember that.


## 42. The rules for not lying with a chart


- Bar charts must **always** start from zero — truncating the axis exaggerates the differences.
- Use bar charts for comparisons, lines for trends over time; avoid pie charts beyond 5 slices (the eye can't compare angles well).
- Color must encode information (categorical/sequential/diverging), not decorate.
- Eliminate visual noise: heavy gridlines, 3D bars, shadows — every pixel should be data (Tufte's data-ink ratio).
- Label lines directly instead of using a separate legend.

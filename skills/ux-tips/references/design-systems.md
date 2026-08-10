# Design system, layout, and tokens

## 5. Why a card looks "cheap" (and how to fix it)


- Increase the internal **padding** (e.g., from 8px to 28px) for a more intentional look.
- Give each element its **own space** (avatar, text, image, actions).
- Increase the text's **line-height** (e.g., from 1.1 to 1.6) to let it "breathe".
- Spacing, not color or font, is often the real culprit behind the perception of quality.


## 11. The basics of a design system (color, typography, spacing)


- **Color**: start from a hue, use monochromatic (lightness variations), complementary (contrast), or analogous (harmony).
- **Typography**: use a fixed-ratio modular scale (display/heading/body/caption) instead of arbitrary sizes.
- **Spacing**: define a base unit (e.g., 8px) and always use multiples of it.
- Color + typography + spacing = atoms that make up buttons (molecules) and cards (organisms).


## 14. FigmaMake — from static mockup to interactive prototype (tool)


- Static mockups don't convey the real experience to stakeholders.
- With text prompts you generate animations/interactions while keeping the existing design system.
- Useful for going from PRD to a working prototype in a few minutes, without code.


## 16. The 3 types of white space


- **Micro white space**: internal padding of a button.
- **Macro white space**: margins between sections.
- **Active white space**: intentional generous spacing to guide the eye toward what matters.
- Doubling padding/gap (e.g., 16→32px, 8→16px) can make a card feel "premium" with the same content.


## 18. The grid system isn't "12 equal columns"


- The grid is a **system of ratios** (e.g., 4+8, 6+6, 3+9), not just fixed columns.
- At breakpoints the grid reconfigures (12 → 6 → 4 → 1), it doesn't disappear.
- The gutter is a design choice: 8px feels technical, 24px balanced, 40px editorial/luxurious.
- Intentionally breaking the grid (full-bleed hero, pull quote) creates contrast, not chaos.


## 21. The 5 pillars of a design system that works


- **Semantic color system**: name colors by purpose (background, brand, success, error), not by hex value.
- **Type scale**: intentional sizes/weights/line-heights for each level (display/heading/body/small).
- **Consistent spacing**: fixed base unit (e.g., 4px) and multiples for every margin/padding/gap.
- **Components with all states**: default, hover, active, focus, disabled — not just the happy path.
- **Motion with purpose**: consistent easing and duration (ease-out for entrances, ease-in for exits, max 300ms).


## 67. Extracting and reusing design tokens consistently (tool case study)


- Interfaces generated one at a time tend to diverge (different colors/styles on each screen) if they don't share a single system file.
- Before inventing new values, read what already exists (Tailwind config, CSS variables, most reused components) — the system is often already there.
- Every extracted token should have an explicit rationale recorded, not be "silently invented".
- Extensions to the system are allowed, but must be documented with the reason — that's how style drift happens.
- Forcing "one decision per axis" (type, color, spacing, finish) prevents a consistent but undistinctive result.

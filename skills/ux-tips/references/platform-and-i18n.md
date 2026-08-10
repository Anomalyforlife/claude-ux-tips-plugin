# Dark mode, internationalization, responsive images

## 66. Text overflow and truncation: edge cases to handle


- A flex child doesn't shrink below the size of its own text by default: `min-width: 0` is needed to make it work.
- For filenames or emails, truncate **in the middle** rather than at the end, to preserve the extension/domain (the most useful information).
- Use `font-variant-numeric: tabular-nums` for numbers that change frequently, to avoid the layout "jumping" on every update.
- Apply `overflow-wrap: anywhere` for long URLs that would otherwise blow out the container (the browser never breaks a word on its own).


## 77. Dark mode: it's not just inverting colors


- Pure black (#000) on OLED screens creates excessive contrast that causes fatigue: use very dark grays (e.g., #121212).
- Shadows don't work in dark mode: replace them with thin borders or brightness variations to communicate elevation.
- Saturated colors "vibrate" on a dark background: slightly desaturate semantic colors (success, error) compared to the light version.
- Images and illustrations often need a dedicated variant, not just an automatic inversion filter.


## 81. Internationalization and RTL layout


- Never hardcode `left`/`right` in CSS: use logical properties (`margin-inline-start`, `padding-inline-end`) for an automatic flip in Arabic/Hebrew.
- Directional icons (back/next arrows, chevrons) should be mirrored in RTL, but icons with universal meaning (play, check) stay unchanged.
- Translated text can take up to 30-40% more space (German, Finnish): don't fix rigid widths on buttons and labels.
- Format dates, numbers, and currencies with the browser's locale-aware APIs (`Intl.DateTimeFormat`, `Intl.NumberFormat`), never concatenated by hand.
- Always test with an "extreme" language (German for length, Arabic for direction) instead of just English/Italian.


## 84. Responsive images: the right size for every screen


- Use `srcset` and `sizes` to serve the resolution appropriate for the device, instead of always downloading the heaviest image.
- Modern formats (WebP, AVIF) with JPEG/PNG fallback reduce weight without perceptible quality loss.
- Always apply explicit `width`/`height` (or `aspect-ratio`) to reserve space and prevent layout shift on load.
- Lazy loading (`loading="lazy"`) should only be applied to images outside the initial viewport — above-the-fold images should load immediately.
- For photos with an off-center subject, use targeted `object-position` instead of the default center, so the responsive crop doesn't cut off the important part.

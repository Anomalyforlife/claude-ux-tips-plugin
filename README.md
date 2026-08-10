# ux-tips

A [Claude Code](https://claude.com/claude-code) plugin containing 85 practical UX/UI tips, organized by topic so Claude loads only what's relevant instead of dumping everything into context at once.

## What's inside

- **`.claude-plugin/plugin.json`** — the plugin manifest.
- **`skills/ux-tips/SKILL.md`** — the skill's entry point: when to use it, and a routing table mapping topics to reference files and section numbers.
- **`skills/ux-tips/references/`** — 85 tips split across 7 topic files, each a set of short, concrete bullet points (the rule + why it matters):
  - `psychology-and-motion.md` — UI psychology, micro-interactions, motion, animation timing
  - `design-systems.md` — design systems, layout, grid, tokens
  - `components.md` — UI components (forms, nav, data tables, overlays, drag & drop, etc.)
  - `accessibility-and-mobile.md` — accessibility, touch, mobile, push notifications
  - `performance-and-loading.md` — perceived performance, loading states, long lists
  - `platform-and-i18n.md` — dark mode, i18n/RTL, responsive images, overflow
  - `system-boundaries.md` — client/server boundaries, offline-first, onboarding, dark patterns

## Installation

### As a plugin (recommended)

This repo is itself a plugin marketplace (single plugin). Add it as a source, then install:

```
/plugin marketplace add Anomalyforlife/claude-ux-tips-skill
/plugin install ux-tips@claude-ux-tips-skill
```

### As a standalone skill

If you just want the skill without the plugin wrapper, copy `skills/ux-tips/` into your project's `.claude/skills/` directory (or `~/.claude/skills/` for a global install):

```bash
git clone https://github.com/Anomalyforlife/claude-ux-tips-skill.git /tmp/ux-tips-plugin
cp -r /tmp/ux-tips-plugin/skills/ux-tips .claude/skills/ux-tips
```

Claude Code will automatically discover the skill. Invoke it explicitly with `/ux-tips`, or let Claude pull it in automatically when a task looks UX/UI-related.

## Usage

Claude reads `SKILL.md` first (lightweight index), then reads only the specific `references/*.md` file(s) relevant to the task at hand — e.g. it'll open `components.md` for a dropdown question rather than loading all 85 tips.

## License

MIT — see [LICENSE](LICENSE).

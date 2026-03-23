# Changelog

All notable changes to Task Manager Pro are documented here.

---

## [3.2.0] - 2026-03-22

A major feature update adding time-aware scheduling, a smart tagging system, task type classification, AI-assisted categorization, and several UI improvements.

### Added

**Time Support for Tasks/Events**
- Optional time field (HH:MM, 24-hour) on every task — entered at creation or present in ICS imports
- If time is provided, displayed clearly alongside the date on task cards, week view chips, and the detail panel
- If no time is set, task is treated as all-day (defaults to 23:59 for urgency ordering)

**Time-Aware Urgency Scoring**
- Urgency score now considers both date AND time of day
- Tasks due within 6 hours score 97/100 (up from standard same-day 88)
- Tasks due within 12 hours score 93/100
- Same-day tasks with earlier times rank higher than later ones — morning classes surface above afternoon ones
- All-day tasks (no time) default to end-of-day ordering within the same date
- No breaking change to existing score scale; values only increase for higher precision

**Smart Tagging System**
- Multiple tags per task — add while creating or edit later
- Pill-style tag input: press `Enter`, `,`, or `Space` to commit; `Backspace` to remove last tag
- Colored tag pills displayed on task cards, week view, and the detail panel
- Tag colors: exam = red, assignment = gold, class = purple, holiday = green, event = orange, custom = neutral glass
- Tags are searchable in the All Tasks free-text search

**Auto Tagging (Rule-Based)**
- `inferAutoTags()` scans task names for keywords and applies matching tags automatically
- Applied on manual task creation AND on ICS/iCal import
- User-defined tags are never overridden — auto tags only fill gaps
- Keyword rules follow the same vocabulary as `inferPriority()`

**Task Type Classification**
- New `type` field per task: `task`, `assignment`, `class`, `exam`, `event`, `holiday`
- `inferType()` function detects type from task name keywords on creation and import
- Type shown as a color-coded pill badge on every task card
- Manual override available via Type dropdown in the Add Task modal
- New **Type** filter dropdown in the All Tasks tab

**AI-Assisted Categorization**
- On every task creation and import, type and tags are inferred from content using `inferType()` and `inferAutoTags()`
- Rule-based; no API call required — fast, offline-capable

**AI Disclaimer**
- Visible warning banner added inside the AI Assistant tab:
  `"⚠️ AI features are in development mode. Results may not always be accurate. Please double-check important tasks."`
- Styled in gold glass — subtle but clearly visible, does not disrupt layout

### Improved

**Urgency Scoring**
- Replaced coarse day-bucket logic with continuous millisecond-based diff
- Added sub-day tiers: <6 h (97), <12 h (93), <24 h (88) — existing day-level tiers unchanged

**All Tasks Filtering**
- Added Type filter dropdown alongside existing Priority and Status filters
- Search placeholder updated to reflect tag and type searchability

**Detail Panel**
- Due Date card now shows time if present (e.g. "Monday, March 24 at 14:30")
- Urgency label updated to "Urgency Score (time-aware)"
- Tags displayed as colored pills below the title in the detail panel
- Type badge shown in the header pill row alongside priority

**ICS Import**
- Imported tasks now receive `type` and `tags` in addition to `priority`
- Auto-categorization runs on every import — Canvas dumps get typed and tagged automatically

**Export**
- CSV export now includes `Time`, `Type`, and `Tags` columns (tags semicolon-delimited)

### Fixed

**Dashboard Shadow / Nav Rendering Bug**
- Active nav pill (`.nbtn.on`) previously had `overflow:hidden` or mismatched `border-radius` that caused a square cut-off shadow on the left side
- Fixed: explicit `border-radius: var(--r-pill)` and `overflow: visible` on active state; shadow now blends smoothly with no clipping or harsh edges

---

## [3.1.2] - 2026-03-19

A polish and compatibility commit — renamed entry point for GitHub Pages, tightened the custom timer input range, added a dynamic canvas favicon, and formally documented the ICS file upload feature.

### Added

**Dynamic Canvas Favicon**
- Browser tab icon generated at runtime via an inline `<canvas>` script
- Draws a rounded-square with a conic rainbow gradient and a white checkmark stroke
- Falls back to a linear gradient on browsers that do not support `createConicGradient`

**ICS File Upload (formally documented)**
- Import modal includes a `📄 Upload .ics File` section
- Parsed through the same `parseICS()` pipeline as URL imports

### Changed

**Entry point renamed to `index.html`**
- Previously `TaskManagerPro.html`; renamed for GitHub Pages compatibility

**Custom Timer Input Cap**
- Main Study Timer custom input now has `max="240"` in HTML
- JS validation threshold unchanged at 600

---

## [3.1.1] - 2026-03-19

### Added

**Bulk Task Actions (Past Due section)**
- Mark All Done and Mark Range Done with date-range picker

**Clickable Dashboard Stats**
- Each stat card navigates to the relevant filtered view

**Week View Navigation**
- Left/right arrow buttons; week range title; click-to-filter day tiles; task count badges

**Smart Auto-Priority from Task Name**
- `inferPriority()` applied on every ICS import

**Custom Timer Duration**
- Free numeric input in Study Timer tab and task detail panel

**ICS Parsing Improvements**
- Backslash-comma and backslash-n escape handling

### Fixed

**Pomodoro Reset Bug**
- `resetTimer()` now restores to last set duration, not always 25:00

**AI Scheduling Overload**
- Deduplication, 25-task cap, 4–6/day limit, fallback improvements

---

## [3.1.0] - 2026-03-19

### Added
- AI quick questions fire instantly on click
- 16 quick questions across 4 groups
- Weekly AI scheduling capability
- `_runAI()` shared internal function
- Landing page always shown on load

---

## [3.0.0] - 2026-03-19

### Added
- Landing page and onboarding flow
- iOS 26 liquid glass full redesign
- Task detail panel with deep blue glass and animated orbs
- Urgency scoring system (0–100)
- Week View tab
- Study Timer tab with animated SVG ring
- Claude API integration
- Auto-refresh calendar sources
- Course/category field
- Dark/light theme toggle
- All Tasks filters

---

## [2.0.0] - 2026-01-31

### Added
- Enhanced AI with natural language date parsing
- Date range and specific date queries
- Duplicate task handling
- Past due toggle section

### Fixed
- Checkbox alignment, text overflow, long note layout

---

## [1.0.0] - 2026-01-01

### Added
- Initial release: task creation, dashboard, calendar import, AI assistant, export, dark glassmorphic UI, localStorage persistence

---

Made by Aryan Kandula
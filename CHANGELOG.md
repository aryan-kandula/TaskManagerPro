# Changelog

All notable changes to Task Manager Pro are documented here.

---

## [3.1.2] - 2026-03-19

A polish and compatibility commit — renamed entry point for GitHub Pages, tightened the custom timer input range, added a dynamic canvas favicon, and formally documented the ICS file upload feature that was present but missing from the changelog.

### Added

**Dynamic Canvas Favicon**
- Browser tab icon is now generated at runtime via an inline `<canvas>` script
- Draws a rounded-square with a conic rainbow gradient (matching the app logo colors) and a white checkmark stroke
- Falls back to a linear gradient on browsers that do not support `createConicGradient`
- No external favicon file needed — fully self-contained in `index.html`

**ICS File Upload (formally documented)**
- Import modal includes a `📄 Upload .ics File` section — select any `.ics` file directly from disk
- Parsed through the same `parseICS()` pipeline as URL imports (unfolding, backslash-escape cleanup, auto-priority, duplicate guard)
- Tasks are tagged with source `ics-file` and shown with the 📄 ICS label in the detail panel

### Changed

**Entry point renamed to `index.html`**
- File was previously `TaskManagerPro.html`; renamed to `index.html` for GitHub Pages compatibility (serves automatically at the root URL without a filename in the address bar)
- No functional changes — all logic, styles, and structure are identical

**Custom Timer Input Cap (Study Timer tab)**
- Main Study Timer custom input now has `max="240"` in the HTML (previously displayed `max` was uncapped / set to 240 but JS validated up to 600)
- JS validation threshold unchanged at 600 — values between 241 and 600 are still accepted if typed manually
- Detail panel focus timer input retains `max="600"` (unchanged)

---

## [3.1.1] - 2026-03-19

A focused improvement commit addressing overdue task management, dashboard navigation, week view usability, AI scheduling quality, priority auto-detection, and timer bugs.

### Added

**Bulk Task Actions (Past Due section)**
- **Mark All Done** button — completes every overdue task in a single click
- **Mark Range Done** — date-range picker (from / to) to bulk-complete all tasks within a window
- Both actions live in a glass action bar directly above the Past Due task list
- Each action shows a toast confirming how many tasks were marked done

**Clickable Dashboard Stats**
- Total stat card → navigates to All Tasks tab
- Pending stat card → navigates to All Tasks with Pending filter pre-applied
- Done stat card → navigates to All Tasks with Done filter pre-applied
- Overdue stat card → opens the Past Due section on the dashboard and scrolls to it
- Each stat card shows a small hint label indicating where it navigates
- Hover effect with scale and border highlight on all stat cards

**Week View Navigation**
- Left/right arrow buttons to move between weeks
- Week range title shows e.g. "Mar 16 – Mar 22, 2026"
- Click any day tile to filter tasks for that specific day below the grid
- Selected day highlighted in purple, deselect by clicking again
- Task count badge per day tile (gold when tasks exist)
- Two-task preview chips per day, truncated to fit
- Full navigable week detail section replaces the static week task list

**Smart Auto-Priority from Task Name**
- `inferPriority(text)` function called on every imported task
- Keyword rules (case-insensitive):
  - **High**: exam, final, midterm, test, quiz, capstone, sprint
  - **Medium**: lab, assessment, assignment, homework, module lab, hands-on
  - **Low**: exercise, guided, attendance, survey, podcast, discussion, EC, career
  - Default: medium
- Applied automatically during ICS/iCal parsing — no manual priority needed for Canvas imports
- Manually added tasks still use the dropdown selection

**Custom Timer Duration**
- Free numeric input field in the Study Timer tab — type any number of minutes (1–600)
- Same custom input inside every task detail panel focus timer
- Both inputs show a toast confirming the new duration on Set

**ICS Parsing Improvements**
- Backslash-comma escapes (`\,`) in Canvas task names now correctly stripped to plain commas
- Backslash-n escapes (`\n`) in descriptions now converted to real line breaks
- Task names trimmed of excess whitespace after parsing

### Fixed

**Pomodoro Reset Bug**
- `resetTimer()` previously always reset to 25:00 regardless of what duration was set
- Fixed: reset now restores to `timerTotal` — the last duration that was set
- Same fix applied to `resetDT()` in the task detail panel focus timer (resets to `dtTotal`)

**AI Scheduling Overload (Canvas dump fix)**
- AI context now deduplicates tasks before sending — tasks with identical name prefix + date counted once
- Scheduling capped at 25 tasks total with max 4–6 per day
- Fallback scheduler also deduplicates and caps at 25, distributing evenly
- Task names truncated to 60 chars in AI context to avoid token waste
- Fallback output also truncates displayed names to 50 chars

**AI Response Quality**
- System prompt now explicitly instructs: max 4–6 tasks per day, skip weekends unless overdue
- Day-by-day format standardized: `DayName (Month Day):\n  • Task name [priority, due date]`
- "Remaining days" in fallback scheduler starts from today and goes through Friday only
- All AI quick question fallbacks now truncate long task names to prevent walls of text
- Course grouping fallback caps at 5 tasks per group with "+N more" indication

### Changed
- Week View tab no longer has a static full-week task dump at the bottom — replaced by interactive day-detail section
- `weekOffset` state variable tracks which week is being viewed
- `selectedWeekDay` state variable tracks the clicked day (date string)
- Timer reset buttons in both main timer and detail panel now respect last-set duration
- Stats row cursor changed to `pointer` with hover lift animation to indicate clickability

---

## [3.1.0] - 2026-03-19

### Added
- AI quick questions now fire instantly on click (no input box pre-fill)
- 16 quick questions across 4 groups: Planning, Status, Priority, By Course
- Weekly AI scheduling capability with day-by-day output
- Expanded Claude API system prompt with scheduling rules
- `_runAI()` shared internal function
- Fixed syntax error in quick question buttons (data attributes + addEventListener)
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
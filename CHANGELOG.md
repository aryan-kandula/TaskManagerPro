# Changelog

All notable changes to Task Manager Pro are documented here.

---

## [4.0.0] - 2026-05-09

The biggest update yet. Version 4.0 introduces direct Canvas assignment links — import your Canvas calendar feed once, and every assignment card gains a live **🔗 Open** button that takes you straight to the assignment page on Canvas. No more switching tabs or digging through Canvas manually. This release also ships a dedicated Courses tab with per-course progress tracking, a smarter multi-strategy URL resolver that handles assignments, quizzes, discussions, and New Quizzes, a background link resolver that silently upgrades indirect URLs into direct assignment pages, and a full suite of UI and reliability improvements.

### Added

**Direct Canvas Assignment Links (LLM Link Pull Integration)**
- Every imported Canvas task now attempts to resolve a direct link to its Canvas assignment page
- "🔗 Open" button appears on task cards and in the detail panel whenever a direct link is available
- Visual link indicator (🔗) on task cards signals which assignments have a confirmed direct URL
- Detail panel displays a styled "Open in Canvas →" action button for direct navigation
- Import once — log in to Canvas once — and open any assignment directly from the app without returning to Canvas to find it

**Multi-Strategy Canvas URL Resolver**
- New `pickCanvasUrl()` engine tries multiple resolution strategies in priority order:
  - Direct `/courses/` URLs embedded in `DESCRIPTION` fields (highest confidence)
  - UID-pattern parsing for assignments, quizzes, New Quizzes, and discussion topics
  - `URL:` field fallback for calendar events without a better direct link
- `canvasUrlFromUid()` constructs direct assignment, quiz, and discussion URLs from Canvas iCal UIDs:
  - `event-assignment-<ID>` → `/courses/<id>/assignments/<id>`
  - `event-quiz_lti-<ID>` → `/courses/<id>/quizzes/<id>` (New Quizzes)
  - `event-quiz-<ID>` → `/courses/<id>/quizzes/<id>` (Classic Quizzes)
  - `event-discussion_topic-<ID>` → `/courses/<id>/discussion_topics/<id>`
- Quoted-Printable DESCRIPTION decoding for Canvas iCal feeds that use encoded formatting

**Background Canvas URL Resolver (`resolveCanvasUrls()`)**
- Runs silently after every import and auto-refresh cycle
- Upgrades any remaining `canvas-api:` indirect URLs into confirmed direct assignment links
- Uses Canvas session credentials (`credentials: 'include'`) — works if you are already logged into Canvas in the same browser
- Saves resolved URLs back to localStorage so the upgrade persists across reloads
- Re-import support: re-importing a Canvas feed always updates the stored `eventUrl` for existing tasks, so improved URL resolution on a subsequent import is automatically reflected

**Courses Tab**
- New **Courses** tab groups all tasks by detected course code
- Per-course cards display:
  - Course code (monospaced, color-coded)
  - Course name inferred from import data
  - Total, pending, and completed assignment counts
  - Live completion progress bar
- Click any course card to filter the full task list to that course
- Course color system — each course gets a consistent accent color across cards, pills, progress bars, and badges
- Uncategorized bucket for tasks with no detected course code
- Google Calendar personal events grouped into their own separate bucket

**Onboarding & Landing Page Updates**
- Landing page feature showcase updated to highlight direct Canvas link access
- New step-by-step guide entry: "Review Courses & Track Progress"
- In-app callout added: *"No need to open Canvas for every assignment."*
- Onboarding note added clarifying the single-file app model and manual completion marking, with a note that automatic completion sync is coming in a future update

### Improved

**Import Pipeline**
- Re-import now updates `eventUrl` on existing tasks instead of skipping them — improved link resolution on repeat syncs
- Smarter deduplication during repeated auto-refresh cycles
- `resolveCanvasUrls()` now fires automatically after every import and file upload
- DESCRIPTION field parsing improved for Quoted-Printable encoded Canvas feeds
- Better extraction of direct assignment URLs from multi-URL DESCRIPTION blocks

**Task Cards**
- Direct-link indicator (🔗) shown on task card title row when a confirmed Canvas URL is available
- "🔗 Open" quick-action button added to task card footer for one-click Canvas navigation
- Card footer buttons now use `event.stopPropagation()` to prevent accidental detail panel triggers

**Detail Panel**
- "Open in Canvas →" styled action button replaces generic link display when source is Canvas
- Fallback message displayed when no direct link is available, with a re-import hint for Canvas tasks
- Source badge system extended for Canvas LMS (🎓 yellow) and ICS file (📄) sources

**Course Detection**
- Course code extraction improved for bracketed formats like `[CSC-251]`
- False-positive filtering expanded — common abbreviations (LAB, TEST, QUIZ, EXAM, HW, API, SQL, state codes, timezone codes) are excluded from course detection
- Course grouping now powers the Courses tab in addition to dashboard insights

### Fixed

- Fixed tasks with `canvas-api:` URLs not displaying an Open button after background resolution
- Fixed re-imports not updating the stored Canvas URL when a better direct link was found
- Fixed course color not applying consistently across cards and progress bars on re-render
- Fixed task card Open button triggering the detail panel open event simultaneously
- Fixed detail panel showing no link section for tasks where a URL existed but wasn't yet resolved

---

## [3.3.0] - 2026-05-07

A major intelligence and organization update introducing Smart Course Detection, enhanced Google iCal integration, improved AI-assisted categorization logic, large-scale UI refinements, and multiple synchronization and import stability improvements.

### Added

**Smart Course Detection**
- Added intelligent course detection and grouping system for tasks and imported calendar events
- Automatic recognition of common academic naming formats:
  - `CSC-151`
  - `ENG 111`
  - `BIO-168`
  - `MAT 171`
- Added automatic separation of academic tasks and personal events
- Added smarter course grouping support for dashboard insights and filtering
- Manual course override support preserved

**Enhanced Google iCal Intelligence**
- Added improved parsing support for Google Calendar `.ics` feeds
- Added smarter extraction of:
  - event titles
  - descriptions
  - dates
  - times
  - course identifiers
  - assignment naming patterns
- Added better recurring event interpretation
- Added stronger duplicate prevention during repeated sync cycles

**Improved Categorization Logic**
- Expanded rule-based categorization engine for smarter task classification
- Improved automatic type inference accuracy during imports
- Improved automatic tag inference for academic content
- Enhanced keyword recognition for assignments, exams, labs, lectures, and events

### Improved

**UI & Visual Polish**
- Improved spacing consistency across dashboard cards and overlays
- Refined detail panel alignment and metadata spacing
- Improved badge wrapping and overflow handling
- Improved week-view chip spacing and readability
- Refined hover animations and modal transitions
- Improved responsive scaling behavior on smaller screens
- Improved typography consistency across tabs and overlays
- Improved empty-state layouts and visual hierarchy

**Import & Sync Pipeline**
- Improved compatibility across Canvas, Google Calendar, and uploaded `.ics` files
- Reduced malformed event parsing failures
- Improved sync consistency during repeated auto-refresh cycles
- Reduced redundant parsing operations during imports
- Improved task grouping stability after synchronization

**Search & Filtering**
- Improved course-aware filtering behavior
- Improved keyword matching for imported academic tasks
- Improved organization insights for mixed academic/personal schedules

**Performance**
- Faster rendering for larger task collections
- Improved filtering responsiveness
- Optimized task sorting and grouping logic
- Improved localStorage synchronization handling

### Fixed

**Import & Parsing Fixes**
- Fixed several malformed `.ics` edge cases causing incomplete imports
- Fixed inconsistent course duplication during certain sync operations
- Fixed edge cases where imported tasks received incorrect types
- Fixed repeated tag duplication after multiple imports

**UI Fixes**
- Fixed metadata alignment inconsistencies in the detail panel
- Fixed badge overflow issues on smaller screens
- Fixed overlay inconsistencies between dark and light mode
- Fixed several spacing inconsistencies across navigation pills and dashboard cards

---

## [3.2.0] - 2026-03-22

A major feature update adding time-aware scheduling, a smart tagging system, task type classification, AI-assisted categorization, and several UI improvements.

### Added
- Time-aware scheduling
- Smart tagging
- Task type classification
- AI-assisted categorization
- CSV export enhancements

### Fixed
- Dashboard nav shadow clipping
- Detail panel alignment issues

---

## [3.1.2] - 2026-03-19

### Added
- Dynamic canvas favicon generation
- ICS file upload support

### Changed
- Entry point renamed to `index.html`

---

## [3.1.1] - 2026-03-19

### Added
- Bulk task actions
- Clickable dashboard stats
- Week view navigation
- Smart auto-priority detection

### Fixed
- Pomodoro reset bug
- AI scheduling overload edge cases

---

## [3.1.0] - 2026-03-19

### Added
- AI quick questions
- Weekly AI scheduling
- Landing page onboarding flow

---

## [3.0.0] - 2026-03-19

### Added
- iOS 26 liquid glass redesign
- Week View
- Study Timer
- Claude AI integration
- Auto-refresh calendar imports

---

## [2.0.0] - 2026-01-31

### Added
- Natural language date parsing
- Duplicate task handling
- Past due section

### Fixed
- Checkbox alignment
- Text overflow bugs

---

## [1.0.0] - 2026-01-01

### Added
- Initial release
- Task creation
- Dashboard
- Calendar imports
- AI assistant
- LocalStorage persistence

---

Made by Aryan Kandula

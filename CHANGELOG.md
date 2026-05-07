# Changelog

All notable changes to Task Manager Pro are documented here.

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

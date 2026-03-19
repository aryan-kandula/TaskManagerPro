# Changelog

All notable changes to Task Manager Pro are documented here.

---

## [3.0.0] - 2026-03-19

### Added

**Landing Page & Onboarding**
- Full onboarding landing page shown on first visit with animated hero section
- Feature showcase grid explaining all six major feature areas
- Step-by-step how-to guide with six numbered steps covering every workflow
- Smooth fade and scale transition animation when entering the dashboard
- Guide button in the app header to return to the landing page at any time
- Smart session memory — returning users skip the guide automatically

**iOS 26 Liquid Glass Design System**
- Complete visual redesign using a full CSS token system (`--glass`, `--glass-2`, `--glass-3`, `--glass-strong`, `--blur`)
- Liquid glass surfaces with `backdrop-filter: blur(40px) saturate(1.8)` throughout
- Pill-shaped floating sticky header and pill navigation tabs
- Animated background orb mesh on both landing page and app (four independent orbs)
- Dark and light mode both fully redesigned with distinct glass opacities, shadow depths, and orb color palettes
- Spring-physics animation (`cubic-bezier(0.175, 0.885, 0.32, 1.275)`) on modals and detail panels
- Smooth `600ms` theme transition on all surfaces

**Task Detail Panel**
- Full immersive task detail panel triggered by clicking any task card
- iOS 26 deep blue glass panel with triple animated floating orbs inside the panel itself
- Urgency score display (0–100) with animated fill bar that transitions on open
- Full due date, time remaining countdown, status, source, and course fields
- Built-in Pomodoro focus timer directly inside the detail view
- Mark done and delete actions from within the detail panel
- Separate light-mode variant of the panel using frosted white glass

**Urgency Scoring System**
- Auto-calculated urgency score (0–100) for every task based on deadline proximity and priority
- Color-coded urgency bar on every task card: green → teal → blue → gold → red
- Countdown label on cards showing days remaining or days overdue
- All tasks views sorted by urgency score descending so most critical tasks always surface first

**Week View Tab**
- 7-day calendar grid showing the current week
- Tasks plotted per day with clickable chips
- Today highlighted in primary blue, overdue days highlighted in red accent
- Full task list below the grid showing all tasks for the week

**Study Timer Tab**
- Pomodoro timer with animated SVG gradient ring
- 25-minute, 50-minute, and 5-minute break presets
- Task selection list sorted by urgency score
- Toast notification on session completion
- Focus timer also available inside each task detail panel

**AI Assistant Upgrade**
- Connected to the Claude API (`claude-sonnet-4-20250514`) for genuine reasoning
- System prompt injects full task list, counts, overdue status, and completion rate into every query
- Smart local fallback logic if the API is unavailable
- Quick question buttons for eight common queries
- Live snapshot panel showing completion rate, overdue count, high priority count, and next deadline

**Auto-Refresh Calendar Sources**
- Calendar URLs saved as persistent sources after import
- Background auto-refresh polling every 5 minutes
- New task badge counter on the Live pill in the header
- Manual refresh via the Live pill
- Source list with remove option in the Settings tab

**Course/Category Field**
- New optional course/category field on every task
- Displayed as a purple badge on task cards
- Shown in the task detail panel

**All Tasks Filters**
- Priority filter, status filter, and free-text search all work simultaneously
- Results re-sort by urgency score on every filter change

### Changed
- Header redesigned as a pill-shaped floating glass bar sticky at `top: 14px`
- Navigation redesigned as horizontal pill buttons (not tabs)
- All buttons use pill border-radius throughout
- Stats row uses animated counters on every render
- Task cards use spring animation on hover (`translateY(-5px) scale(1.01)`)
- Modal open animation uses spring physics
- Checkbox uses custom styled appearance with smooth scale transition
- App font changed to Sora + JetBrains Mono pairing
- localStorage keys updated to `tmp_tasks`, `tmp_sources`, `tmp_theme`, `tmp_seen`

### Removed
- Old flat dark glassmorphic style replaced entirely
- Legacy AI assistant local-only logic replaced by Claude API with fallback
- Separate CSS file dependency (fully self-contained single HTML file)

---

## [2.0.0] - 2026-01-31

### Added
- Enhanced AI assistant with natural language date parsing
- Date range queries ("tasks until Feb 10")
- Specific date queries ("tasks on March 15")
- This week / next week query support
- Duplicate task handling
- Toggle button for past due tasks section
- Improved task card layout with better text wrapping
- Consistent checkbox alignment for long descriptions
- Separate upcoming and past due task sections

### Changed
- Reorganized dashboard to show upcoming tasks first
- Past due tasks now hidden by default with toggle
- Improved task card flexbox layout
- Enhanced text overflow handling in task cards
- Updated AI assistant welcome message

### Fixed
- Task checkbox alignment issues with long descriptions
- Text overflow in task cards
- Layout breaking with very long notes
- Inconsistent spacing in task cards

---

## [1.0.0] - 2026-01-01

### Added
- Initial release
- Task creation with description, date, priority, and notes
- Dashboard with statistics
- Task completion tracking
- Google Calendar integration via iCal URL
- Canvas LMS calendar integration
- ICS file upload and import
- AI assistant with basic natural language queries
- Export to JSON and CSV
- Dark glassmorphic UI
- LocalStorage persistence
- Priority system (High / Medium / Low)
- Task deletion
- Responsive layout for desktop and mobile

---

Made with ❤️ by Aryan Kandula

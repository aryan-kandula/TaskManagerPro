# Changelog

All notable changes to Task Manager Pro are documented here.

---

## [3.1.0] - 2026-03-19

### Added

**AI Quick Questions — Instant Fire**
- Quick question buttons now fire immediately when clicked — the question appears in the chat as a user message and the AI responds without any intermediate step
- Clicking a button no longer pre-fills the input box; it bypasses it entirely and goes straight to the AI
- Questions are now grouped into four labelled categories rendered with section headers: 📅 Planning, 📊 Status, 🎯 Priority, 📚 By Course

**Expanded Quick Question Set (16 questions across 4 groups)**
- Planning: "Schedule my tasks across this week by importance", "Give me a day-by-day study plan for this week", "What should I work on today?", "Build me a study schedule for the next 3 days"
- Status: "Am I falling behind on anything?", "How's my completion rate looking?", "Which tasks are overdue?", "How many days until my next deadline?"
- Priority: "What are my highest priority tasks?", "What is the single most important thing I should do right now?", "Rank all my pending tasks by urgency", "Which tasks can I safely leave until later?"
- By Course: "Group my tasks by course or category", "Which course has the most pending work?", "Show me everything due in the next 7 days", "What tasks are due this week vs next week?"

**Weekly Scheduling via AI**
- The AI can now produce a full day-by-day schedule for the current week
- Each pending task is assigned to a specific day based on urgency score, due date proximity, and workload balance
- Overdue and high-priority tasks are placed on the earliest available day
- Workload is spread sensibly — no single day is overloaded
- Works via both Quick Question click and free-text input

**Expanded AI System Prompt**
- System prompt now includes full day names for the current week so the AI can reason about specific days correctly
- Each task in context now includes the day-of-week name alongside the date
- AI instructions explicitly cover: scheduling, workload balancing, course grouping, urgency ranking, overdue analysis, and deadline countdowns
- `max_tokens` increased from 1000 to 1200 to accommodate longer scheduling responses

**Refactored AI Architecture**
- Introduced `_runAI(q)` internal function that both `sendAI()` and `askAI()` delegate to — eliminates code duplication
- `askAI(msg)` now appends the user message and calls `_runAI` directly without touching the input element

**Expanded Local Fallback**
- Fallback now handles scheduling/planning queries and produces a real day-by-day schedule using local urgency scoring — works even without the API
- Added fallback branches for: urgency ranking, course grouping, 7-day deadline window
- All fallback responses reference actual task names and dates, not generic placeholders

### Changed
- Quick Questions panel now renders grouped sections with category labels instead of a flat list of 8 buttons
- `sugList` container scrolls independently when there are many questions
- AI snapshot panel styling unchanged; stat values still update on every tab render

### Fixed
- Quick question buttons no longer leave residual text in the input field after firing
- Clicking a quick question while the input had existing text no longer sends the wrong message

---

## [3.0.0] - 2026-03-19

### Added
- Landing page and onboarding flow with feature showcase and step-by-step guide
- iOS 26 liquid glass design system with full CSS token architecture
- Task detail panel with deep blue glass, animated orbs, urgency bar, and built-in focus timer
- Urgency scoring system (0–100) based on deadline proximity and priority
- Week View tab with 7-day calendar grid
- Study Timer tab with Pomodoro-style animated SVG ring
- AI Assistant connected to Claude API with task-aware system prompt
- Auto-refresh calendar sources (Canvas + Google) polling every 5 minutes
- Course/category field on tasks
- Dark/light theme toggle with localStorage persistence
- All Tasks filters: priority, status, and free-text search simultaneously
- Spring-physics modal and detail panel animations
- Sora + JetBrains Mono font pairing

### Changed
- Full visual redesign replacing v2.0 glassmorphic style
- Header redesigned as pill-shaped floating sticky bar
- Navigation redesigned as horizontal pill buttons
- Stats row uses animated counters
- Font changed from system fonts to Sora + JetBrains Mono
- localStorage keys updated to `tmp_tasks`, `tmp_sources`, `tmp_theme`, `tmp_seen`

---

## [2.0.0] - 2026-01-31

### Added
- Enhanced AI assistant with natural language date parsing
- Date range queries ("tasks until Feb 10")
- Specific date queries ("tasks on March 15")
- This week / next week query support
- Duplicate task handling
- Toggle button for past due tasks section
- Separate upcoming and past due task sections

### Changed
- Dashboard reorganized to show upcoming tasks first
- Past due tasks hidden by default
- Improved task card flexbox layout and text overflow handling

### Fixed
- Checkbox alignment with long task descriptions
- Text overflow in task cards
- Layout breaking with very long notes

---

## [1.0.0] - 2026-01-01

### Added
- Initial release with task creation, dashboard, completion tracking
- Google Calendar and Canvas LMS integration
- ICS file import
- AI assistant with basic queries
- JSON and CSV export
- Dark glassmorphic UI
- LocalStorage persistence
- Priority system and responsive layout

---

Made with ❤️ by Aryan Kandula

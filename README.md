# Task Manager Pro

A modern, student-focused task management application built with vanilla JavaScript and powered by Claude AI.
Featuring a full iOS 26-style liquid glassmorphic design, intelligent scheduling, smart tagging, time-aware prioritization, enhanced Google iCal integration, and Smart Course Detection for deeply organized academic workflows.

![Version](https://img.shields.io/badge/version-3.3.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Design](https://img.shields.io/badge/design-iOS%2026%20Glass-blueviolet.svg)
![AI](https://img.shields.io/badge/AI-Claude%20Powered-orange.svg)

---

## 🔗 Live Demo

👉 https://aryan-kandula.github.io/TaskManagerPro

---

## ✨ Version 3.3 Features

### 🧠 Smart Course Detection

Task Manager Pro now intelligently analyzes tasks and imported calendar events to detect and organize course-related content automatically.

#### Features
- Automatic course detection from:
  - task titles
  - assignments
  - imported Google Calendar events
  - Canvas iCal feeds
  - uploaded `.ics` files
- Smarter academic vs personal event separation
- Better grouping across dashboard insights and task views
- Improved detection of common course formats:
  - `CSC-151`
  - `ENG 111`
  - `BIO-168`
  - `MAT 171`
- Manual course override always supported

#### Benefits
- Cleaner organization
- Better academic workload visibility
- More accurate insights and filtering
- Faster recognition of imported schedules

---

### 🔗 Enhanced Google iCal Integration

The calendar import engine has been heavily upgraded with smarter parsing and improved event understanding.

#### Improvements
- Better compatibility with Google Calendar exports and feeds
- Improved handling of inconsistent `.ics` formatting
- Smarter extraction of:
  - titles
  - descriptions
  - dates
  - times
  - course identifiers
  - assignment keywords
- More reliable recurring event parsing
- Improved duplicate prevention during sync refreshes
- Better consistency across Canvas, Google Calendar, and uploaded `.ics` files

---

### 🤖 Improved AI-Assisted Categorization

The local rule-based intelligence engine has been upgraded.

#### Enhancements
- Smarter task type detection
- Better auto-tagging accuracy
- Improved academic keyword recognition
- More reliable classification of assignments, exams, classes, and events
- Smarter categorization during imports and manual task creation

> ⚠️ AI-assisted features are privacy-safe and rule-based. No external AI processing is required for task categorization or imports.

---

## 🌟 Full Feature List

### 🎨 iOS 26 Liquid Glass Design
- Full liquid glassmorphic UI inspired by Apple's iOS 26 design language
- Deep layered glass panels with animated floating orb backgrounds
- Dark and light mode with smooth animated transitions
- Floating pill navigation and sticky glass headers
- Dynamic animated background mesh effects
- Runtime-generated canvas favicon with gradient styling

### 📋 Task Management
- Create tasks with:
  - title
  - description
  - due date
  - optional time
  - priority
  - type
  - tags
  - course/category
  - notes
- High, Medium, and Low priority scoring
- Intelligent urgency calculation with time awareness
- Visual urgency bars on every task card

### ⏰ Time-Aware Scheduling
- Optional time field for every task
- Same-day tasks prioritize earlier times automatically
- All-day tasks sort toward end-of-day ordering
- Sub-day urgency tiers:
  - `<6h` → 97 urgency
  - `<12h` → 93 urgency
  - `<24h` → 88 urgency

### 🏷️ Smart Tagging System
- Multiple tags per task
- Pill-style tag input with keyboard shortcuts
- Auto-tagging during creation and imports
- Colored tag badges throughout the app
- Searchable tags in All Tasks search

### 🗂️ Task Type Classification

| Type | Description |
|---|---|
| `task` | General to-do |
| `assignment` | Coursework and submissions |
| `class` | Lectures and labs |
| `exam` | Tests, quizzes, finals |
| `event` | Meetings and activities |
| `holiday` | Breaks and no-class days |

- Automatic type inference
- Manual override support
- Type filtering in All Tasks
- Color-coded badges on task cards

### 👁️ Immersive Task Detail Panel
- Full-screen detail experience
- Displays:
  - urgency score
  - due date/time
  - task type
  - tags
  - source
  - course
  - notes
- Built-in focus timer with custom duration support
- Mark complete or delete directly from the panel

### 📅 Week View
- Interactive 7-day calendar layout
- Week navigation controls
- Click-to-filter day tiles
- Task count indicators
- Improved chip layout and spacing

### 📊 Dashboard & Insights
- Animated statistic counters
- Clickable stat navigation
- Improved course-aware organization insights
- Past Due management section
- Bulk completion actions

### 🔍 Advanced Filtering & Search
- Filter by:
  - priority
  - status
  - type
  - course
- Free-text search across:
  - titles
  - notes
  - tags
  - courses

### 🔄 Auto-Refresh Calendar Sources
- Import from:
  - Canvas iCal links
  - Google Calendar feeds
  - uploaded `.ics` files
- Automatic sync every 5 minutes
- Intelligent import categorization
- Auto-priority, auto-tags, and auto-type assignment

### ⏱️ Study Timer
- Pomodoro-style timer
- Animated SVG progress ring
- Presets:
  - 25 min
  - 50 min
  - 5 min break
- Custom duration support

### 💾 Data & Privacy
- Fully local-first architecture
- No accounts required
- No servers or backend
- Data stored locally in browser localStorage
- Export as JSON or CSV

---

## 🚀 Getting Started

No installation. No dependencies. No build process.

1. Clone or download the repository
2. Open `index.html` in any modern browser
3. Complete onboarding
4. Start managing tasks instantly

---

## 📁 File Structure

```
Taskmanagerpro/
    ├── README.md
    ├── CHANGELOG.md
    ├── CONTRIBUTING.md
    ├── ITERATION_LOG.md
    ├── LICENSE
    ├── PRD.md
    ├── PROTOTYPE_TESTING.md
    └── .github/
        └── workflows/
            └── static.yml

```

## 🔐 Privacy & Security

No analytics or tracking
No user accounts
No backend infrastructure
All data remains local to the browser
Clearing browser storage removes saved tasks

## 👤 Author

### Aryan Kandula

GitHub: https://github.com/aryan-kandula

# Task Manager Pro

A modern, student-focused task management application built with vanilla JavaScript and powered by Claude AI.
Featuring a full iOS 26-style liquid glassmorphic design, intelligent scheduling, smart tagging, time-aware prioritization, direct Canvas assignment links, per-course progress tracking, enhanced Google iCal integration, and Smart Course Detection for deeply organized academic workflows.

![Version](https://img.shields.io/badge/version-4.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Design](https://img.shields.io/badge/design-iOS%2026%20Glass-blueviolet.svg)
![AI](https://img.shields.io/badge/AI-Claude%20Powered-orange.svg)

---

## 🔗 Live Demo

👉 https://aryan-kandula.github.io/TaskManagerPro

---

## 💡 The Idea

This app started with a real student problem — mine.

I didn't want five different tools to stay on top of my classes. I didn't want to open Canvas separately for each assignment, navigate through menus just to find what was due, or rely on calendar apps that only let me *view* tasks without doing anything about them.

So I built one place to do it all: import your schedule, plan your week with strategy tools, and open assignments directly — all without leaving the app. Log into Canvas once in your browser, paste your calendar feed once, and everything is there. Every course, every deadline, every assignment link — one tab.

> **No need to open Canvas for every assignment.**
> Import once. Stay here. Get things done.

Since this is a single-file app, Canvas completion status isn't read automatically — mark tasks done here after you finish them in Canvas, and the app does the rest. A future update will sync completion status automatically.

---

## ✨ Version 4.0 Features

### 🔗 Direct Canvas Assignment Links

The headline feature of v4.0. Every imported Canvas task now resolves a direct link to its assignment page — so you can open it with one click, right from the task card or detail panel.

#### How it works
- Import your Canvas Calendar Feed URL once via the **⬇ Import** panel
- The app parses your iCal feed and resolves direct assignment, quiz, discussion, and New Quizzes URLs automatically
- A **🔗 Open** button appears on every task card that has a confirmed direct link
- The detail panel shows an **"Open in Canvas →"** action button for full assignment access
- Already logged into Canvas in your browser? The background resolver silently upgrades any indirect links into direct ones after every import

#### What gets resolved
| Canvas Event Type | Direct URL Format |
|---|---|
| Assignment | `/courses/<id>/assignments/<id>` |
| Classic Quiz | `/courses/<id>/quizzes/<id>` |
| New Quizzes | `/courses/<id>/quizzes/<id>` |
| Discussion Topic | `/courses/<id>/discussion_topics/<id>` |
| Calendar Event | Calendar URL (fallback) |

#### A note on completion
Task Manager Pro is a single-file static app — it cannot read your Canvas submission status automatically. After completing an assignment in Canvas, mark it done here so the app can track your progress. **Automatic completion sync is coming in a future update.**

---

### 🏫 Courses Tab

A dedicated **Courses** tab organizes everything by detected course code, giving you a per-course view of your entire semester at a glance.

#### Features
- Per-course cards showing:
  - Course code and name
  - Total, pending, and completed assignment counts
  - Live completion progress bar
- Color-coded course accent system — consistent colors across cards, pills, progress bars, and badges
- Click any course card to filter the task list to that course only
- Separate buckets for uncategorized tasks and Google Calendar personal events

---

### 🧠 Smart Course Detection

Task Manager Pro automatically detects and groups course-related content from all imported and manually created tasks.

#### Features
- Automatic course detection from task titles, assignments, iCal feeds, and uploaded `.ics` files
- Recognizes common academic naming formats including bracketed variants:
  - `CSC-151`, `[CSC-251]`, `ENG 111`, `BIO-168`, `MAT 171`, `NOS-120`
- Smart false-positive filtering — common abbreviations (LAB, QUIZ, EXAM, API, timezone and state codes) are excluded
- Smarter academic vs. personal event separation
- Manual course override always supported

---

### 🔗 Enhanced Google iCal Integration

The calendar import engine supports both Canvas and Google Calendar feeds with smarter parsing and improved event understanding.

#### Improvements
- Better compatibility with Google Calendar exports and feeds
- Improved handling of inconsistent `.ics` formatting including Quoted-Printable encoding
- Smarter extraction of titles, descriptions, dates, times, course identifiers, and assignment keywords
- More reliable recurring event parsing
- Improved duplicate prevention during sync refreshes
- Re-import updates existing tasks with improved URL resolution — no duplicates created

---

### 🤖 Improved AI-Assisted Categorization

The local rule-based intelligence engine classifies tasks automatically on every import and creation.

#### Enhancements
- Smarter task type detection
- Better auto-tagging accuracy
- Improved academic keyword recognition
- More reliable classification of assignments, exams, classes, and events

> ⚠️ AI-assisted categorization is privacy-safe and rule-based. No external AI processing is required for task categorization or imports.

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
- Create tasks with title, description, due date, optional time, priority, type, tags, course/category, and notes
- High, Medium, and Low priority scoring
- Intelligent urgency calculation with time awareness
- Visual urgency bars on every task card

### ⏰ Time-Aware Scheduling
- Optional time field for every task
- Same-day tasks prioritize earlier times automatically
- All-day tasks sort toward end-of-day ordering
- Sub-day urgency tiers: `<6h` → 97, `<12h` → 93, `<24h` → 88

### 🏷️ Smart Tagging System
- Multiple tags per task with pill-style input
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

- Automatic type inference on creation and import
- Manual override support
- Type filtering in All Tasks
- Color-coded badges on task cards

### 👁️ Immersive Task Detail Panel
- Full-screen detail experience
- Displays urgency score, due date/time, task type, tags, source, course, and notes
- Direct Canvas link with "Open in Canvas →" action button
- Built-in focus timer with custom duration support
- Mark complete or delete directly from the panel

### 📅 Week View
- Interactive 7-day calendar layout
- Week navigation controls
- Click-to-filter day tiles
- Task count indicators

### 📊 Dashboard & Insights
- Animated statistic counters
- Clickable stat navigation
- Course-aware organization insights
- Past Due management section
- Bulk completion actions

### 🔍 Advanced Filtering & Search
- Filter by priority, status, type, and course
- Free-text search across titles, notes, tags, and courses

### 🔄 Auto-Refresh Calendar Sources
- Import from Canvas iCal links, Google Calendar feeds, or uploaded `.ics` files
- Automatic sync every 5 minutes
- Intelligent import categorization
- Auto-priority, auto-tags, and auto-type assignment
- Background Canvas URL resolver upgrades links silently after every sync

### ⏱️ Study Timer
- Pomodoro-style timer with animated SVG progress ring
- Presets: 25 min, 50 min, 5 min break
- Custom duration support

### 💾 Data & Privacy
- Fully local-first architecture
- No accounts required
- No servers or backend
- All data stored locally in browser localStorage
- Export as JSON or CSV

---

## 🚀 Getting Started

No installation. No dependencies. No build process.

1. Clone or download the repository
2. Open `index.html` in any modern browser
3. Complete onboarding
4. Paste your Canvas Calendar Feed URL in **⬇ Import**
5. Start managing your semester

### Finding your Canvas Calendar Feed URL
1. Open Canvas and click the **Calendar** icon in the left sidebar
2. On the Calendar page, find the **Calendars** panel on the right side
3. Scroll to the bottom of that panel and click **Calendar Feed**
4. Copy the URL that appears
5. Paste it into the Canvas Calendar Feed URL field in the Import panel and click **Import & Watch**

---

## 📁 File Structure

```
TaskManagerPro/
    ├── index.html
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

---

## 🔐 Privacy & Security

- No analytics or tracking
- No user accounts
- No backend infrastructure
- All data remains local to the browser
- Canvas links open using your existing browser session — no credentials are stored by the app
- Clearing browser storage removes all saved tasks

---

## 👤 Author

### Aryan Kandula

GitHub: https://github.com/aryan-kandula

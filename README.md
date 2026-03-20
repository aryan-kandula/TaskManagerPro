# Task Manager Pro

A modern, student-focused task management application built with vanilla JavaScript and powered by Claude AI.  
Featuring a full iOS 26-style liquid glassmorphic design, intelligent AI assistance, auto-refreshing calendar sources, and an immersive task detail experience.

![Version](https://img.shields.io/badge/version-3.1.2-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Design](https://img.shields.io/badge/design-iOS%2026%20Glass-blueviolet.svg)
![AI](https://img.shields.io/badge/AI-Claude%20Powered-orange.svg)

---

## 🔗 Live Demo

👉 [https://aryan-kandula.github.io/TaskManagerPro](https://aryan-kandula.github.io/TaskManagerPro)

---

## 🌟 Features

### 🎨 iOS 26 Liquid Glass Design
- Full liquid glassmorphic UI inspired by Apple's iOS 26 design language
- Deep navy layered glass on detail panels with triple animated floating orbs
- Dark and light mode with smooth animated toggle — both fully redesigned
- Pill-shaped floating sticky header and pill navigation throughout
- Animated background mesh with drifting color orbs on every page
- Dynamic canvas favicon — rainbow gradient rounded-square with checkmark, generated at runtime

### 🛬 Landing Page & Onboarding
- Full onboarding landing page that explains every feature before you start
- Step-by-step visual guide walking through each part of the app
- Smooth fade and scale transition into the dashboard on entry
- Remembers returning users and skips the guide automatically
- A **← Guide** button in the app header brings the landing page back at any time

### 📋 Task Management
- Create tasks with description, due date, priority, course/category, and notes
- High, Medium, and Low priority system with color-coded urgency scoring
- Urgency score (0–100) auto-calculated from deadline proximity and priority level
- Visual urgency bar on every task card, color-coded from green to red
- Countdown label showing days remaining or days overdue on every card

### 🧠 Smart Auto-Priority Detection
- Task names are scanned automatically to infer priority on every import
- **High**: exam, final, midterm, test, quiz, capstone, sprint
- **Medium**: lab, assessment, assignment, homework, module lab, hands-on
- **Low**: exercise, guided, attendance, survey, podcast, discussion, EC, career
- Manually added tasks still use the dropdown — auto-detection only applies to imports

### 👁️ Task Detail Panel
- Click any task to open an immersive full-screen detail view
- iOS 26 deep blue glassmorphic panel with animated floating orbs inside
- Shows urgency score with animated fill bar, full due date, status, source, and course
- Built-in focus timer inside the detail panel with custom duration input (up to 600 min)
- Mark done or delete directly from the detail view

### 🤖 AI Assistant — Powered by Claude
The AI assistant connects to the Claude API (`claude-sonnet-4-20250514`) and has full awareness of all your tasks, deadlines, priorities, and courses. Clicking a Quick Question fires it instantly — no typing required.

**What you can ask:**
- `Schedule my tasks across this week by importance` — generates a full day-by-day plan, max 4–6 tasks per day, skipping weekends unless overdue
- `Give me a day-by-day study plan for this week` — assigns specific tasks to specific days based on urgency and due dates
- `What should I work on today?` — surfaces the most critical tasks for right now
- `Am I falling behind on anything?` — checks overdue and near-due tasks
- `Rank all my pending tasks by urgency` — full urgency-scored ranked list
- `Group my tasks by course or category` — organizes everything by the course field
- `Which course has the most pending work?` — workload breakdown by course
- `What tasks are due this week vs next week?` — deadline window comparison
- `What is the single most important thing I should do right now?` — concise top priority
- `Which tasks can I safely leave until later?` — identifies low-urgency items
- And any free-form question in natural language

**Quick Question groups** (all clickable, fire instantly):
- 📅 Planning — scheduling and study plans
- 📊 Status — completion rate, overdue checks, deadline countdowns
- 🎯 Priority — urgency ranking and focus advice
- 📚 By Course — grouped views and course-level workload

### 🔄 Auto-Refresh Calendar Sources
- Paste a Canvas or Google Calendar URL once — tasks sync every 5 minutes automatically
- Live badge on the header pill when new tasks are detected
- Manual refresh available at any time
- Sources managed and removable in the Settings tab

### 📅 Week View
- Full 7-day calendar grid with left/right arrow navigation between weeks
- Week range title updates as you navigate (e.g. "Mar 16 – Mar 22, 2026")
- Click any day tile to filter tasks for that specific day below the grid; click again to deselect
- Today highlighted in blue, selected day highlighted in purple
- Task count badge per tile (gold when tasks exist), two-task preview chips per day
- Interactive day-detail section below the grid replaces the old static list

### ⏱ Study Timer
- Pomodoro-style timer with animated SVG gradient ring
- 25-minute, 50-minute, and 5-minute break presets
- Custom duration input — type any number of minutes up to 240 in the Study Timer tab
- Same custom input inside every task detail panel (up to 600 min)
- Reset always restores the last-set duration, not the default 25:00
- Task selection sorted by urgency score
- Toast notification on session completion

### 📊 Dashboard
- Animated stat counters for total, pending, done, and overdue — all clickable
- Total → All Tasks tab; Pending → All Tasks filtered to Pending; Done → All Tasks filtered to Done; Overdue → scrolls to Past Due section
- Upcoming tasks auto-sorted by urgency score
- Past Due section hidden by default with toggle
- Bulk actions bar above Past Due: Mark All Done or Mark Range Done with a date picker

### 🔍 All Tasks View
- Filter simultaneously by priority, status, and free-text search
- Results always sorted by urgency score

### 💾 Data & Privacy
- All data stored locally in your browser — nothing leaves your device
- Export as JSON or CSV from the Settings tab
- No accounts, no tracking, no servers

---

## 🚀 Getting Started

No installation. No dependencies. No build process.

1. Download or clone the repository
2. Open `index.html` in any modern web browser
3. Follow the onboarding guide, then start adding tasks

---

## 💡 Usage

### Adding Tasks
Click **+ Add Task**, fill in the description, due date, priority, course, and notes, then click **Add Task**.

### Viewing a Task
Click any task card to open the full detail panel with urgency breakdown, notes, and a built-in focus timer.

### Importing from Calendars
Click **Import**, then either:
- Paste your Canvas Calendar Feed URL or Google iCal URL and click **Import & Watch** — tasks import and the source auto-refreshes every 5 minutes going forward
- Upload a `.ics` file directly from disk using the file picker and click **Import File**

### AI Assistant
Open the **AI Assistant** tab. Click any Quick Question button — it fires immediately. Or type your own question in the input box and press Enter or Send.

### Study Timer
Open **Study Timer**, select a task from the right panel, pick a duration (preset or custom), and click Start.

### Theme Toggle
Click the pill toggle in the top-right of the header to switch dark/light mode.

---

## 🎨 Design System

| Token | Purpose |
|---|---|
| `--glass` / `--glass-2` / `--glass-3` | Layered surface depths |
| `--glass-strong` | Toasts and high-contrast overlays |
| `--blur` | `blur(40px) saturate(1.8)` — main glass effect |
| `--pri` | Primary blue accent |
| `--acc` | Red/pink danger accent |
| `--grn` | Green success accent |
| `--gld` | Gold/warning accent |
| `--purp` | Purple gradient accent |

---

## 🔧 Technical Details

**Technologies:** HTML5 · CSS3 · Vanilla JavaScript · Claude API (`claude-sonnet-4-20250514`) · LocalStorage API · Fetch API

**Browser Compatibility:** Chrome / Edge (recommended) · Firefox · Safari · Opera

---

## 📁 File Structure

```
TaskManagerPro/
├── index.html      # Complete single-file application
├── README.md       # Project documentation
├── CHANGELOG.md    # Version history
└── LICENSE         # MIT License
```

---

## 🔐 Privacy & Security

- No tracking or analytics
- No accounts or logins
- No servers or backend
- All task data in localStorage only
- Export regularly — clearing browser data removes tasks

---

## 🤝 Contributing

1. Fork the repository
2. Create a branch — `git checkout -b feature/YourFeature`
3. Commit — `git commit -m "Add YourFeature"`
4. Push — `git push origin feature/YourFeature`
5. Open a Pull Request

**Ideas:** task categories, recurring tasks, drag-and-drop reordering, browser push notifications, mobile-first layout, theme builder, multi-language support.

---

## 🗺️ Roadmap

- [ ] Task categories and labels
- [ ] Recurring tasks
- [ ] Drag-and-drop task ordering
- [ ] Browser push notifications for deadlines
- [ ] Mobile-first UI overhaul
- [ ] Theme customization panel
- [ ] Task sharing

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.

---

## 👤 Author

**Aryan Kandula**  
[github.com/aryan-kandula](https://github.com/aryan-kandula)

---

Made by Aryan Kandula
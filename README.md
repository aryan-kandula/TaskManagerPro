# Task Manager Pro

A modern, student-focused task management application built with vanilla JavaScript and powered by Claude AI.  
Featuring a full iOS 26-style liquid glassmorphic design, intelligent AI assistance, auto-refreshing calendar sources, and an immersive task detail experience.

![Version](https://img.shields.io/badge/version-3.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Design](https://img.shields.io/badge/design-iOS%2026%20Glass-blueviolet.svg)
![AI](https://img.shields.io/badge/AI-Claude%20Powered-orange.svg)

---

## 🔗 Live Demo

👉 [https://aryan-kandula.github.io/TaskManagerPro/TaskManagerPro.html](https://aryan-kandula.github.io/TaskManagerPro/TaskManagerPro.html)

---

## 🌟 Features

### 🎨 iOS 26 Liquid Glass Design
- Full liquid glassmorphic UI inspired by Apple's iOS 26 design language
- Deep navy layered glass on detail panels with triple floating orbs inside
- Dark and light mode with smooth animated toggle — both fully redesigned
- Pill-shaped floating header and navigation consistent across the whole app
- Animated background mesh with drifting color orbs on every page

### 🛬 Landing Page & Onboarding
- Full onboarding landing page that explains every feature before you start
- Step-by-step visual guide walking through each part of the app
- Smooth fade and scale transition into the dashboard on entry
- Remembers returning users and skips the guide automatically
- A Guide button in the header brings the landing page back at any time

### 📋 Task Management
- Create tasks with description, due date, priority, course/category, and notes
- High, Medium, and Low priority system with color-coded urgency scoring
- Urgency score (0–100) auto-calculated from deadline proximity and priority level
- Visual urgency bar on every task card, color-coded from green to red
- Countdown label on each card showing days remaining or days overdue

### 👁️ Task Detail Panel
- Click any task to open an immersive full-screen detail view
- iOS 26 deep blue glassmorphic panel with animated floating orbs inside
- Shows urgency score with animated fill bar, full due date, status, source, and course
- Built-in 25-minute focus timer inside the detail panel itself
- Mark done or delete directly from the detail view without going back

### 🤖 AI Assistant — Powered by Claude
- Connected to the Claude API for genuine task-aware reasoning
- Reads all your tasks and answers questions intelligently in context
- Ask things like "what should I focus on today?" or "am I falling behind?"
- Smart local fallback if the API is unavailable
- Quick question buttons for the most common queries
- Live snapshot panel showing completion rate, overdue count, and next deadline

### 🔄 Auto-Refresh Calendar Sources
- Paste a Canvas or Google Calendar URL once — tasks sync every 5 minutes automatically
- Live badge appears on the header pill when new tasks are detected
- Manual refresh button available at any time from the header
- All sources are managed and removable in the Settings tab

### 📅 Week View
- Full 7-day calendar grid for the current week
- Tasks plotted on each day with clickable chips that open the detail panel
- Overdue days highlighted in red, today highlighted in primary blue

### ⏱ Study Timer
- Pomodoro-style focus timer with an animated SVG ring
- 25-minute, 50-minute, and 5-minute break presets
- Select a specific task to associate with the session
- Toast notification when the session ends

### 📊 Dashboard
- Live animated stat counters for total, pending, done, and overdue tasks
- Upcoming tasks auto-sorted by urgency score — most critical always on top
- Past due section hidden by default with a toggleable reveal button

### 🔍 All Tasks View
- Filter simultaneously by priority, status, and free-text search
- Results sorted by urgency score so the most critical tasks always surface first

### 💾 Data & Privacy
- All data stored locally in your browser — nothing leaves your device
- Export tasks as JSON or CSV from the Settings tab at any time
- No accounts, no tracking, no servers, no backend

---

## 🚀 Getting Started

No installation. No dependencies. No build process.

1. Download or clone the repository
2. Open `TaskManagerPro.html` in any modern web browser
3. Follow the onboarding landing page, then start adding tasks

---

## 💡 Usage

### Adding Tasks
1. Click **+ Add Task** in the header
2. Fill in the description, due date, priority, course, and optional notes
3. Click **Add Task** — it appears immediately, sorted by urgency

### Viewing a Task
Click any task card to open the full detail panel. From there you can mark it done, delete it, start a focus timer, and see the full urgency breakdown.

### Importing from Calendars
1. Click **Import** in the header
2. Paste your Canvas Calendar Feed URL or Google iCal URL
3. Click **Import & Watch** — tasks are imported and the source is saved for auto-refresh going forward

### AI Assistant
1. Open the **AI Assistant** tab
2. Ask anything in natural language, or click one of the quick question buttons
3. The AI reads all your tasks and responds with specific, actionable advice

### Study Timer
1. Open the **Study Timer** tab
2. Select a task from the list on the right
3. Choose a duration preset and click Start — the animated ring tracks your session

### Dark / Light Mode
Click the toggle pill in the top-right of the header to switch themes instantly. Your choice is remembered across sessions.

---

## 🎨 Design System

Task Manager Pro v3.0 uses a full CSS token system modeled after iOS 26 liquid glass principles.

| Token | Purpose |
|---|---|
| `--glass` | Primary surface background |
| `--glass-2` / `--glass-3` | Elevated surface layers |
| `--glass-strong` | Toasts and high-contrast overlays |
| `--blur` | `blur(40px) saturate(1.8)` — main glass effect |
| `--pri` | Primary blue accent |
| `--acc` | Red/pink danger accent |
| `--grn` | Green success accent |
| `--gld` | Gold/warning accent |
| `--purp` | Purple gradient accent |

Both dark and light themes are fully implemented with distinct orb colors, shadow depths, and glass opacities.

---

## 🔧 Technical Details

**Technologies:** HTML5 · CSS3 · Vanilla JavaScript · Claude API · LocalStorage API · Fetch API

**Browser Compatibility:** Chrome / Edge (recommended) · Firefox · Safari · Opera

Requires JavaScript and LocalStorage to be enabled.

---

## 📁 File Structure

```
TaskManagerPro/
│
├── TaskManagerPro.html   # Complete single-file application
├── README.md             # Project documentation
├── CHANGELOG.md          # Version history
└── LICENSE               # MIT License
```

---

## 🔐 Privacy & Security

- No tracking or analytics
- No accounts or logins required
- No servers or backend
- All task data stays in your browser's localStorage
- Export regularly — clearing browser data will remove all tasks

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch — `git checkout -b feature/YourFeature`
3. Commit your changes — `git commit -m "Add YourFeature"`
4. Push the branch — `git push origin feature/YourFeature`
5. Open a Pull Request

### Ideas for Contributions
- Task categories and labels
- Recurring tasks
- Drag-and-drop reordering
- Mobile-first layout improvements
- Custom theme builder
- Multi-language support

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

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Aryan Kandula**  
[github.com/aryan-kandula](https://github.com/aryan-kandula)

---

## ⭐ Support the Project

If you find Task Manager Pro useful:
- ⭐ Star this repository
- 🧑‍💻 Share it with fellow students
- 🔧 Contribute a feature

---

Made with ❤️ by Aryan Kandula

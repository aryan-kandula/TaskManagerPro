# Task Manager Pro

A modern, student-focused task management application built with vanilla JavaScript and powered by Claude AI.  
Featuring a full iOS 26-style liquid glassmorphic design, intelligent AI assistance, smart tagging, time-aware scheduling, and an immersive task detail experience.

![Version](https://img.shields.io/badge/version-3.2.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Design](https://img.shields.io/badge/design-iOS%2026%20Glass-blueviolet.svg)
![AI](https://img.shields.io/badge/AI-Claude%20Powered-orange.svg)

---

## 🔗 Live Demo

👉 [https://aryan-kandula.github.io/TaskManagerPro](https://aryan-kandula.github.io/TaskManagerPro)

---

## ✨ Version 3.2 Features

### ⏰ Time-Based Scheduling

Tasks now support an optional **time field** (HH:MM, 24-hour format):

- If a time is provided, it displays alongside the date on every card and in the detail panel
- If no time is set, the task is treated as an **all-day item** (defaults to end-of-day for urgency)
- **Urgency scoring is now fully time-aware** — a task due in 3 hours scores dramatically higher than one due in 8 hours, even on the same date
- Within-day ordering: earlier time = higher urgency, so morning classes rank above afternoon ones

### 🏷️ Smart Tagging System

Every task can have multiple tags — both user-defined and auto-detected:

- **User tags**: Add any tags while creating a task. Press `Enter`, `,`, or `Space` to commit a tag. Backspace removes the last one. Tags are displayed as colored pill badges throughout the app
- **Auto tags**: On creation and import, task names are scanned for keywords. Matching tasks get tags automatically — these never override tags you set yourself
- **Tag types with distinct colors**:
  - `exam` — red/pink
  - `assignment` — gold
  - `class` — purple
  - `holiday` — green
  - `event` — orange
  - custom tags — neutral glass
- Tags are searchable in the **All Tasks** search bar

### 🗂️ Task Type Classification

Each task now has a **type** field:

| Type | Description |
|---|---|
| `task` | General to-do (default) |
| `assignment` | Coursework with a submission deadline |
| `class` | Lecture, lab, or scheduled session |
| `exam` | Test, quiz, midterm, or final |
| `event` | Meeting, club, or workshop |
| `holiday` | Break or no-class day |

- Type is shown as a color-coded badge on every card
- Filter by type in the **All Tasks** tab using the new Type dropdown
- Auto-detected from task name on creation and import — manual override always available

### 🤖 AI-Assisted Categorization (Development Mode)

When creating or importing tasks, the AI categorization engine scans task names and:
- Infers the most likely **type** (exam, assignment, class, etc.)
- Applies **auto tags** matching the content
- Uses **priority inference** (unchanged from v3.1)

> ⚠️ **AI features are in development mode.** A visible disclaimer appears in the AI Assistant tab. Results may not always be accurate — always double-check important tasks.

---

## 🌟 Full Feature List

### 🎨 iOS 26 Liquid Glass Design
- Full liquid glassmorphic UI inspired by Apple's iOS 26 design language
- Deep navy layered glass on detail panels with triple animated floating orbs
- Dark and light mode with smooth animated toggle — both fully redesigned
- Pill-shaped floating sticky header and pill navigation throughout
- Animated background mesh with drifting color orbs on every page
- Dynamic canvas favicon — rainbow gradient rounded-square with checkmark, generated at runtime

### 🛬 Landing Page & Onboarding
- Full onboarding landing page that explains every feature before you start
- Smooth fade and scale transition into the dashboard on entry
- Remembers returning users and skips the guide automatically
- A **← Guide** button in the app header brings the landing page back at any time

### 📋 Task Management
- Create tasks with description, due date, **time**, priority, type, **tags**, course/category, and notes
- High, Medium, and Low priority with color-coded urgency scoring
- Urgency score (0–100) auto-calculated from deadline proximity, **time of day**, and priority level
- Visual urgency bar on every task card, color-coded from green to red

### 🧠 Smart Auto-Priority Detection
- Task names are scanned automatically to infer priority on every import
- **High**: exam, final, midterm, test, quiz, capstone, sprint
- **Medium**: lab, assessment, assignment, homework, module lab, hands-on
- **Low**: exercise, guided, attendance, survey, podcast, discussion, EC, career

### 👁️ Task Detail Panel
- Click any task to open an immersive full-screen detail view
- Shows urgency score (time-aware), full due date and time, status, type, tags, source, and course
- Built-in focus timer with custom duration input (up to 600 min)
- Mark done or delete directly from the detail view

### 🤖 AI Assistant — Powered by Claude
Connects to the Claude API and has full awareness of all your tasks, deadlines, priorities, and courses.
> ⚠️ AI features are in development mode. Results may not always be accurate. Please double-check important tasks.

### 🔄 Auto-Refresh Calendar Sources
- Paste a Canvas or Google Calendar URL once — tasks sync every 5 minutes
- Imported tasks get auto-priority, auto-type, and auto-tags applied on arrival

### 📅 Week View
- Full 7-day calendar grid with left/right arrow navigation between weeks
- Click any day tile to filter tasks for that specific day

### ⏱ Study Timer
- Pomodoro-style timer with animated SVG gradient ring
- 25-min, 50-min, and 5-min break presets plus custom duration input

### 📊 Dashboard
- Animated stat counters — all clickable to navigate to filtered views
- Past Due section with bulk Mark All Done / Mark Range Done actions

### 🔍 All Tasks View
- Filter by priority, status, **type**, and free-text search (searches task name, notes, course, tags)
- Results always sorted by urgency score

### 💾 Data & Privacy
- All data stored locally — nothing leaves your device
- Export as JSON or CSV (CSV now includes time, type, and tags columns)

---

## 🚀 Getting Started

No installation. No dependencies. No build process.

1. Download or clone the repository
2. Open `index.html` in any modern web browser
3. Follow the onboarding guide, then start adding tasks

---

## 💡 Usage

### Adding Tasks
Click **+ Add Task**, fill in the description, due date, optional time, priority, type, tags, course, and notes, then click **Add Task**. Type is auto-detected from the task name if left as default.

### Tagging Tasks
In the tag input, type a tag and press `Enter` or `,` to add it. Press `Backspace` to remove the last tag. Tags show as colored pills throughout the app.

### Importing from Calendars
Click **Import**, paste a Canvas or Google iCal URL and click **Import & Watch**, or upload a `.ics` file. Imported tasks receive auto-priority, auto-type, and auto-tags.

### Filtering by Type
In the **All Tasks** tab, use the **Type** dropdown alongside priority and status filters.

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

- No tracking or analytics · No accounts or logins · No servers or backend
- All task data in localStorage only
- Export regularly — clearing browser data removes tasks

---

## 🧪 Rapid Prototyping Process

This project was developed using an AI-assisted rapid prototyping workflow.

### Approach
- Created a Product Requirements Document (PRD) to define the MVP scope
- Used Claude AI as the primary tool to generate and iterate on the application
- Compared outputs with other AI tools for refinement
- Repeatedly tested and improved features through structured iterations

### Key Takeaways
- AI tools accelerate development but require careful testing and debugging
- Iteration is essential for refining both functionality and user experience
- Clear documentation improves both development speed and final quality

### Supporting Documentation
- `PRD.md` — Product requirements and scope definition  
- `PROTOTYPE_TESTING.md` — Comparison of AI-generated prototypes  
- `ITERATION_LOG.md` — Step-by-step development and refinement process  

## 🤝 Contributing

1. Fork the repository
2. Create a branch — `git checkout -b feature/YourFeature`
3. Commit — `git commit -m "Add YourFeature"`
4. Push — `git push origin feature/YourFeature`
5. Open a Pull Request

---

## 🗺️ Roadmap

- [ ] Recurring tasks
- [ ] Drag-and-drop task ordering
- [ ] Browser push notifications for deadlines
- [ ] Mobile-first UI overhaul
- [ ] Theme customization panel
- [ ] AI categorization accuracy improvements

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.

---

## 👤 Author

**Aryan Kandula**  
[github.com/aryan-kandula](https://github.com/aryan-kandula)

---

Made by Aryan Kandula

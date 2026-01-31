# Task Manager Pro

A modern, feature-rich task management application built with vanilla JavaScript. Task Manager Pro helps you stay organized with an intuitive interface, smart AI assistant, and powerful calendar integrations.

![Task Manager Pro](https://img.shields.io/badge/version-2.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 🌟 Features

### Core Functionality
- **Task Management**: Create, edit, and delete tasks with ease
- **Priority System**: Organize tasks by priority (High, Medium, Low)
- **Due Dates**: Set and track due dates for all your tasks
- **Task Notes**: Add detailed descriptions and notes to any task
- **Completion Tracking**: Mark tasks as complete and track your progress
- **Duplicate Tasks**: Support for multiple instances of the same task

### Smart Organization
- **Dashboard View**: Quick overview of all your tasks at a glance
- **Upcoming Tasks**: See tasks that are coming up, sorted by date
- **Past Due Section**: Separate, toggleable section for overdue tasks
- **Statistics**: Real-time stats showing total, pending, completed, and overdue tasks
- **Flexible Sorting**: Tasks automatically organized by date and completion status

### AI Assistant
The built-in AI assistant understands natural language queries about your tasks:
- "What tasks do I have until Feb 10?"
- "Show me tasks on March 15"
- "What are my high priority tasks?"
- "What tasks are overdue?"
- "What's my completion rate?"
- "What tasks do I have today/tomorrow?"
- "Show me tasks this week/next week"

### Calendar Integration
Import tasks from your favorite calendar applications:
- **Google Calendar**: Import via iCal URL
- **Canvas LMS**: Direct integration with Canvas calendar
- **ICS Files**: Upload any standard .ics calendar file

### Data Management
- **Local Storage**: All data stored securely in your browser
- **Export Options**: Export tasks to JSON or CSV format
- **Import/Export**: Backup and restore your tasks anytime
- **Data Persistence**: Tasks saved automatically

## 🚀 Getting Started

### Quick Start
1. Download `TaskManagerPro.html`
2. Open the file in any modern web browser
3. Start adding tasks!

No installation, no dependencies, no build process required.

### First Time Setup
1. Click the **"+ Add Task"** button to create your first task
2. Fill in the task description, due date, priority, and optional notes
3. Your task will appear on the dashboard automatically
4. Use the AI Assistant tab to ask questions about your tasks

## 💡 Usage

### Adding Tasks
1. Click **"+ Add Task"** in the header
2. Enter task details:
   - Task description (required)
   - Due date (required)
   - Priority level (Low/Medium/High)
   - Additional notes (optional)
3. Click **"Add Task"** to save

### Managing Tasks
- **Complete a task**: Click the checkbox next to the task
- **Delete a task**: Click the "Delete" button on the task card
- **View past due**: Click "Show Past Due Tasks" to toggle the past due section

### Using the AI Assistant
1. Navigate to the **"AI Assistant"** tab
2. Type your question in natural language
3. Press Enter or click Send
4. The assistant will analyze your tasks and provide relevant information

### Importing from Calendars
1. Click **"Import"** in the header
2. Choose your calendar source:
   - **Google Calendar**: Paste your iCal feed URL
   - **Canvas**: Paste your Canvas calendar feed URL
   - **ICS File**: Upload a .ics file from your computer
3. Click the corresponding import button
4. Tasks will be automatically added to your list

### Exporting Data
1. Go to the **"Settings"** tab
2. Choose your export format:
   - **JSON**: Full data export with all task details
   - **CSV**: Spreadsheet-compatible format
3. Your browser will download the file

## 🎨 Design

Task Manager Pro features a modern, glassmorphic design with:
- Dark theme optimized for reduced eye strain
- Smooth animations and transitions
- Responsive layout that works on all devices
- Color-coded priority system
- Gradient accents and visual feedback

## 🔧 Technical Details

### Technologies Used
- **HTML5**: Semantic markup and structure
- **CSS3**: Modern styling with flexbox, grid, and animations
- **Vanilla JavaScript**: No frameworks or libraries required
- **LocalStorage API**: Client-side data persistence
- **Fetch API**: Calendar integration and CORS proxy support

### Browser Compatibility
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

Requires a modern browser with JavaScript and LocalStorage enabled.

### File Structure
```
TaskManagerPro/
│
├── TaskManagerPro.html          # Main application file
├── README.md                     # This file
└── LICENSE                       # MIT License
```

## 📊 Data Storage

All task data is stored locally in your browser using the LocalStorage API. This means:
- ✅ Your data never leaves your computer
- ✅ No account or login required
- ✅ Complete privacy
- ⚠️ Data is specific to each browser
- ⚠️ Clearing browser data will remove tasks

**Recommendation**: Regularly export your tasks as a backup.

## 🔐 Privacy & Security

- **No tracking**: Task Manager Pro does not collect any user data
- **No analytics**: No third-party analytics or tracking scripts
- **Local-only**: All data stays on your device
- **No servers**: Application runs entirely in your browser
- **Open source**: Full transparency - inspect the code yourself

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Ideas for Contributions
- Additional calendar integrations
- More AI assistant capabilities
- Task categories and tags
- Recurring tasks
- Mobile app version
- Theme customization
- Multi-language support

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Aryan Kandula**

## 🙏 Acknowledgments

- Inspired by modern productivity apps
- Built with a focus on simplicity and user experience
- Designed for students and professionals alike

## 📮 Support

If you encounter any issues or have questions:
1. Check the existing issues in the repository
2. Open a new issue with a detailed description
3. Include browser version and steps to reproduce any bugs

## 🗺️ Roadmap

Future features planned:
- [ ] Task categories and labels
- [ ] Recurring tasks
- [ ] Task sharing capabilities
- [ ] Mobile-optimized interface
- [ ] Custom themes
- [ ] Task reminders
- [ ] Search and filter functionality
- [ ] Drag-and-drop task reordering

## ⭐ Show Your Support

If you find Task Manager Pro useful, please consider:
- Starring this repository
- Sharing it with others
- Contributing to the project

---

Made with ❤️ by Aryan Kandula

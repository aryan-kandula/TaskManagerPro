# Task Manager Pro — Product Requirements Document (PRD)

## 1. Project Overview

**What it does:**  
Task Manager Pro is a single-page web application that helps students manage tasks, deadlines, and study schedules with AI-assisted planning.

**Target Users:**  
- College students  
- Anyone managing assignments, deadlines, and study sessions  

**Problem it Solves:**  
Students struggle to organize tasks across multiple platforms (Canvas, calendars, notes). This app centralizes tasks, prioritizes work, and provides intelligent guidance.

---

## 2. Core Features (MVP)

### 1. Task Management System
**Description:**  
Users can create, edit, delete, and mark tasks as complete.

**Why it matters:**  
Core functionality for tracking academic work.

**Success Criteria:**  
- Tasks can be added with details (date, priority, type)
- Tasks persist using local storage
- Users can mark tasks as done

---

### 2. Calendar & Weekly View
**Description:**  
Displays tasks across a weekly layout with navigation.

**Why it matters:**  
Helps users visualize workload and plan ahead.

**Success Criteria:**  
- Users can switch between weeks
- Tasks are grouped by day
- Today’s date is highlighted

---

### 3. Study Timer (Pomodoro + Custom)
**Description:**  
Built-in timer to help users focus on tasks.

**Why it matters:**  
Encourages productivity and time management.

**Success Criteria:**  
- Timer starts, pauses, resets correctly
- Users can set custom durations
- Timer visually updates

---

### 4. AI Assistant (Basic Integration)
**Description:**  
Provides suggestions and scheduling help based on tasks.

**Why it matters:**  
Adds intelligent planning support.

**Success Criteria:**  
- User can input questions
- AI responds with suggestions
- UI supports chat interaction

---

## 3. User Experience

### Entry Flow:
1. User lands on landing page
2. Clicks "Get Started"
3. Enters dashboard

### Main Actions:
- Add tasks
- View tasks (dashboard / list / week view)
- Use timer
- Ask AI for help

### Interaction Behavior:
- Clicking tasks opens detail view
- Filters refine task visibility
- Bulk actions improve efficiency

---

## 4. Technical Constraints

- Single Page Application (SPA)
- Built with HTML, CSS, JavaScript
- No backend/server required
- Uses browser localStorage
- Runs directly in browser

---

## 5. Out of Scope (Future Features)

- User accounts / authentication
- Cloud sync across devices
- Real AI API integration (currently simulated)
- Notifications/reminders
- Mobile app version

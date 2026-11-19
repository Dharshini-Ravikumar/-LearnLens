# LearnLens – AI-Powered Smart Learning & Academic Management System
> **Tagline:** *Learn Smarter. Teach Better. Manage Efficiently.*

LearnLens is an educational web application designed to connect **Students**, **Faculty Members**, and **Administrators** through three integrated, reactive modules. The platform improves the educational experience by analyzing academic performance, identifying learning gaps, providing personalized study recommendations, monitoring student progress with early warning triggers, and simplifying institutional management.

---

## 🚀 Key Highlights & Architectural Strengths

- **No Frontend Framework Overhead:** Crafted with clean, modular HTML5, modern CSS3, and vanilla JavaScript (ES6+).
- **Single-Source-of-Truth Data Architecture:** Powered by a shared LocalStorage State Store (`js/data.js`) with an event-driven pub/sub pattern that coordinates live updates across all three modules without requiring a paid backend.
- **Interactive Visualizations:** Chart.js powered radar competency charts, multi-bar performance distributions, attendance doughnut gauges, and departmental comparative analytics.
- **Cognitive Offline AI Assistant:** Features a local curriculum knowledge base (covering DSA, DBMS, Web Development, Machine Learning, and Computer Networks) that provides instant concept explanations, time complexity breakdowns, and SQL normalization rules.
- **Ready for Production Extensibility:** Structured so that genuine backend microservices (Node.js/Django/Spring) and real LLM APIs (Gemini/OpenAI) can be integrated seamlessly.

---

## 🔑 Demo Accounts & 1-Click Quick Access

Both the landing page (`index.html`) and the dedicated login page (`login.html`) include **1-Click Demo Login cards** for instant evaluation.

| Role | Email | Password | Representative Persona |
| :--- | :--- | :--- | :--- |
| **Student** | `student@learnlens.com` | `Student123` | **Alex Rivera** (3rd Year CSE, Roll: `CS2023-0101`) |
| **Faculty** | `faculty@learnlens.com` | `Faculty123` | **Dr. Robert Vance** (Professor & Head of CSE) |
| **Admin** | `admin@learnlens.com` | `Admin123` | **Dr. Eleanor Vance** (Academic Dean & Super Admin) |

*Additional realistic student profiles (such as Marcus Johnson for testing critical academic alerts, and Sophia Chen for high achiever metrics) can be accessed via the User Management table in the Admin portal.*

---

## 🌟 6 Unique Innovative Features

1. **Smart Learning Gap Detector:**
   - Evaluates marks, midterms, and quiz mistakes against a configurable mastery threshold (default: 65%).
   - Flags specific concept deficits (e.g. *Gradient Descent Cost Convergence* in ML or *AVL Rotations* in DSA).
   - Generates four actionable remedies: *Concept Revision*, *Targeted Practice Exercises*, *Faculty Mentoring Request*, and *Diagnostic Quizzes*.

2. **Early Academic Warning System:**
   - Multi-factor automated triage engine detecting students at risk based on:
     - Marks below **40%** (Critical Academic Alert) or below **50%** (Performance Warning).
     - Attendance below **75%** (Statutory Shortfall) or below **65%** (Critical Deficit).
     - Overdue assignments backlog.
   - Allows faculty to review, acknowledge, and initiate formal counseling interventions.

3. **Personalized Study Roadmap:**
   - Dynamically synthesizes identified learning gaps, impending assignment deadlines, and available study hours into an adaptive 7-day study plan.

4. **Faculty Intervention Tracker:**
   - Documents 1-on-1 counseling, remedial sessions, and prescribed practice.
   - Quantifies the **Impact Delta** (e.g. Liam Patel improving from **48% → 73%**, recording a **+25% score gain** post-mentoring).

5. **Institutional Intelligence:**
   - Gives academic leaders macro-level analytics on departmental performance gaps, pass-fail distributions, and curriculum balance across CSE, IT, and Data Science.

6. **Learning Progress Comparison:**
   - Allows students to benchmark current marks against previous semesters with net gain/loss indicators and trajectory status (*Significant Improvement*, *Steady*, *Needs Focus*).

---

## 🔄 Cross-Module Data Sharing In Action

All three modules interact through a shared persistence layer:
1. **Assignment Evaluation:** When a student submits an assignment deliverable in the Student Module, it appears in the Faculty Grading Queue. When faculty grades it with marks and feedback, the student's marks and GPA recalculate instantly.
2. **Attendance Matrix:** When faculty marks daily attendance in the matrix and saves records, the student's Attendance Tracker updates in real-time, recalculating compliance and warning flags.
3. **Curriculum Updates:** When an administrator adds an academic subject or enrolls a student in the Admin Module, the updates immediately propagate to faculty course lists and student dashboards.
4. **Broadcast Announcements:** When faculty or admin publishes announcements, they appear instantly on student dashboards.

---

## 📁 Project Directory Structure

```text
LearnLens/
├── index.html           # Landing page with feature showcases, platform metrics & 1-click demo launchers
├── login.html           # Dedicated role-based login portal with credentials cheat sheet
├── student.html         # Student portal (Dashboard, Analyzer, Gap Detector, Planner, Quizzes, AI Tutor, Report)
├── faculty.html         # Faculty portal (Dashboard, Student Rosters, Attendance Matrix, Grading, Early Warnings)
├── admin.html           # Admin portal (Overview, Student/Faculty CRUD, Curriculum, Institution Analytics, Reports)
│
├── css/
│   ├── style.css        # Lavender, indigo & soft blue design system, responsive grid, modals, toasts, cards
│   ├── login.css        # Login & hero card styling
│   ├── student.css      # Quiz runner, study checklist, AI chat bubble, progress report styling
│   ├── faculty.css      # Attendance matrix, grading panel, triage badges, intervention tracker styling
│   └── admin.css        # Department health cards, accreditation print templates
│
├── js/
│   ├── data.js          # Shared LocalStorage store, realistic seed data (10 students, 3 faculty, 3 depts, 5 subjects)
│   ├── auth.js          # Client-side demo RBAC, session management & route guards
│   ├── common.js        # UI utilities: Toast engine, modal manager, confirmations, date formatters
│   ├── analytics.js     # Learning Gap Detector engine, Early Warning System rules, Chart.js visualizers
│   ├── student.js       # Student portal controller
│   ├── faculty.js       # Faculty portal controller
│   └── admin.js         # Admin portal controller
│
└── README.md            # Comprehensive project documentation & usage guide
```

---

## 💻 How to Run the Application

Because LearnLens uses plain HTML5, CSS3, JavaScript, and LocalStorage, **no installation, build step, or npm packages are required**.

### Option 1: Direct Browser Launch
1. Navigate to the project folder (`C:\hackathon`).
2. Double-click `index.html` or `login.html` to open it in your browser (Chrome, Edge, Firefox, Safari).
3. Click any of the **1-Click Demo Login** buttons to immediately explore the Student, Faculty, or Admin dashboards.

### Option 2: Using Any Local Web Server
You can serve the files with any lightweight HTTP server:
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# VS Code
Right-click index.html and select "Open with Live Server"
```
Then visit `http://localhost:8080` in your web browser.

---

## 🧪 Testing Checklist & Verification

- [x] **Navigation:** All sidebar items switch views cleanly without page reloads.
- [x] **Role Access:** Direct URLs to `student.html`, `faculty.html`, or `admin.html` without appropriate credentials redirect to `login.html`.
- [x] **Demo Switcher:** Top-right profile dropdown allows 1-click switching between Student, Faculty, and Admin at any time.
- [x] **Reset Data:** Top-right profile dropdown includes a *"Reset Demo Data"* button that restores the pristine seed dataset at any time.
- [x] **Interactive Quizzes:** Real-time countdown timer, multiple-choice options, instant score calculation, and question-by-question review with explanations.
- [x] **AI Assistant:** Type academic questions (or click prompt pills) to receive instant explanations from the local knowledge base.
- [x] **Print-Ready Reports:** Both the Student Progress Report and Admin Accreditation Report include `@media print` stylesheets for clean printing.

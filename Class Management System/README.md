# 🎓 Class Management System

> **A modern, role-based academic management platform designed to bring students, teachers, administrators, attendance, learning resources, announcements, and academic records into one secure workspace.**

![Class Management System](https://img.shields.io/badge/Project-Class%20Management%20System-4F46E5?style=for-the-badge)
![React](https://img.shields.io/badge/Frontend-React-61DAFB?style=for-the-badge\&logo=react\&logoColor=white)
![TypeScript](https://img.shields.io/badge/Language-TypeScript-3178C6?style=for-the-badge\&logo=typescript\&logoColor=white)
![Express](https://img.shields.io/badge/Backend-Express-000000?style=for-the-badge\&logo=express\&logoColor=white)
![Vite](https://img.shields.io/badge/Build-Vite-646CFF?style=for-the-badge\&logo=vite\&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/UI-Tailwind%20CSS-06B6D4?style=for-the-badge\&logo=tailwindcss\&logoColor=white)

---

## ✨ Overview

**Class Management System (CMS)** is a full-stack web application built to simplify and centralize academic administration.

Instead of managing announcements, subjects, attendance, notes, student records, and permissions across multiple disconnected tools, CMS provides a unified institutional workspace with **role-based access control, granular permissions, audit logging, file management, and database administration**.

The system is designed around three core user roles:

* 👑 **Main Administrator**
* 👨‍🏫 **Teacher**
* 🎓 **Student**

Each role receives an experience and access level appropriate to its responsibilities.

---

## 🚀 Why This Project?

Modern educational environments need more than a basic CRUD dashboard.

This project focuses on building an **institutional-grade management experience** that combines:

🔐 Secure authentication
🛡️ Role-based authorization
🎯 Granular resource permissions
📚 Subject & class management
📝 Digital notes and study materials
📢 Academic announcements
✅ Attendance management
👨‍🎓 Student records
📊 Academic class logs
🧾 Security audit trails
🗄️ Database/schema management
📎 File uploads
⚙️ System configuration

The result is a centralized platform where academic operations can be managed from a single interface.

---

# 🌟 Core Features

## 📊 Dashboard & Overview

A centralized dashboard gives users a quick overview of the academic environment.

Depending on their role and permissions, users can access:

* Subjects
* Announcements
* Notes
* Attendance
* Students
* Academic activity
* Administrative controls
* Database tools

The interface dynamically adapts to the logged-in user's permissions.

---

## 👑 Main Admin Control Center

The **Main Admin** has complete control over the platform.

Administrators can:

* Create and manage users
* Assign roles
* Activate/deactivate accounts
* Manage subjects
* Configure user permissions
* Review audit logs
* Manage system settings
* Inspect the database schema
* Import data
* Seed demo data
* Reset database data
* Export SQL DDL
* Manage uploaded resources

The admin role also has a full-access permission bypass for system resources.

---

## 🛡️ Granular Permission System

One of the major features of this project is its **resource-level Access Control List (ACL)**.

Permissions can be configured for different sections:

```text
Announcements
Subjects
Notes
Attendance
Students
Admin
```

And each permission can define:

```text
READ
CREATE
EDIT
DELETE
```

Permissions may also be scoped to a **specific subject** rather than the entire section.

### Example

A teacher could have:

```text
Subjects → Read
Subjects → Create
Subjects → Edit
Notes → Read
Notes → Create
Attendance → Read
Attendance → Edit
```

while another user may have access to only a single subject.

This creates a flexible authorization model suitable for different academic environments.

---

# 🔐 Authentication & Security

Security is built directly into the backend architecture.

### Authentication Features

* Session-based token authentication
* Bearer token support
* Password hashing with **bcrypt**
* Session expiration
* Logout/session invalidation
* Account status validation
* Role-based authorization
* Resource-level permissions
* Authentication rate limiting

### Security Logging

Administrative and data-changing operations are recorded in an audit trail containing information such as:

```text
User
Role
Action
Entity
Entity ID
Details
Timestamp
IP Address
```

This makes it easier to track important system activity and investigate administrative changes.

---

# 📚 Subject Management

The subject module provides a centralized academic structure.

Each subject can contain:

* Subject name
* Course code
* Department
* Description
* Thumbnail
* Attached syllabus/file
* Assigned teachers
* Class records
* Related notes

Teachers can also maintain academic records for their assigned subjects.

---

# 🧑‍🏫 Academic Class Records

Teachers can log what happened during each class session.

A class record contains:

```text
Date
Topic Covered
Class Notes
Teacher
Subject
```

This creates a historical academic record of what was taught throughout the term.

---

# 📝 Notes & Learning Materials

The Notes module allows academic resources to be organized by subject.

Notes support:

* Titles
* Content
* Subject association
* File attachments
* File names
* File metadata
* Search/filtering
* Editing
* Deletion

This gives students and teachers a centralized place to manage study materials.

---

# 📢 Announcements

The announcement system provides institution-wide communication.

Announcements support:

* Title
* Description
* Priority
* Thumbnail/banner
* Attachments
* Posting user
* Timestamp

Priority levels include:

```text
NORMAL
IMPORTANT
URGENT
```

This makes it easier to highlight important academic notices.

---

# ✅ Attendance Management

The attendance module provides subject-based attendance tracking.

Supported statuses include:

* ✅ Present
* ❌ Absent
* 🕒 Late
* 📌 Excused

Attendance can be queried by:

```text
Subject
Student
Date
```

The system also provides attendance statistics and supports attendance export.

---

# 👨‍🎓 Student Management

Student profiles include information such as:

```text
Name
Roll Number
Email
Phone
Class
Section
Enrollment
Profile Image
```

Students can be associated with their login accounts and enrolled subjects.

Teachers and administrators can access student information according to their permissions.

---

# 🧾 Audit Logs

The platform maintains a security-oriented audit trail of administrative and data operations.

Example events include:

```text
SYSTEM_BOOTSTRAP
USER_CREATED
USER_UPDATED
PERMISSIONS_UPDATED
SUBJECT_CREATED
ATTENDANCE_UPDATED
DATABASE_OPERATION
```

The system retains the latest audit records to provide visibility into platform activity.

---

# 🗄️ Database & Data Management

The project includes a dedicated database management interface.

Administrators can:

* Inspect table structures
* View schema definitions
* Ingest records
* Seed demo data
* Reset application data
* Export SQL DDL

The application currently persists runtime application data in a structured JSON database file:

```text
data/database.json
```

The repository also includes a relational SQL schema blueprint:

```text
server/schema.sql
```

The SQL schema is designed around relational tables such as:

```text
users
user_permissions
subjects
subject_teachers
class_records
notes
announcements
students
attendance
audit_logs
system_settings
```

This makes the architecture easier to migrate toward a production relational database.

---

# 📎 File Upload Support

The backend provides file upload handling for academic resources and announcements.

Uploaded files are stored through the application's:

```text
uploads/
```

directory and exposed through the server for application access.

---

# ⚙️ System Settings

Administrators can configure institution-wide settings such as:

* School name
* School tagline
* Academic term
* Theme
* Announcement banner
* Registration-related settings

This allows the application to be adapted to different institutions without changing the core application code.

---

# 🏗️ Tech Stack

## Frontend

* **React 19**
* **TypeScript**
* **Vite**
* **Tailwind CSS**
* **Lucide React**
* **Motion**

## Backend

* **Node.js**
* **Express**
* **TypeScript**
* **tsx**
* **bcryptjs**
* **Multer**

## Data & Architecture

* JSON-based persistent application storage
* Relational SQL schema blueprint
* REST-style API architecture
* File upload handling
* Token-based authentication
* Role-based authorization
* Granular ACL permissions
* Audit logging

---

# 🧩 Application Architecture

```text
                         ┌────────────────────────┐
                         │      React Frontend     │
                         │                        │
                         │  Dashboard              │
                         │  Subjects               │
                         │  Notes                  │
                         │  Attendance             │
                         │  Students               │
                         │  Announcements          │
                         │  Admin                  │
                         └───────────┬────────────┘
                                     │
                                     │ REST API
                                     ▼
                         ┌────────────────────────┐
                         │     Express Backend     │
                         │                        │
                         │ Authentication         │
                         │ Authorization          │
                         │ CRUD APIs              │
                         │ File Uploads           │
                         │ Audit Logging          │
                         │ Database Operations    │
                         └───────────┬────────────┘
                                     │
                    ┌────────────────┴────────────────┐
                    │                                 │
                    ▼                                 ▼
          ┌──────────────────┐              ┌──────────────────┐
          │ JSON Persistence │              │   SQL Schema     │
          │ data/database.json│              │ server/schema.sql │
          └──────────────────┘              └──────────────────┘
```

---

# 📁 Project Structure

```text
class-management-system/
│
├── src/
│   ├── components/
│   │   ├── AdminView.tsx
│   │   ├── AnnouncementsView.tsx
│   │   ├── AttendanceView.tsx
│   │   ├── DatabaseSchemaView.tsx
│   │   ├── LoginModal.tsx
│   │   ├── Navbar.tsx
│   │   ├── NotesView.tsx
│   │   ├── OverviewView.tsx
│   │   ├── SettingsView.tsx
│   │   ├── Sidebar.tsx
│   │   ├── StudentsView.tsx
│   │   ├── SubjectsView.tsx
│   │   └── SubjectDetailModal.tsx
│   │
│   ├── lib/
│   │   └── api.ts
│   │
│   ├── App.tsx
│   ├── index.css
│   ├── main.tsx
│   └── types.ts
│
├── server/
│   ├── auth.ts
│   ├── db.ts
│   ├── routes.ts
│   └── schema.sql
│
├── server.ts
├── package.json
├── vite.config.ts
├── tsconfig.json
├── .env.example
└── README.md
```

---

# 🛠️ Getting Started

## Prerequisites

Make sure you have installed:

* **Node.js**
* **npm**

---

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/class-management-system.git
cd class-management-system
```

---

## 2. Install Dependencies

```bash
npm install
```

---

## 3. Configure Environment Variables

Create a local environment file based on:

```bash
.env.example
```

Then configure the required application variables for your environment.

> Do not commit API keys, secrets, or production credentials to GitHub.

---

## 4. Run the Development Server

```bash
npm run dev
```

The application will be available through the server configured in `server.ts`.

---

# 📦 Production Build

Build the frontend and backend bundle with:

```bash
npm run build
```

Then start the production server:

```bash
npm start
```

---

# 🧪 Type Checking

Run TypeScript validation with:

```bash
npm run lint
```

---

# 👤 User Roles

| Role          | Purpose                                                                    |
| ------------- | -------------------------------------------------------------------------- |
| 👑 Main Admin | Complete system administration                                             |
| 👨‍🏫 Teacher | Manage teaching resources, records and attendance according to permissions |
| 🎓 Student    | Access enrolled academic resources and student-specific information        |

---

# 🔄 Typical Workflow

```text
Login
  ↓
Authentication
  ↓
Role & Permission Resolution
  ↓
Dashboard
  ↓
Academic Module
  ├── Announcements
  ├── Subjects
  ├── Notes
  ├── Attendance
  └── Students
  ↓
Audit Logging
```

---

# 🎯 Future Improvements

The project provides a strong foundation for extending the platform further.

Potential upgrades include:

* PostgreSQL/MySQL production database
* JWT or secure persistent session architecture
* Email/SMS notifications
* Assignment and submission management
* Timetable and scheduling
* Examination & grading module
* Parent portal
* Real-time notifications
* Advanced analytics dashboards
* Cloud file storage
* Automated backups
* Docker deployment
* CI/CD pipeline
* Multi-institution support

---

# 🔒 Production Security Notice

This repository is intended as a development/academic project and should be reviewed before production deployment.

Before exposing the application publicly:

* Change all default/demo credentials.
* Store secrets outside the repository.
* Use HTTPS.
* Use a production-grade persistent database.
* Review authentication/session handling.
* Restrict file upload types and sizes.
* Add proper CSRF/CORS protections where required.
* Configure secure cookies/tokens and deployment secrets.
* Back up application data regularly.

---

# 💡 What Makes It Different?

This project is more than a conventional student management CRUD application.

It combines:

> **Academic Management + RBAC + Granular ACL + Security Auditing + File Management + Database Administration**

into a single full-stack platform.

The permission architecture is especially useful for institutions where different teachers, administrators, and students require **different levels of access to different academic resources**.

---

# 📸 Screenshots

Add your application screenshots here to make the GitHub repository more visually engaging.

```text
docs/
├── dashboard.png
├── announcements.png
├── subjects.png
├── attendance.png
├── students.png
├── admin-panel.png
└── database-schema.png
```

Example:

```md
![Dashboard](docs/dashboard.png)
![Attendance](docs/attendance.png)
![Admin Panel](docs/admin-panel.png)
```

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome.

```bash
git checkout -b feature/your-feature
git commit -m "Add your feature"
git push origin feature/your-feature
```

Then open a Pull Request.

---

# 📄 License

This project can be released under the license chosen by the project owner.

---

# ⭐ Support the Project

If this project helped you or you found the architecture interesting, consider giving the repository a ⭐.

It helps the project gain visibility and motivates further development.

---

<div align="center">

### 🎓 Class Management System

**Manage Classes. Empower Teachers. Support Students. Secure Academic Data.**

Built with ❤️ using React, TypeScript, Express & modern web technologies.

</div>

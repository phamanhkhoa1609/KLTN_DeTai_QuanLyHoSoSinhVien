# Student Profile Management System

A web-based system that helps universities manage student profiles, academic records, training activities, and student services. The application provides **3 roles** — Administrator, Lecturer, and Student — with separate interfaces, permissions, and business workflows.

- **Frontend:** React (port `3000`)
- **Backend:** Node.js + Express (port `8080`)
- **Database:** MySQL 8
- **File Storage:** Amazon S3 (student photos, news media, attachments)

---

## Demo Accounts

Log in at `/login`. The **username** is the student ID or lecturer ID.

| Role | Username | Password | Page |
|------|----------|----------|------|
| **Student** | `121220255` | `123456` | `/student` |
| **Lecturer** | `1481312` | `123456` | `/teacher` |

> **Note:** The Administrator account is not provided as a demo account. Administrative access is restricted to authorized users.

The default password for newly created accounts is `123456`. On the first login, users may be required to change their password before accessing the system.

---

## Three Roles

### 1. Student (`121220255`)

Students can view and manage **their own academic profile and information**. They cannot manage other users or system-wide data.

**Main Features**

- **Dashboard:** overview, personal information, student photo.
- **Class Schedule / Exam Schedule:** timetable based on registered course sections.
- **Academic Results:** component scores, final grades, and GPA.
- **Curriculum:** course roadmap based on the student's major and study progress.
- **Course Registration:** register for / cancel courses during an open registration period; check class capacity, schedule conflicts, and prerequisite requirements.
- **Financial Status:** tuition fees, outstanding payments, and payment status.
- **Training Results:** view training and conduct results by semester.
- **Scholarships:** view scholarship eligibility and results, if applicable.
- **News:** university announcements, including images, videos, and file attachments.
- **Academic Consultation:** send questions to lecturers of registered course sections and track responses.
- **AI Chatbot:** assistance with grade calculation and academic consultation.
- **Change Password.**

**Quick Demo:**  
Log in with `121220255` / `123456` → view schedule and grades → open Course Registration (when registration is available) → view news / financial status / consultation requests.

---

### 2. Lecturer (`1481312`)

Lecturers are responsible for the **course sections assigned to them**. They cannot manage university-wide departments, majors, tuition fees, or other system-wide configuration.

**Main Features**

- **Dashboard:** lecturer information.
- **Course Sections:** list of assigned course sections.
- **Students in Class:** view students enrolled in each course section.
- **Teaching Schedule:** schedule by class period, room, and campus.
- **Grade Management:** enter coursework, midterm, and final grades during the allowed grading period. Saved grades are normally not editable directly; administrative approval is required for corrections.
- **News:** view announcements for lecturers.
- **Academic Consultation:** receive and respond to student consultation requests and update their status.
- **Change Password.**

**Quick Demo:**  
Log in with `1481312` / `123456` → open a course section → enter grades (if the grading period is open) → view teaching schedule → respond to consultation requests.

---

### 3. Administrator

The Administrator operates and manages the **entire system**, including system configuration, users, academic data, financial information, and administrative processes.

**User & Profile Management**

- Account management: lock / unlock accounts and manage permissions.
- Student and lecturer management: create, update, delete, import from Excel, and upload student photos to S3.

**University Management**

- Departments, majors, and administrative classes.
- Courses, course sections, and lecturer assignments.
- Class schedules / sessions and holidays.

**Academic & Registration Management**

- Course registration periods (open / close).
- Edit finalized grades when necessary.
- Import and manage training results.
- Import and manage English certificates.
- Scholarship evaluation and graduation evaluation.

**Communication & Finance**

- News and announcements (images, videos, and files).
- Tuition fees and outstanding balances.
- Monitor consultation requests across the system.

> **Security Note:** Administrator credentials are intentionally excluded from this README. Administrative access is restricted to authorized personnel.

---

## Permission Summary

| Feature | Student | Lecturer | Administrator |
|---------|:-------:|:--------:|:-------------:|
| View own profile / grades / schedule | Yes | Yes (assigned classes) | All users |
| Course registration | Yes | — | Configure periods |
| Enter grades | — | Yes (during open period) | Edit saved grades |
| Manage departments, majors, classes, courses | — | — | Yes |
| Tuition, scholarships, graduation | View own information | — | Manage / evaluate |
| Academic consultation | Send | Respond | Monitor |
| News | View | View | Create / edit / delete |

---

## Running Locally

Requirements:

- **Node.js**
- **MySQL 8**


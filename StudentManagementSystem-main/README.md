# Student Management System

A modular Python command-line application designed to handle academic administrative tasks, including student record management, course enrollments, grading, and attendance tracking. Built using Object-Oriented Programming (OOP) principles with persistent text-file storage.

---

## Key Features

- **Student Directory:** Add and manage student records (ID, name, section).
- **Course Administration:** Register subjects with course codes, titles, and credit hours.
- **Enrollment Workflow:** Enroll students into specific subjects.
- **Grade Management:** Assign and update letter grades per student and subject.
- **Subject-Wise Attendance:** Mark daily attendance (`P` for Present, `A` for Absent) with automated percentage calculations.
- **Academic Reports:** View complete academic summaries per student or inspect global enrollment lists.
- **Persistent Storage:** Saves all updates locally in the `data/` folder so records persist across sessions.

---

## System Architecture

The project follows an Object-Oriented design separated into four primary classes:

- **`Student`**: Stores profile information (ID, name, section).
- **`Subject`**: Encapsulates course metadata (code, name, credit hours).
- **`Record`**: Handles performance tracking, storing grades and attendance metrics.
- **`SystemManager`**: Serves as the central controller handling user inputs, data persistence, and calculations.

---

## Data Storage Format

All program data is stored in the `data/` directory using plain text files:

- `data/students.txt` — Stores student ID, full name, and section.
- `data/subjects.txt` — Stores subject code, title, and credit hours.
- `data/enrollments.txt` — Tracks student-to-subject enrollments.
- `data/records.txt` — Stores grades and attendance counts per student per course.

---

## How to Run

### Requirements
- Python 3.8 or higher installed on your machine.

### Instructions

1. Clone the repository:
   ```bash
   git clone [https://github.com/emanchahal44-max/StudentManagementSystem.git](https://github.com/emanchahal44-max/StudentManagementSystem.git)



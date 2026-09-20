# Student Management System — Python Project

A modular, console-based academic management application developed in Python. Built using Object-Oriented Programming (OOP) principles, the system streamlines student record maintenance, course enrollments, grade tracking, and subject-wise attendance management with automated percentage calculations and persistent text-file storage.

---

## Key Features

- **Student Directory:** Add and manage student profile records (Student ID, Full Name, Section).
- **Course Catalog:** Register subjects with course codes, titles, and credit hour values.
- **Enrollment Workflow:** Map and enroll individual students into multiple academic subjects.
- **Grade Records:** Assign, track, and update performance grades per student per course.
- **Subject-Wise Attendance Tracker:** Take daily roll calls (`P` for Present, `A` for Absent) with automated attendance percentage computation.
- **Academic Reporting:** Generate comprehensive individual student progress reports and inspect system-wide directories.
- **Persistent Text-File Storage:** Automatically reads from and writes updates to plain text files located in the `data/` directory.

---

## 🏗️ Architecture & OOP Design

The codebase is built on an Object-Oriented structure separated into four dedicated classes:

| Class | Primary Responsibility |
| :--- | :--- |
| `Student` | Encapsulates student profile data (ID, name, section). |
| `Subject` | Represents academic course parameters (code, name, credit hours). |
| `Record` | Tracks academic grades and subject-level attendance counters. |
| `SystemManager` | Orchestrates operations: data validation, enrollments, computations, and file I/O. |

---

## Directory & Storage Structure

```text
student_management_system/
│
├── main.py                     # Application entry point and CLI menu
├── student.py                  # Student class definition
├── subject.py                  # Subject class definition
├── record.py                   # Record class definition
├── system_manager.py           # Controller managing operations and storage
│
└── data/                       # Persistent text-file database
    ├── students.txt            # Student identity records
    ├── subjects.txt            # Course catalog details
    ├── enrollments.txt         # Student-to-subject mapping
    └── records.txt             # Academic grades and attendance logs
```

---

## How to Run

1. Open your terminal in the project directory:
   ```bash
   cd student_management_system
   ```
2. Run the main script:
   ```bash
   python main.py
   ```
3. Use the numbered menu options (`1` through `9`) to perform administrative tasks.

---

## Terminal Session & Example Output

### 1. Main Navigation Menu
```text
============================================================
                 STUDENT MANAGEMENT SYSTEM
============================================================
 [1] Add Student
 [2] Add Subject
 [3] Enroll Student
 [4] Add Grade
 [5] Mark Attendance (Subject-wise)
 [6] View Student Report
 [7] View All Students
 [8] View Enrollments
 [9] Exit
============================================================
Enter your choice: 1

Enter Student ID: S101
Enter Student Name: Eman Fatima
Enter Section: ME-01
[✓] Student 'S101 - Eman Fatima' successfully registered!
```

### 2. Marking Subject Attendance
```text
Enter your choice: 5
Enter Subject Code: ME201

--- Marking Attendance for ME201 (Thermodynamics) ---
[1/3] Eman Fatima (S101) - [P/A]: P
[2/3] Hamza Ali (S102)   - [P/A]: P
[3/3] Zainab Noor (S103) - [P/A]: A

[✓] Attendance updated and stored successfully!
```

### 3. Student Academic Report
```text
Enter your choice: 6
Enter Student ID: S101

============================================================
                   STUDENT ACADEMIC REPORT
============================================================
Student ID : S101
Full Name  : Eman Fatima
Section    : ME-01
------------------------------------------------------------
Course Code | Subject Title             | Grade | Attendance
------------------------------------------------------------
CS101       | Programming Fundamentals  | A     | 95.00% (19/20)
ME201       | Thermodynamics            | A-    | 90.00% (18/20)
MATH102     | Linear Algebra            | B+    | 85.00% (17/20)
============================================================
Overall Attendance Average: 90.00%
============================================================
```

---

## Database File Examples

Data inside the `data/` folder is stored in structured, delimited text lines.

### Sample `data/students.txt`
```text
S101,Eman Fatima,ME-01
S102,Hamza Ali,ME-01
S103,Zainab Noor,ME-02
```

### Sample `data/records.txt`
```text
S101,CS101,A,19,20
S101,ME201,A-,18,20
S101,MATH102,B+,17,20
```

1. Clone the repository:
   ```bash
   git clone [https://github.com/emanchahal44-max/StudentManagementSystem.git](https://github.com/emanchahal44-max/StudentManagementSystem.git)



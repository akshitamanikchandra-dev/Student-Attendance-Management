# Student Attendance System

## Description

The **Student Attendance System** is a console-based C++ application that helps track and manage student attendance across multiple subjects. It uses **Object-Oriented Programming (OOP)** concepts such as inheritance, polymorphism, and encapsulation to model real-world entities like students, subjects, and attendance records.

Attendance data is stored persistently in plain text files (`students.txt`, `subjects.txt`, `attendance.txt`), so all records are saved between sessions — no database required.

### Key concepts used

- **Inheritance** — `Student` derives from the base class `Person`, sharing common attributes like ID and name while overriding the `display()` method (polymorphism).
- **Encapsulation** — each class (`Subject`, `AttendanceRecord`, `AttendanceSystem`) keeps its data private and exposes only what is needed through public methods.
- **File I/O** — records are loaded from and written to `.txt` files on every operation, ensuring data persists across runs.
- **STL containers** — `vector` is used to hold students, subjects, and records; `map` is used for computing attendance statistics efficiently.

### Features

- Add students and subjects in batch
- Mark daily attendance (Present / Absent) for each student per subject
- View all attendance records in a tabular format
- Update a specific attendance entry by student ID, subject, and date
- View subject-wise attendance percentage for each student
- View student-wise overall attendance average across all subjects

---

## Build and run

**Requirements:** any C++11-compatible compiler (g++, clang++, etc.)

```bash
# Compile
g++ -std=c++11 -o attendance_system attendance_system.cpp

# Run
./attendance_system
```

**Data files** (`students.txt`, `subjects.txt`, `attendance.txt`) are created automatically in the same directory when you first add data. You can also create them manually — format shown below.

---

## File formats

**students.txt**
```
S001,Alice Johnson
S002,Bob Smith
```

**subjects.txt**
```
Mathematics
Physics
Computer Science
```

**attendance.txt**
```
S001,Mathematics,15-03-2025,Present
S002,Mathematics,15-03-2025,Absent
```

---

## Example session

```
===== STUDENT ATTENDANCE SYSTEM =====
1. Add Students (Batch)
2. Add Subjects
3. Mark Attendance
4. View Attendance Records
5. Update Attendance
6. View Subject-wise Average
7. View Student-wise Average
8. Exit
Enter choice: 7

===== Student-wise Attendance Average =====
S001 (Alice Johnson) -> 85.0% Present (17/20)
S002 (Bob Smith)     -> 70.0% Present (14/20)
```

---

## Project structure

```
.
├── attendance_system.cpp   # Full source — single file, no dependencies
├── students.txt            # Auto-generated: student ID and name records
├── subjects.txt            # Auto-generated: subject names
└── attendance.txt          # Auto-generated: daily attendance log
```

---

## OOP class diagram (overview)

```
Person (base)
└── Student (derived) — overrides display()

Subject           — stores subject name
AttendanceRecord  — stores one attendance entry (student, subject, date, status)
AttendanceSystem  — manages all data; handles file I/O and menu operations
```

---

## License

MIT — feel free to use and adapt.

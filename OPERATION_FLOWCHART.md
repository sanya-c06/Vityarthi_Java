# CCRM Operation Flowchart

## 🚀 Application Startup Flow

```
START
  ↓
Open Command Prompt
  ↓
Navigate to: cd C:\Users\OneDrive\Desktop\vityarthi_project\src
  ↓
Run: java -cp . edu.ccrm.cli.Main
  ↓
Application Starts → Main Menu Appears
  ↓
Choose Operation (1-8)
```

## 📋 Main Menu Decision Tree

```
MAIN MENU
├── 1. Manage Students
│   ├── 1. Add Student
│   ├── 2. List All Students
│   ├── 3. Update Student
│   ├── 4. View Student Profile
│   ├── 5. View Student Transcript
│   ├── 6. Deactivate Student
│   └── 7. Back to Main Menu
│
├── 2. Manage Courses
│   ├── 1. Add Course
│   ├── 2. List All Courses
│   ├── 3. Update Course
│   ├── 4. Search Courses
│   ├── 5. Assign Instructor
│   ├── 6. Deactivate Course
│   └── 7. Back to Main Menu
│
├── 3. Manage Enrollments
│   ├── 1. Enroll Student
│   ├── 2. Unenroll Student
│   ├── 3. View Enrollments
│   └── 4. Back to Main Menu
│
├── 4. Manage Grades
│   ├── 1. Record Grade
│   ├── 2. View Grades
│   ├── 3. Calculate GPA
│   └── 4. Back to Main Menu
│
├── 5. Import/Export Data
│   ├── 1. Import Students from CSV
│   ├── 2. Import Courses from CSV
│   ├── 3. Export Students to CSV
│   ├── 4. Export Courses to CSV
│   ├── 5. Export All Data
│   └── 6. Back to Main Menu
│
├── 6. Backup Operations
│   ├── 1. Create Backup
│   ├── 2. Show Backup Size (Recursive)
│   ├── 3. List Backup Files
│   └── 4. Back to Main Menu
│
├── 7. Generate Reports
│   ├── 1. Top Students by GPA
│   ├── 2. GPA Distribution
│   ├── 3. Course Statistics
│   ├── 4. Enrollment Summary
│   └── 5. Back to Main Menu
│
└── 8. Exit Application
```

## 🎯 Common Operation Flows

### Student Management Flow
```
1 → 1 (Add Student)
  ↓
Enter: ID, RegNo, Name, Email
  ↓
Student Added Successfully
  ↓
Back to Student Menu (7)
```

### Enrollment Flow
```
3 → 1 (Enroll Student)
  ↓
Enter: StudentID, CourseCode, Semester, Year
  ↓
System Validates:
├── Student exists and active
├── Course exists and active
├── Not already enrolled
├── Credit limit not exceeded
  ↓
Enrollment Successful
  ↓
Back to Enrollment Menu (4)
```

### Grade Recording Flow
```
4 → 1 (Record Grade)
  ↓
Enter: EnrollmentID, Percentage
  ↓
System Converts: Percentage → Letter Grade
  ↓
Grade Recorded Successfully
  ↓
Back to Grade Menu (4)
```

### Transcript Generation Flow
```
1 → 5 (View Student Transcript)
  ↓
Enter: StudentID
  ↓
System Gathers:
├── Student Information
├── All Enrollments
├── Grades and Credits
├── GPA Calculation
  ↓
Formatted Transcript Displayed
  ↓
Back to Student Menu (7)
```

## 📊 Data Flow Examples

### Adding a New Student
```
Input: STU009, REG009, Alice Johnson, alice@university.edu
  ↓
Validation:
├── ID format: STU###
├── RegNo format: REG###
├── Name not empty
├── Email contains @
  ↓
Create Student Object
  ↓
Store in StudentService
  ↓
Success Message
```

### Enrolling Student in Course
```
Input: STU001, CS101, Fall, 2024
  ↓
Validations:
├── Student STU001 exists
├── Course CS101 exists
├── Both are active
├── Not already enrolled
├── Credit limit check
  ↓
Create Enrollment Object
  ↓
Update Student's enrolled courses
  ↓
Success Message with Enrollment ID
```

### Recording Grade
```
Input: ENR001, 85.5
  ↓
Validations:
├── Enrollment exists
├── Enrollment is active
├── Percentage 0-100
  ↓
Convert: 85.5% → Grade A (9.0 points)
  ↓
Update Enrollment with Grade
  ↓
Success Message
```

## 🔄 Navigation Patterns

### Standard Navigation
```
Main Menu → Sub-Menu → Operation → Result → Back to Sub-Menu → Back to Main Menu
```

### Quick Operations
```
Main Menu → Operation → Result → Back to Main Menu
```

### Multi-Step Operations
```
Main Menu → Sub-Menu → Step 1 → Step 2 → Step 3 → Result → Back to Sub-Menu
```

## ⚡ Quick Access Patterns

### View Information
- **Students**: 1 → 2 (List) or 1 → 4 (Profile)
- **Courses**: 2 → 2 (List) or 2 → 4 (Search)
- **Enrollments**: 3 → 3 (View)
- **Grades**: 4 → 2 (View)

### Add Information
- **Students**: 1 → 1 (Add)
- **Courses**: 2 → 1 (Add)
- **Enrollments**: 3 → 1 (Enroll)
- **Grades**: 4 → 1 (Record)

### Generate Reports
- **Academic**: 7 → 1 (Top Students)
- **Statistics**: 7 → 2 (GPA Distribution)
- **Course Data**: 7 → 3 (Course Statistics)
- **Enrollment**: 7 → 4 (Enrollment Summary)

## 🛡️ Error Handling Flow

### Input Validation
```
User Input
  ↓
Validate Format
  ↓
If Invalid → Error Message → Retry Input
  ↓
If Valid → Process Request
```

### Business Rule Validation
```
Request
  ↓
Check Business Rules
  ↓
If Violated → Error Message with Reason
  ↓
If Valid → Execute Operation
```

### System Error Handling
```
Operation
  ↓
Try/Catch Block
  ↓
If Exception → Error Message → Return to Menu
  ↓
If Success → Success Message → Continue
```

## 📱 Mobile-Friendly Quick Reference

### Essential Commands
```
Start: java -cp . edu.ccrm.cli.Main
Students: 1 → 2 (List) or 1 → 4 (Profile)
Courses: 2 → 2 (List) or 2 → 4 (Search)
Enroll: 3 → 1 (Enroll Student)
Grade: 4 → 1 (Record Grade)
Backup: 6 → 1 (Create Backup)
Report: 7 → 1 (Top Students)
Exit: 8
```

### Sample Data
```
Students: STU001, STU002, STU003
Courses: CS101, CS201, MATH101
Semesters: 1=Spring, 2=Summer, 3=Fall
```

This flowchart provides a visual guide to understanding how to navigate and use the CCRM application efficiently!

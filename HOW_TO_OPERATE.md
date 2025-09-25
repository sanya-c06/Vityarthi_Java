# How to Operate the CCRM Application

## 🚀 Quick Start Guide

### 1. Prerequisites
- Java 11 or higher installed
- Windows Command Prompt or PowerShell
- Eclipse IDE (optional, for development)

### 2. Running the Application

#### Method 1: Command Line (Recommended)
```cmd
# Navigate to project directory
cd C:\Users\megha\OneDrive\Desktop\vityarthi_project

# Compile the application
cd src
javac -cp . edu/ccrm/cli/Main.java

# Run the application
java -cp . edu.ccrm.cli.Main
```

#### Method 2: Eclipse IDE
1. Import the project into Eclipse
2. Right-click `Main.java` in `edu.ccrm.cli` package
3. Select "Run As" → "Java Application"

---

## 📋 Main Menu Navigation

When you start the application, you'll see:

```
=== Campus Course & Records Manager (CCRM) ===

Configuration loaded from: data

=== MAIN MENU ===
1. Manage Students
2. Manage Courses
3. Manage Enrollments
4. Manage Grades
5. Import/Export Data
6. Backup Operations
7. Generate Reports
8. Exit
Enter your choice (1-8):
```

**Simply type the number (1-8) and press Enter to select an option.**

---

## 🎯 Step-by-Step Operations Guide

### 📚 1. STUDENT MANAGEMENT

#### 1.1 Add a New Student
```
Main Menu → 1 (Manage Students) → 1 (Add Student)
```
**Enter the following information:**
- Student ID: `STU009` (format: STU###)
- Registration Number: `REG009` (format: REG###)
- Full Name: `Alice Johnson`
- Email: `alice.johnson@university.edu`

#### 1.2 List All Students
```
Main Menu → 1 (Manage Students) → 2 (List All Students)
```
**Shows:** All students with ID, name, email, and status

#### 1.3 Update Student Information
```
Main Menu → 1 (Manage Students) → 3 (Update Student)
```
**Enter student ID, then choose what to update:**
- Full Name
- Email
- Registration Number
- Status

#### 1.4 View Student Profile
```
Main Menu → 1 (Manage Students) → 4 (View Student Profile)
```
**Enter student ID (e.g., STU001)**
**Shows:** Detailed student information including enrollment count

#### 1.5 View Student Transcript
```
Main Menu → 1 (Manage Students) → 5 (View Student Transcript)
```
**Enter student ID (e.g., STU001)**
**Shows:** Complete academic record with grades and GPA

#### 1.6 Deactivate Student
```
Main Menu → 1 (Manage Students) → 6 (Deactivate Student)
```
**Enter student ID to deactivate**

---

### 📖 2. COURSE MANAGEMENT

#### 2.1 Add a New Course
```
Main Menu → 2 (Manage Courses) → 1 (Add Course)
```
**Enter the following information:**
- Course Code: `CS401` (format: XXXX###)
- Course Title: `Software Engineering`
- Credits: `3` (1-6)
- Instructor ID: `INST011` (optional)
- Semester: `3` (1=Spring, 2=Summer, 3=Fall)
- Department: `Computer Science`

#### 2.2 List All Courses
```
Main Menu → 2 (Manage Courses) → 2 (List All Courses)
```
**Shows:** All courses with code, title, credits, instructor, semester, department

#### 2.3 Update Course Information
```
Main Menu → 2 (Manage Courses) → 3 (Update Course)
```
**Enter course code, then choose what to update:**
- Title
- Credits
- Instructor
- Semester
- Department
- Active Status

#### 2.4 Search Courses
```
Main Menu → 2 (Manage Courses) → 4 (Search Courses)
```
**Choose search method:**
- By text (searches code, title, department)
- By instructor
- By department
- By semester
- By credits

#### 2.5 Assign Instructor to Course
```
Main Menu → 2 (Manage Courses) → 5 (Assign Instructor)
```
**Enter course code and instructor ID**

#### 2.6 Deactivate Course
```
Main Menu → 2 (Manage Courses) → 6 (Deactivate Course)
```
**Enter course code to deactivate**

---

### 🎓 3. ENROLLMENT MANAGEMENT

#### 3.1 Enroll Student in Course
```
Main Menu → 3 (Manage Enrollments) → 1 (Enroll Student)
```
**Enter the following:**
- Student ID: `STU001`
- Course Code: `CS101`
- Semester: `3` (Fall)
- Year: `2024`

**Business Rules Applied:**
- Maximum 18 credits per semester
- No duplicate enrollments
- Student and course must be active

#### 3.2 Unenroll Student from Course
```
Main Menu → 3 (Manage Enrollments) → 2 (Unenroll Student)
```
**Enter enrollment ID to unenroll**

#### 3.3 View Enrollments
```
Main Menu → 3 (Manage Enrollments) → 3 (View Enrollments)
```
**Choose viewing option:**
- All enrollments
- By student
- By course
- By semester

---

### 📊 4. GRADE MANAGEMENT

#### 4.1 Record Grade
```
Main Menu → 4 (Manage Grades) → 1 (Record Grade)
```
**Enter the following:**
- Enrollment ID: `ENR001`
- Percentage: `85.5` (0-100)

**Grade automatically converted to letter grade (A, B, C, etc.)**

#### 4.2 View Grades
```
Main Menu → 4 (Manage Grades) → 2 (View Grades)
```
**Choose viewing option:**
- By student
- By course
- All grades

#### 4.3 Calculate GPA
```
Main Menu → 4 (Manage Grades) → 3 (Calculate GPA)
```
**Enter student ID to calculate GPA**

---

### 📁 5. IMPORT/EXPORT DATA

#### 5.1 Import Students from CSV
```
Main Menu → 5 (Import/Export Data) → 1 (Import Students from CSV)
```
**Enter file path or press Enter for default: `data/students.csv`**

#### 5.2 Import Courses from CSV
```
Main Menu → 5 (Import/Export Data) → 2 (Import Courses from CSV)
```
**Enter file path or press Enter for default: `data/courses.csv`**

#### 5.3 Export Students to CSV
```
Main Menu → 5 (Import/Export Data) → 3 (Export Students to CSV)
```
**Enter output path or press Enter for default**

#### 5.4 Export Courses to CSV
```
Main Menu → 5 (Import/Export Data) → 4 (Export Courses to CSV)
```
**Enter output path or press Enter for default**

#### 5.5 Export All Data
```
Main Menu → 5 (Import/Export Data) → 5 (Export All Data)
```
**Creates timestamped export files**

---

### 💾 6. BACKUP OPERATIONS

#### 6.1 Create Backup
```
Main Menu → 6 (Backup Operations) → 1 (Create Backup)
```
**Creates timestamped backup folder with all current data**

#### 6.2 Show Backup Size (Recursive)
```
Main Menu → 6 (Backup Operations) → 2 (Show Backup Size)
```
**Shows total backup size and size by depth (demonstrates recursion)**

#### 6.3 List Backup Files
```
Main Menu → 6 (Backup Operations) → 3 (List Backup Files)
```
**Shows all backup folders and files**

---

### 📈 7. GENERATE REPORTS

#### 7.1 Top Students by GPA
```
Main Menu → 7 (Generate Reports) → 1 (Top Students by GPA)
```
**Shows ranked list of students by academic performance**

#### 7.2 GPA Distribution
```
Main Menu → 7 (Generate Reports) → 2 (GPA Distribution)
```
**Shows statistical breakdown of GPA ranges**

#### 7.3 Course Statistics
```
Main Menu → 7 (Generate Reports) → 3 (Course Statistics)
```
**Shows courses by department and semester**

#### 7.4 Enrollment Summary
```
Main Menu → 7 (Generate Reports) → 4 (Enrollment Summary)
```
**Shows enrollment statistics and popular courses**

---

## 🎯 Sample Workflow Demonstration

### Complete Demo Scenario (5 minutes)

1. **Start Application**
   ```cmd
   cd src
   java -cp . edu.ccrm.cli.Main
   ```

2. **View Existing Students**
   ```
   Main Menu → 1 → 2 (List All Students)
   ```

3. **View Student Profile**
   ```
   Main Menu → 1 → 4 (View Student Profile)
   Enter: STU001
   ```

4. **View Courses**
   ```
   Main Menu → 2 → 2 (List All Courses)
   ```

5. **Search for Programming Course**
   ```
   Main Menu → 2 → 4 (Search Courses) → 1 (Search by text)
   Enter: programming
   ```

6. **Enroll Student in Course**
   ```
   Main Menu → 3 → 1 (Enroll Student)
   Enter: STU001, CS101, 3 (Fall), 2024
   ```

7. **Record Grade**
   ```
   Main Menu → 4 → 1 (Record Grade)
   Enter: ENR001, 85.5
   ```

8. **View Transcript**
   ```
   Main Menu → 1 → 5 (View Student Transcript)
   Enter: STU001
   ```

9. **Create Backup**
   ```
   Main Menu → 6 → 1 (Create Backup)
   ```

10. **Generate Report**
    ```
    Main Menu → 7 → 1 (Top Students by GPA)
    ```

11. **Exit Application**
    ```
    Main Menu → 8 (Exit)
    ```

---

## ⚠️ Important Notes

### Data Format Requirements
- **Student IDs**: Must follow format `STU###` (e.g., STU001, STU002)
- **Course Codes**: Must follow format `XXXX###` (e.g., CS101, MATH101)
- **Registration Numbers**: Must follow format `REG###` (e.g., REG001)
- **Email**: Must contain @ symbol
- **Credits**: Must be between 1 and 6
- **Year**: Must be between 2020 and 2030

### Business Rules
- **Credit Limit**: Maximum 18 credits per semester per student
- **Duplicate Prevention**: Cannot enroll in same course twice in same semester
- **Active Status**: Only active students and courses can be used for enrollment
- **Grade Range**: Percentages must be between 0 and 100

### Navigation Tips
- **Always use numbers** to select menu options
- **Press Enter** after typing your choice
- **Use Ctrl+C** to exit if application gets stuck
- **Navigate back** using menu option 7 (Back to Main Menu) in sub-menus

---

## 🔧 Troubleshooting

### Common Issues

#### Application Won't Start
```cmd
# Check Java installation
java -version

# Check compilation
javac -cp . edu/ccrm/cli/Main.java

# Run with error checking
java -cp . edu.ccrm.cli.Main
```

#### Menu Navigation Issues
- Use only numbers (1-8) for main menu
- Use only numbers for sub-menu selections
- Press Enter after each selection

#### Data Entry Errors
- Follow exact format requirements
- Check spelling of IDs and codes
- Ensure valid email format
- Verify credit limits and year ranges

#### File Operations Issues
- Ensure `data/` folder exists
- Check file permissions
- Verify CSV file format

---

## 📱 Quick Reference Commands

### Essential Commands
```cmd
# Start application
java -cp . edu.ccrm.cli.Main

# View students
1 → 2

# View courses  
2 → 2

# Enroll student
3 → 1

# Record grade
4 → 1

# Create backup
6 → 1

# Generate report
7 → 1

# Exit
8
```

### Sample Data IDs
- **Students**: STU001, STU002, STU003
- **Courses**: CS101, CS201, MATH101
- **Enrollments**: ENR001, ENR002, ENR003

---

## 🎉 You're Ready to Use CCRM!

The application is designed to be intuitive and user-friendly. Follow the menu prompts, enter data in the requested format, and explore all the features. The system includes comprehensive error handling and validation to guide you through any issues.

**Happy managing your campus courses and records!** 📚✨

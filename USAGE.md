# CCRM Usage Guide

This guide provides detailed instructions on how to use the Campus Course & Records Manager (CCRM) application.

## Quick Start

1. **Run the Application**
   ```cmd
   java -cp src edu.ccrm.cli.Main
   ```

2. **Navigate the Menu**
   - Use numbers 1-8 to select menu options
   - Press Enter to confirm selections
   - Follow prompts for data entry

## Main Menu Options

### 1. Manage Students
- **1.1 Add Student**: Create new student records
- **1.2 List All Students**: View all student information
- **1.3 Update Student**: Modify existing student data
- **1.4 View Student Profile**: Detailed student information
- **1.5 View Student Transcript**: Academic record with grades
- **1.6 Deactivate Student**: Mark student as inactive

### 2. Manage Courses
- **2.1 Add Course**: Create new course records
- **2.2 List All Courses**: View all course information
- **2.3 Update Course**: Modify existing course data
- **2.4 Search Courses**: Find courses by various criteria
- **2.5 Assign Instructor**: Assign instructor to course
- **2.6 Deactivate Course**: Mark course as inactive

### 3. Manage Enrollments
- **3.1 Enroll Student**: Enroll student in course
- **3.2 Unenroll Student**: Remove student from course
- **3.3 View Enrollments**: Display enrollment information

### 4. Manage Grades
- **4.1 Record Grade**: Enter student grades
- **4.2 View Grades**: Display grade information
- **4.3 Calculate GPA**: Compute student GPA

### 5. Import/Export Data
- **5.1 Import Students from CSV**: Load students from file
- **5.2 Import Courses from CSV**: Load courses from file
- **5.3 Export Students to CSV**: Save students to file
- **5.4 Export Courses to CSV**: Save courses to file
- **5.5 Export All Data**: Comprehensive data export

### 6. Backup Operations
- **6.1 Create Backup**: Generate timestamped backup
- **6.2 Show Backup Size**: Calculate backup directory size
- **6.3 List Backup Files**: Display backup information

### 7. Generate Reports
- **7.1 Top Students by GPA**: Rank students by academic performance
- **7.2 GPA Distribution**: Statistical analysis of grades
- **7.3 Course Statistics**: Course enrollment analytics
- **7.4 Enrollment Summary**: Enrollment overview

### 8. Exit
- Terminate the application

## Sample Data Entry

### Adding a Student
```
Enter student ID: STU009
Enter registration number: REG009
Enter full name: Alice Johnson
Enter email: alice.johnson@university.edu
```

### Adding a Course
```
Enter course code: CS401
Enter course title: Software Engineering
Enter credits (1-6): 3
Enter instructor ID (optional): INST011
Select semester:
1. Spring
2. Summer
3. Fall
Enter choice (1-3): 3
Enter department: Computer Science
```

### Enrolling a Student
```
Enter student ID: STU001
Enter course code: CS101
Select semester:
1. Spring
2. Summer
3. Fall
Enter choice (1-3): 3
Enter year: 2024
```

### Recording a Grade
```
Enter enrollment ID: ENR001
Enter percentage (0-100): 85.5
```

## CSV File Formats

### Students CSV Format
```csv
ID,Registration Number,Full Name,Email
STU001,REG001,John Doe,john.doe@university.edu
STU002,REG002,Jane Smith,jane.smith@university.edu
```

### Courses CSV Format
```csv
Code,Title,Credits,Instructor ID,Semester,Department
CS101,Introduction to Programming,3,INST001,FALL,Computer Science
CS201,Data Structures and Algorithms,4,INST002,SPRING,Computer Science
```

## File Operations

### Importing Data
1. Prepare CSV files in the correct format
2. Place files in the `data/` directory
3. Use menu option 5 to import
4. Specify file path or use defaults

### Exporting Data
1. Choose export option from menu
2. Specify output file path
3. Files are created with timestamp
4. Check `data/` directory for exports

### Backup Operations
1. Create backup using menu option 6.1
2. Backup includes all current data
3. Timestamped folders in `backups/` directory
4. Use recursive size calculation to monitor storage

## Business Rules

### Enrollment Rules
- Maximum 18 credits per semester
- Students must be active to enroll
- Courses must be active for enrollment
- No duplicate enrollments for same semester/year

### Grade Rules
- Percentage must be 0-100
- Grades automatically converted to letter grades
- GPA calculated based on credit hours

### Data Validation
- Student IDs must follow STU### format
- Course codes must follow XXXX### format
- Email addresses must be valid format
- Registration numbers must follow REG### format

## Error Handling

### Common Errors
- **Invalid ID Format**: Use correct format (STU001, CS101)
- **Duplicate Records**: Check if student/course already exists
- **Credit Limit**: Cannot exceed 18 credits per semester
- **File Not Found**: Ensure CSV files exist in correct location

### Error Messages
- Clear error descriptions provided
- Suggestions for correction included
- Graceful handling of invalid input

## Advanced Features

### Search and Filter
- Search courses by text, instructor, department
- Filter students by status, enrollment count
- Use Stream API for complex queries

### Reporting
- GPA distribution analysis
- Top student rankings
- Course popularity statistics
- Enrollment summaries

### Recursive Operations
- Directory size calculation
- File counting and traversal
- Backup size analysis by depth

## Tips for Best Results

1. **Use Sample Data**: Start with provided CSV files
2. **Follow Formats**: Use exact ID and code formats
3. **Regular Backups**: Create backups before major operations
4. **Validate Input**: Check data before entering
5. **Monitor Storage**: Use recursive size calculation

## Troubleshooting

### Application Won't Start
- Check Java installation: `java -version`
- Verify classpath: `-cp src`
- Ensure Main.java is in correct location

### Import Errors
- Check CSV file format
- Verify file path
- Ensure proper delimiters (commas)

### Backup Issues
- Check disk space
- Verify backup directory permissions
- Ensure data directory exists

## Sample Workflow

1. **Initial Setup**
   ```
   Run application → Import sample data → Verify data loaded
   ```

2. **Add New Student**
   ```
   Manage Students → Add Student → Enter details → Confirm
   ```

3. **Create Course**
   ```
   Manage Courses → Add Course → Enter details → Confirm
   ```

4. **Enroll Student**
   ```
   Manage Enrollments → Enroll Student → Select student/course → Confirm
   ```

5. **Record Grades**
   ```
   Manage Grades → Record Grade → Enter enrollment ID → Enter percentage
   ```

6. **Generate Report**
   ```
   Generate Reports → Top Students → View rankings
   ```

7. **Create Backup**
   ```
   Backup Operations → Create Backup → Verify backup created
   ```

This comprehensive guide should help you effectively use all features of the CCRM application.

# Vityarthi_Java
# Campus Course & Records Manager (CCRM)

A comprehensive Java SE console-based application for managing students, courses, enrollments, and academic records in an educational institution.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Evolution of Java](#evolution-of-java)
3. [Java Platform Comparison](#java-platform-comparison)
4. [Java Architecture](#java-architecture)
5. [Installation & Setup](#installation--setup)
6. [How to Run](#how-to-run)
7. [Project Structure](#project-structure)
8. [Features](#features)
9. [Technical Implementation](#technical-implementation)
10. [Syllabus Topic Mapping](#syllabus-topic-mapping)
11. [Usage Examples](#usage-examples)
12. [Screenshots](#screenshots)

## Project Overview

The Campus Course & Records Manager (CCRM) is a Java SE application that provides comprehensive management of academic records including:

- **Student Management**: Add, update, view, and deactivate student records
- **Course Management**: Create, modify, search, and assign instructors to courses
- **Enrollment Management**: Enroll/unenroll students with business rule validation
- **Grade Management**: Record grades, calculate GPA, and generate transcripts
- **File Operations**: Import/export data using CSV files with NIO.2
- **Backup Operations**: Create timestamped backups with recursive size calculation
- **Reporting**: Generate various reports using Stream API

## Evolution of Java

### Java Timeline
- **1995**: Java 1.0 released by Sun Microsystems
- **1996**: Java 1.1 with inner classes, reflection, and JDBC
- **1998**: Java 2 (JDK 1.2) with Collections Framework and Swing
- **2000**: Java 1.3 with HotSpot JVM and JNDI
- **2002**: Java 1.4 with assert keyword, regex, and NIO
- **2004**: Java 5 (JDK 1.5) with generics, enums, and autoboxing
- **2006**: Java 6 with scripting support and improved performance
- **2011**: Java 7 with try-with-resources, switch on strings, and NIO.2
- **2014**: Java 8 with lambdas, streams, and date/time API
- **2017**: Java 9 with modules (Project Jigsaw)
- **2018**: Java 10 with local variable type inference (var)
- **2018**: Java 11 LTS with HTTP client and single-file execution
- **2021**: Java 17 LTS with sealed classes and pattern matching
- **2023**: Java 21 LTS with virtual threads and string templates

## Java Platform Comparison

| Platform | Full Name | Purpose | Target Environment |
|----------|-----------|---------|-------------------|
| **Java SE** | Java Standard Edition | Desktop and server applications | General-purpose computing |
| **Java EE** | Java Enterprise Edition | Enterprise applications | Large-scale distributed systems |
| **Java ME** | Java Micro Edition | Mobile and embedded devices | Resource-constrained environments |

### Java SE vs Java EE vs Java ME

**Java SE (Standard Edition)**
- Core Java platform for desktop and server applications
- Includes basic APIs for I/O, networking, GUI, database connectivity
- Used for standalone applications and applets
- Foundation for other Java platforms

**Java EE (Enterprise Edition)**
- Built on top of Java SE
- Includes APIs for web services, messaging, persistence
- Used for enterprise applications, web applications
- Includes technologies like Servlets, JSP, EJB, JPA

**Java ME (Micro Edition)**
- Subset of Java SE optimized for mobile devices
- Reduced footprint for memory-constrained environments
- Used for mobile applications and embedded systems
- Includes CLDC and MIDP profiles

## Java Architecture

### JDK, JRE, and JVM

**JDK (Java Development Kit)**
- Complete development environment for Java applications
- Includes JRE + development tools (compiler, debugger, etc.)
- Contains source code and documentation
- Required for developing Java applications

**JRE (Java Runtime Environment)**
- Runtime environment for executing Java applications
- Includes JVM + Java class libraries + other supporting files
- Required for running Java applications
- Smaller than JDK (no development tools)

**JVM (Java Virtual Machine)**
- Virtual machine that executes Java bytecode
- Provides platform independence (Write Once, Run Anywhere)
- Manages memory, garbage collection, and security
- Converts bytecode to machine-specific instructions

### How They Interact
```
Java Source Code (.java) 
    ↓ (javac compiler)
Java Bytecode (.class)
    ↓ (JVM)
Machine Code (Platform Specific)
```

The **JDK** contains the **JRE**, which contains the **JVM**. The JVM runs on top of the operating system and provides a consistent runtime environment for Java applications.

## Installation & Setup

### Windows Installation Steps

1. **Download JDK**
   - Visit [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or [OpenJDK](https://openjdk.org/)
   - Download JDK 11 or higher for Windows

2. **Install JDK**
   - Run the installer as administrator
   - Follow the installation wizard
   - Note the installation directory (default: `C:\Program Files\Java\jdk-<version>`)

3. **Set Environment Variables**
   - Open System Properties → Advanced → Environment Variables
   - Create `JAVA_HOME` variable pointing to JDK installation directory
   - Add `%JAVA_HOME%\bin` to `PATH` variable

4. **Verify Installation**
   ```cmd
   java -version
   javac -version
   ```

### Eclipse IDE Setup

1. **Download Eclipse**
   - Visit [Eclipse Downloads](https://www.eclipse.org/downloads/)
   - Download Eclipse IDE for Java Developers

2. **Create New Project**
   - File → New → Java Project
   - Enter project name: "CCRM"
   - Select Java version (11 or higher)

3. **Configure Project Structure**
   - Right-click project → Properties → Java Build Path
   - Add source folders: `src`
   - Configure output folder: `bin`

4. **Run Configuration**
   - Right-click `Main.java` → Run As → Java Application
   - Or use Run → Run Configurations

## How to Run

### Prerequisites
- JDK 11 or higher
- Eclipse IDE (recommended) or any Java IDE

### Running the Application

1. **Clone or Download the Project**
   ```bash
   git clone <repository-url>
   cd vityarthi_project
   ```

2. **Compile the Project**
   ```cmd
   javac -cp src src/edu/ccrm/cli/Main.java
   ```

3. **Run the Application**
   ```cmd
   java -cp src edu.ccrm.cli.Main
   ```

4. **Enable Assertions (Optional)**
   ```cmd
   java -ea -cp src edu.ccrm.cli.Main
   ```

### Sample Commands
- Navigate through the menu using numbers 1-8
- Follow prompts to enter data
- Use sample CSV files in `data/` folder for import testing

## Project Structure

```
CCRM/
├── src/
│   └── edu/
│       └── ccrm/
│           ├── cli/           # Console interface and main class
│           ├── domain/        # Business entities and enums
│           ├── service/       # Business logic and services
│           ├── io/            # File I/O operations using NIO.2
│           ├── util/          # Utility classes and recursion
│           └── config/        # Configuration and singleton
├── data/                      # Sample data files
├── backups/                   # Backup directory (auto-created)
└── README.md                  # This file
```

## Features

### Core Functionality
- **Student Management**: CRUD operations for student records
- **Course Management**: Course creation, modification, and search
- **Enrollment System**: Student-course enrollment with validation
- **Grade Management**: Grade recording and GPA calculation
- **File Operations**: CSV import/export using NIO.2
- **Backup System**: Timestamped backups with recursive operations
- **Reporting**: Various reports using Stream API

### Business Rules
- Maximum 18 credits per semester per student
- Students can only enroll in active courses
- Only active students can enroll in courses
- Grade validation (0-100 percentage)
- Duplicate enrollment prevention

## Technical Implementation

### Object-Oriented Programming
- **Encapsulation**: Private fields with getters/setters
- **Inheritance**: Person → Student/Instructor hierarchy
- **Abstraction**: Abstract Person class with abstract methods
- **Polymorphism**: Interface implementations and method overriding

### Design Patterns
- **Singleton**: AppConfig for application configuration
- **Builder**: Course.Builder for complex object creation

### Advanced Java Features
- **NIO.2**: File operations, Path API, Files utility
- **Streams**: Data processing and filtering
- **Date/Time API**: LocalDateTime for timestamps
- **Lambda Expressions**: Functional programming
- **Enums**: Semester and Grade with constructors and methods
- **Generics**: Searchable<T> interface
- **Exception Handling**: Custom exceptions and try-catch-finally

### Recursion
- Directory size calculation
- File counting and traversal
- Mathematical algorithms (factorial, fibonacci)
- Tree structure printing

## Syllabus Topic Mapping

| Topic | Implementation | File/Class/Method |
|-------|---------------|-------------------|
| **Primitive Variables** | Data types in domain classes | `Student.java`, `Course.java` |
| **Objects** | All domain entities | `Person.java`, `Student.java`, `Course.java` |
| **Operators** | Arithmetic, relational, logical | `TranscriptService.calculateGPA()` |
| **Decision Structures** | if/else, switch statements | `Main.java` menu system |
| **Loops** | while, for, enhanced for | `StudentService.listAllStudents()` |
| **Arrays** | Array operations and utilities | `RecursionUtil.sumArray()` |
| **Strings** | String methods and manipulation | `ValidationUtil.isValidEmail()` |
| **Encapsulation** | Private fields, getters/setters | All domain classes |
| **Inheritance** | Person → Student/Instructor | `Person.java`, `Student.java` |
| **Abstraction** | Abstract Person class | `Person.java` |
| **Polymorphism** | Interface implementations | `Searchable<T>` interface |
| **Access Levels** | private, protected, public | All classes |
| **Constructors** | Multiple constructors, super() | `Student.java`, `Course.java` |
| **Immutability** | Final fields, defensive copying | `Student.getEnrolledCourses()` |
| **Nested Classes** | Static nested classes | `Student.StudentStatus` enum |
| **Interfaces** | Persistable, Searchable<T> | `Persistable.java`, `Searchable.java` |
| **Lambdas** | Functional interfaces | `CourseService.search()` |
| **Anonymous Classes** | Custom implementations | Various service classes |
| **Enums** | Semester, Grade with methods | `Semester.java`, `Grade.java` |
| **Upcast/Downcast** | instanceof checks | Service classes |
| **Method Overriding** | toString() overrides | All domain classes |
| **Design Patterns** | Singleton, Builder | `AppConfig.java`, `Course.Builder` |
| **Exceptions** | Custom exceptions | `EnrollmentService` exceptions |
| **Assertions** | Invariant checking | `RecursionUtil.factorialWithAssertion()` |
| **NIO.2** | File operations | `ImportExportService.java` |
| **Streams** | Data processing | `TranscriptService.generateGPADistribution()` |
| **Date/Time API** | LocalDateTime usage | All domain classes |
| **Recursion** | Various algorithms | `RecursionUtil.java` |

## Usage Examples

### Sample Data Files

**students.csv**
```csv
ID,Registration Number,Full Name,Email
STU001,REG001,John Doe,john.doe@university.edu
STU002,REG002,Jane Smith,jane.smith@university.edu
```

**courses.csv**
```csv
Code,Title,Credits,Instructor ID,Semester,Department
CS101,Introduction to Programming,3,INST001,FALL,Computer Science
CS201,Data Structures and Algorithms,4,INST002,SPRING,Computer Science
```

### Command Examples

1. **Add Student**
   - Choose menu option 1 → 1
   - Enter student details

2. **Import Data**
   - Choose menu option 5 → 1
   - Specify CSV file path

3. **Create Backup**
   - Choose menu option 6 → 1
   - Backup created with timestamp

4. **Generate Transcript**
   - Choose menu option 1 → 5
   - Enter student ID

## Screenshots

### Installation Verification
```
C:\>java -version
java version "11.0.16" 2022-07-19 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.16+11-LTS-199)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.16+11-LTS-199, mixed mode)
```

### Eclipse Project Setup
- Project structure in Package Explorer
- Run configuration dialog
- Console output showing application execution

### Program Execution
- Main menu display
- Student management operations
- Course search and filtering
- Grade recording and GPA calculation
- File import/export operations
- Backup creation and size calculation

### File Operations
- CSV file structure
- Backup directory with timestamped folders
- Recursive directory size calculation

## Enabling Assertions

To enable assertions when running the application:

```cmd
java -ea -cp src edu.ccrm.cli.Main
```

Or in Eclipse:
1. Right-click Main.java → Run As → Run Configurations
2. Arguments tab → VM arguments: `-ea`
3. Apply and Run

## Acknowledgments

This project demonstrates comprehensive Java SE programming concepts including:
- Object-oriented programming principles
- Advanced Java features and APIs
- Design patterns and best practices
- File I/O operations with NIO.2
- Functional programming with Streams
- Recursive algorithms and data structures

## License

This project is created for educational purposes as part of a Java programming course.

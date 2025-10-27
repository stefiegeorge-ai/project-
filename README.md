# project-troduction
This SQL project, titled Student Result Processing System, is designed to manage and automate the processing of student academic records. The system handles student enrollment, course data, grade management, and automated GPA calculations using MySQL. It includes a comprehensive schema, sample data, and triggers to streamline database operations.
Database Schema
The project uses the following tables:
Students: Holds student-specific information.
Semesters: Stores semester details.
Courses: Contains course information.
GradeScale: Defines the mapping of letter grades to point values.
Enrollments: Links students, courses, and semesters, along with the student's grade for that course.
StudentSemesterResult: Stores the calculated SGPA for each student per semester.
StudentCGPA: Stores the overall CGPA for each student.

Key Logic and TriggersThe core automation of this system is handled by two triggers:trg_after_enroll_insert: This trigger fires after a new enrollment record is inserted. It calculates and updates both the StudentSemesterResult (SGPA) and StudentCGPA tables for the affected student.trg_after_enroll_update: This trigger fires after an enrollment record is updated (e.g., changing a grade). It re-calculates the SGPA and CGPA to ensure all grades are accurately reflected.The GPA logic is as follows:SGPA: \(SGPA=\frac{\sum (Course\ Credits\times Grade\ Point)}{\sum (Course\ Credits)}\)CGPA: \(CGPA=\frac{\sum (Total\ Credits\times Grade\ Point)}{\sum (Total\ Credits)}\)

## Code

`` public class Course {
    // Course number and title
    private String courseNumber;
    private String courseTitle;

    public void setCourseNumber(String courseNumber) {
        this.courseNumber = courseNumber;
    }

    public String getCourseNumber() {
        return courseNumber;
    }

    public void setCourseTitle(String courseTitle) {
        this.courseTitle = courseTitle;
    }

    public String getCourseTitle() {
        return courseTitle;
    }

    // Print course info
    public void PrintInfo() {
        System.out.println("Course Information:");
        System.out.println("   Course Number: " + courseNumber);
        System.out.println("   Course Title: " + courseTitle);
    }
}
``

``Java

public class OfferedCourse extends Course {
    // Additional offered course details
    private String instructorName;
    private String location;
    private String classTime;

    public void setInstructorName(String instructorName) {
        this.instructorName = instructorName;
    }

    public String getInstructorName() {
        return instructorName;
    }

    public void setLocation(String location) {
        this.location = location;
    }

    public String getLocation() {
        return location;
    }

    public void setClassTime(String classTime) {
        this.classTime = classTime;
    }

    public String getClassTime() {
        return classTime;
    }

    // Include additional info for OfferedCourse
    @Override
    public void PrintInfo() {
        // Print the regular course info
        super.PrintInfo();
        // Print extra info
        System.out.println("   Instructor Name: " + instructorName);
        System.out.println("   Location: " + location);
        System.out.println("   Class Time: " + classTime);
    }
}
``

``Java

public class DerivedClasses {
    public static void main(String[] args) {
        // Create 1st course using Course class
        Course course1 = new Course();
        course1.setCourseNumber("ECE287");
        course1.setCourseTitle("Digital Systems Design");
        course1.PrintInfo();

        // Create 2nd course using OfferedCourse class
        OfferedCourse course2 = new OfferedCourse();
        course2.setCourseNumber("ECE387");
        course2.setCourseTitle("Embedded Systems Design");
        course2.setInstructorName("Mark Patterson");
        course2.setLocation("Wilson Hall 231");
        course2.setClassTime("WF: 2-3:30 pm");
        course2.PrintInfo();
    }
}
``

![2024Flowchart (1)](https://github.com/user-attachments/assets/69e9332b-354c-4294-b7f0-a50a2a239fa9)

Matching the expected output format was a challenge. Since the class PrintInfo() uses a couple System.out.println() calls, I had to be
careful when adding the extra information in OfferedCourse so that the format stays consistent


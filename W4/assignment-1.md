## Code

``Java
public class StudentDerivationFromPerson {
   public static void main(String[] args) {
      // Create student object
      Student courseStudent = new Student();

      // Create the students Id, name, and age using subclass methods
      courseStudent.setName("Smith");
      courseStudent.setAge(20);
      courseStudent.setID(9999);

      // Print student name and age using printAll(),
      // and then print Id using a println() statement.
      courseStudent.printAll();
      System.out.println(", ID: " + courseStudent.getID());
   }
}
``

![Flowchart2020](https://github.com/user-attachments/assets/54c6c6f5-94d0-4009-99ab-52f0ae285b71)

The biggest challenge for me was trying to understand how the Student class inherits from the Person class. 
Trying to know that the setName and setAge methods defined in Person are in the Student class.


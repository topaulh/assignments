## Code

```Java

import java.sql.*;

public class StudentDatabaseManipulation {
    public static void main(String[] args) {
        // Database credentials
        String url = "jdbc:mysql://localhost:3306/Miramar";
        String user = "root";
        String password = "password";

        try {
            // Connect to the database
            Connection conn = DriverManager.getConnection(url, user, password);
            System.out.println("Connected to database.");

            // Insert record
            String insertSQL = "INSERT INTO Student (SSN, FirstName, MiddleName, LastName, DOB, Street, Phone, Zipcode, deptID) " +
                               "VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?)";
            PreparedStatement insertStmt = conn.prepareStatement(insertSQL);
            insertStmt.setString(1, "111222333");
            insertStmt.setString(2, "Philip");
            insertStmt.setString(3, "David Charles");
            insertStmt.setString(4, "Collins");
            insertStmt.setDate(5, Date.valueOf("1951-01-30"));
            insertStmt.setString(6, "NA");
            insertStmt.setString(7, "NA");
            insertStmt.setString(8, "NA");
            insertStmt.setInt(9, 1234);
            insertStmt.executeUpdate();
            System.out.println("Record inserted.");

            // Update record
            String updateSQL = "UPDATE Student SET Zipcode = ? WHERE SSN = ?";
            PreparedStatement updateStmt = conn.prepareStatement(updateSQL);
            updateStmt.setString(1, "92126");
            updateStmt.setString(2, "111222333");
            updateStmt.executeUpdate();
            System.out.println("Zipcode updated.");

            // Close connection
            conn.close();
            System.out.println("Database connection closed.");
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}

```

Some challenges I faced while doing this was setting up JDBC driver and making sure it's in the right classpath. I also faced issues while 
making sure the MySQL server was running and that the database exists.





![Untitled Diagram drawio](https://github.com/user-attachments/assets/7d7b87ab-ad2a-499f-93a9-98136d60df60)

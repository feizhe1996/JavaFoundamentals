# JDBC



```{java}
package com.example.text;
 
 import java.sql.DriverManager;
 import java.sql.ResultSet;
 import java.sql.SQLException;
 import java.util.Date;
 
 public class SimpleJDBCTest {
 
    public static void main(String[] args) {
        String url = "jdbc:derby://localhost:1527/EmployeeDB";
        String username = "public";
        String password = "tiger";
        String query = "SELECT * FROM Employee";
        try (Connection con = 
             DriverManager.getConnection (url, username, password);
             Statement stmt = con.createStatement ();//java.sql.Statement: An object used to execute a static SQL statement and return the result

             ResultSet rs = stmt.executeQuery (query)) {
			while (rs.next()) {
              int empID = rs.getInt("ID");
              String first = rs.getString("FirstName");
              String last = rs.getString("LastName");
              Date birthDate = rs.getDate("BirthDate");
              float salary = rs.getFloat("Salary");
              System.out.println("Employee ID:   " + empID + "\n"
              + "Employee Name: " + first + " " + last + "\n"
              + "Birth Date:    " + birthDate + "\n"
              + "Salary:        " + salary);
          } // end of while
      } catch (SQLException e) {
          System.out.println("SQL Exception: " + e);
      } // end of try-with-resources
   }
 }
```



### SQL Exception

```{java}
catch(SQLException ex) {
     while(ex != null) {
         System.out.println("SQLState:  " + ex.getSQLState());
         System.out.println("Error Code:" + ex.getErrorCode());
         System.out.println("Message:   " + ex.getMessage());
         Throwable t = ex.getCause();
         while(t != null) {
             System.out.println("Cause:" + t);
             t = t.getCause();
         }
         ex = ex.getNextException();
    }
 }

```


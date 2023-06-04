# Java Database Connectivity (JDBC API)

## Steps

1. Make a new package/folder for JDBC connection
2. Download Correct Driver for the database you are using
3. Go to File > Project Structure > Libraries
4. Click the `+` button then add the correct driver you downloaded

## Why?

JDBC is a middleman between Java app and data source, so we need a driver to use a particular data source.

- For PostgreSQl you will need PostgreSQL driver

The driver is simply a library containing classes that implement the API

## How to connect

```java
private static final String USERNAME = "postgres";
private static final String PASSWORD = "lol";

// This URL has the DB NAMe at the end of it already
private static final String URL = "jdbc:postgresql://localhost:5432/postgres";

public static void main(String[] args) {
    try {
        Connection connection = DriverManager.getConnection(URL, USERNAME, PASSWORD);
        System.out.println("Successful Connection");

        connection.close();
        } catch(SQLException e) {
            System.out.println("Couldn't connect: " + e.getMessage());
        }
}
```

- `jdbc:` specifies the Java Database Connectivity (JDBC) protocol.
- `postgresql://` indicates the specific database management system being used, which is PostgreSQL in this case.
- `localhost` refers to the hostname or IP address of the server where the PostgreSQL database is running. In this case, it's assuming the database is running on the same machine where the code is executed.
- `5432` is the default port number used by PostgreSQL for database connections. It represents the port on which the PostgreSQL server is listening.
- `/postgres` is the name of the specific database within the PostgreSQL server that you want to connect to. In this case, it assumes there is a database named "postgres" that the code will connect to. if there is a DB named recipes then put `/recipes`

## Utility Connection

Make the act of getting a connection into a utitlity function in another class so you can call `getConnection` using a function

- Will be easier to execute SQL statements

```java
package JDBC;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DBUtils {
    private static final String USERNAME = "postgres";
    private static final String PASSWORD = "lol";
    private static final String URL = "jdbc:postgresql://localhost:5432/postgres";

    private DBUtils() {}

    public static Connection getConnection() {
        try {
            return DriverManager.getConnection(URL, USERNAME, PASSWORD);
        } catch(SQLException e) {
            throw new RuntimeException(e);
        }
    }
}

```

## Executing Statements

> Remember using the utility function

This will be the templete to use for executing query styatements

```java
public class JDBCStatement {
    public static void main(String[] args) throws SQLException {
        String query = "Whatever you want to do";
        try {
            // Utitlity function from other class
            Connection db = DBUtils.getConnection();
            Statement statement = db.createStatement()

            statement.execute(
            "UPDATE contacts SET phone=123" WHERE name='Jane'
            )

            // Rememebr to close both
            statement.close()
            db.close();
        } catch (SQLException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

## Selcting From Database

`executeQuery()` rerturns the result

```java
// Stores SELECT in results
ResultSet results = statement.executeQuery("SELECT * FROM ingredients");
while(results.next()) { //.next moves to next row
    // Gets each column by the index instead of column name
    System.out.println(results.getString(2) + " | " + results.getString(4));
}
results.close();
```

## SQL Injections

use prepared statements

```java
String query = "INSERT INTO user (first_name, last_name, email, fk_user_role, money) VALUES (?, ?, ?, ?, ?)";

var db = DBUtils.getConnection()
PreparedStatement preparedStatement = conn.prepareStatement(query)

// the index specify the corresponding `?` mark to add statement to
preparedStatement.setString(1, "Dmytriy");
preparedStatement.setString(2, "Voloshov");
preparedStatement.setString(3, "d.voloshov@email.com");
preparedStatement.setInt(4, 4);
preparedStatement.setInt(5, 0);

int rows = preparedStatement.executeUpdate();
System.out.println(rows);
preparedStatement.close();
db.close()
```

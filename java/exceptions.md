# Exceptions

> The core advantage of exception handling is to maintain the normal flow of the application. An exception normally disrupts the normal flow of the application; that is why we need to handle exceptions.

Unchecked/Runtime Exceptions:

- They are not checked at compile-time but at run-time.

For example: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException, exceptions under Error class, etc.

Checked Exceptions:

- These have to be handled. For example, IOException, InterruptedException, etc.

You should handle all exceptions even runtime exceptions

### Java throw keyword

The throw keyword is used to explicitly throw a single exception.

When an exception is thrown, the flow of program execution transfers from the try block to the `catch{}` block. We use the throw keyword within a method.

## Exception on a method

- When you specify that it throws a exception you don't handle it here
- Any class that implements/uses the method must handle the exception by using `try-catch-block`

```java
public static Connection getConnection() throws SQLException {
    return DriverManager.getConnection(URL, USERNAME, PASSWORD);
}
```

# Exceptions

Unchecked Exceptions:

- They are not checked at compile-time but at run-time.For example: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException, exceptions under Error class, etc.

Checked Exceptions:

- They are checked at compile-time. For example, IOException, InterruptedException, etc.

Usually, we don't need to handle unchecked exceptions. It's because unchecked exceptions occur due to programming errors. And, it is a good practice to correct them instead of handling them.

### Java throw keyword

The throw keyword is used to explicitly throw a single exception.

When an exception is thrown, the flow of program execution transfers from the try block to the `catch{}` block. We use the throw keyword within a method.

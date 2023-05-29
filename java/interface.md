# Interface

## Java Interface:

tldr: like a blueprint for methods that all classes that implement it must have

Use case:

- If you want all classes that aren't neccessarily realted to have the same methods use interface

Think of an interface as a set of rules or a contract that a class agrees to follow.
It only provides a list of methods (actions) that a class implementing the interface must have, without specifying how those methods are implemented.
It's like a blueprint that tells a class what methods it must have, but it doesn't provide any actual code for those methods.
An interface can be implemented by multiple unrelated classes.
It allows different classes to have common behavior, even if they are not related by inheritance.

> Fields declared in interface are static and final

## Java Abstract Class:

Think of an abstract class as a partially built class that needs to be completed by its subclasses.
It can have both method declarations (like an interface) and method implementations (actual code).
An abstract class provides a base structure that other classes can inherit from and customize as needed.
It allows you to define common behavior and state (variables) that can be shared by the subclasses.
An abstract class can be extended by only one subclass due to the limitations of single inheritance.

| Feature                | Java Interface                                                   | Java Abstract Class                                                   |
| ---------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------- |
| Instantiation          | Cannot be instantiated directly                                  | Cannot be instantiated directly                                       |
| Method Definitions     | Contains only method signatures (no method bodies)               | Can have both abstract methods and concrete methods                   |
| Fields                 | Can have constant fields                                         | Can have instance variables and other regular class members           |
| Inheritance            | Allows multiple interface implementation                         | Supports single class inheritance                                     |
| Default Implementation | Can have default methods and static methods (Java 8 onwards)     | No default method implementation                                      |
| Method Implementation  | Implementing classes must provide implementation for all methods | Implementing classes must provide implementation for abstract methods |
| Usage                  | Defines a contract for unrelated classes                         | Provides a common base implementation for subclasses                  |
| Polymorphism           | Enables polymorphic behavior                                     | Enables polymorphic behavior                                          |

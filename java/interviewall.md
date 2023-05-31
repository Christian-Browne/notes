# Interview Questions

1. **What is Java?**

   - Java is a high-level, object-oriented programming language developed by Sun Microsystems (now Oracle) in 1995. It is platform-independent, meaning it can run on various operating systems.

2. **What are the key features of Java?**

   - Some of its key features include object-oriented, platform independent, secure, robust, multithreaded and supports automatic memory management.

3. **What is JVM and is it platform independent?**

   - The Java Virtual Machine (JVM) is an engine that provides a runtime environment to drive the Java code. JVM is not platform independent, it is platform specific.

4. **What is the difference between JDK, JRE, and JVM?**

   - JVM is an abstract machine that provides a runtime environment in which java bytecode can be executed. JRE is an implementation of the JVM which physically exists. It contains a set of libraries + other files that JVM uses at runtime. JDK is a bundle of software that you can use to develop Java-based applications.

5. **What is the difference between == and equals() in Java?**

   - The '==' operator compares the reference or memory address of objects, not their content, while the equals() method compares the content of the objects.

6. **What are Java Classes and Objects?**

   - A Class in Java is a blueprint which includes all your data. A Class is used to bind data as well as methods together as a single unit. An Object is an instance of a Class.

7. **What are constructors in Java?**

   - A constructor in Java is a special method that is used to initialize objects. The constructor is called when an object of a class is created.

8. **What is the purpose of 'this' keyword in Java?**

   - 'this' keyword in Java is a reference variable that refers to the current object. It is used to refer to the current instance of a method, constructor, or variable of the current object.

9. **Explain method overloading and overriding in Java.**

   - Overloading in Java is the ability to create multiple methods with the same name, but different parameters. Overriding means having two methods with the same method name and parameters, one in the parent class and another in the child class or subclass.

10. **What is polymorphism in Java?**

    - Polymorphism in Java is a concept by which we can perform a single action in different ways. We can perform polymorphism in java by method overloading and overriding.

11. **What is Inheritance in Java?**

    - Inheritance in Java is a mechanism in which one object acquires all the properties and behaviors of a parent object. It provides code reusability and method overriding.

12. **What is an interface in Java?**

    - An interface in Java is a blueprint of a class or you can say it is a collection of abstract methods and static constants. It is a way to achieve abstraction and multiple inheritance in Java.

13. **What is an abstract class in Java?**

    - An abstract class in Java is a class that can't be instantiated. It can have abstract and non-abstract methods (method with body).

14. **What is Encapsulation in Java?**

    - Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit.

15. **What is an exception in Java?**

    - An exception in Java is an event that disrupts the normal flow of the program. It is an object which is thrown at runtime.

16. **What is the difference between checked and unchecked exceptions?**

    - Checked exceptions are checked at compile-time while unchecked exceptions are checked at runtime. Examples of checked exceptions include IOException, SQLException, etc. Unchecked exceptions include RuntimeException, Errors, etc.

17. **What is a Java package and what are its advantages?**

    - A package in Java is used to group related classes. It helps organize your classes into a folder structure and makes it easy to locate and use them. It also provides access protection.

18. **What is multithreading in Java?**

    - Multithreading in Java is a feature that allows concurrent execution of two or more parts of a program for maximum utilization of CPU.

19. **What is the difference between a process and a thread?**

    - A process is a self-contained execution environment and it can run multiple threads. A thread is a lightweight subprocess and the smallest unit of processing. Threads share the same memory space.

20. **What is synchronization in the context of multithreading?**

    - Synchronization in Java is the capability to control the access of multiple threads to shared resources. It helps prevent thread interference and consistency problems.

21. **What is deadlock in the context of multithreading?**

    - Deadlock describes a situation where two or more threads are blocked forever, waiting for each other.

22. **What is a Java collection?**

    - The Java Collections Framework is a set of classes and interfaces that implement commonly reusable collection data structures like List, Set, and Map.

23. **What is the difference between List, Set and Map?**

    - List in Java is an ordered collection, it can contain duplicate elements. Set is an unordered collection of object in which duplicate values cannot be stored. Map is an object that stores key-value pairs.

24. **What is the difference between ArrayList and LinkedList?**

    - ArrayList is backed by an array and provides fast access but slow insertions and deletions. LinkedList, on the other hand, is implemented with a doubly linked list providing faster insertions and deletions but slower access.

25. **What is a Lambda Expression in Java?**

    - A Lambda Expression is a new feature of Java 8, which provides a clear and concise way to represent a method interface using an expression. It is used to implement functional programming in Java.

26. **What are Java Streams?**

    - In Java 8, the Stream API was introduced as a new abstraction which lets you process data in a declarative way. It can be parallelized automatically to leverage multicore architectures.

27. **What is Java I/O?**

    - Java I/O (Input and Output) is used to process the input and produce the output. Java uses the concept of streams to make I/O operation fast.

28. **What is Serialization and Deserialization in Java?**

    - Serialization is a mechanism of converting the state of an object into a byte stream. Deserialization is the reverse process where the byte stream is used to recreate the actual Java object in memory.

29. **What is the difference between Serialization and Externalization in Java?**

    - Serialization in Java allows us to convert an Object to stream that we can send over the network or save it as file or store in DB for later usage. Externalization is a customized version of Serialization where we write our own methods to serialize the object.

30. **What is JDBC?**

    - JDBC stands for Java Database Connectivity. It is a standard Java API for database-independent connectivity between Java & a wide range of databases.

31. **What are drivers in JDBC?**

    - A JDBC driver is a software component enabling a Java application to interact with a database. There are 4 types of JDBC drivers: JDBC-ODBC bridge driver, Native-API driver (partially java driver), Network Protocol driver (fully java driver) and Thin driver (fully java driver).

32. **Explain the steps to connect to a database in java?**

    - The steps to connect to a database in Java are: Register the driver class, Create connection, Create statement, Execute queries, Close connection.

33. **What are the different types of statements in JDBC?**

    - The different types of statements in JDBC are Statement, PreparedStatement, and CallableStatement.

34. **What is Java Persistence API (JPA)?**

    - The Java Persistence API (JPA) is the Java standard for mapping Java objects to a relational database. It provides an easy way to perform database operations on Java entities.

35. **What is Hibernate in Java?**

    - Hibernate is a popular object-relational mapping and query service for Java. It provides a framework for mapping an object-oriented domain model to a traditional relational database.

36. **What are Annotations in Java?**

    - Annotations are a form of metadata provide data about a program that is not part of the program itself. They have no direct effect on the operation of the code they annotate.

37. **What is reflection in Java?**

    - Java Reflection is a process of examining or modifying the run time behavior of a class at run time.

38. **What is JavaBeans?**

    - JavaBeans are reusable software components for Java that can be manipulated visually in a builder tool. A JavaBean property is a named attribute that can be accessed by the user of the object.

39. **What is JSP?**

    - JavaServer Pages (JSP) is a technology used to develop web pages that support dynamic content which helps developers insert java code in HTML pages.

40. **What is Servlet in Java?**

    - A Servlet is a Java class that is used to extend the capabilities of servers that host applications accessed via a request-response model. Servlets can respond to any type of request, but they are commonly used to extend the applications hosted by web servers.

41. **What is the difference between Servlet and JSP?**

    - A Java Servlet is a Java class that is used to extend the capabilities of servers that host applications accessed via a request-response programming model. JSP is a technology that helps software developers create dynamically generated web pages based on HTML, XML, or other document types.

42. **What is the Spring framework in Java?**

    - Spring is a powerful, lightweight framework used for application development. It provides comprehensive infrastructure support for developing Java applications.

43. **What is Dependency Injection in the context of Spring?**

    - Dependency Injection (DI) is a design pattern that removes the dependency from the programming code so that it can be easy to manage and test the application. DI provides objects that an object needs.

44. **What is a Spring Bean?**

    - A Spring Bean is an object that forms the backbone of your application and that is managed by the Spring IoC container. The bean is created with the configuration metadata that you supply to the container.

45. **What is Aspect-Oriented Programming (AOP) in the context of Spring?**

    - AOP is a programming paradigm that aims to increase modularity by allowing the separation of cross-cutting concerns. In the context of Spring, it is used to modularize cross-cutting concerns in aspects.

46. **What is the Model-View-Controller (MVC) pattern in the context of Spring?**

    - The Spring Web MVC framework provides Model-View-Controller (MVC) architecture and components that can be used to develop flexible and loosely coupled web applications. MVC divides the application into three interconnected parts: the model, the view, and the controller.

47. **What is a RESTful API and how does it work in Java?**

    - A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data. In Java, RESTful APIs can be created using various libraries or frameworks such as JAX-RS, Restlet, Jersey, or Spring.

48. **What is JUnit?**

    - JUnit is a popular testing framework for Java programming language. It is used to write and run repeatable automated tests.

49. **What is Mockito?**

    - Mockito is a mocking framework that tastes really good. It lets you write beautiful tests with a clean & simple API. Mockito doesn’t give you hangover because the tests are very readable.

50. **How can you handle exceptions in Java?**

    - Exceptions in Java can be handled using try-catch blocks. We can also use a finally block to ensure a block of code executes regardless of whether an exception occurs.

51. **What is the difference between a final, finally and finalize in Java?**

    - 'final' is a keyword in java used for restricting some types of class and variable modifications. 'finally' is a block that is used to execute important code such as closing connection, stream etc. 'finalize' is a method that is called by JVM during garbage collection.

52. **What is the purpose of the System class in Java?**

    - The purpose of the System class in Java is to provide access to system resources. It contains several useful class fields and methods like standard input, output methods and methods for loading files and libraries.

53. **What is the purpose of the Runtime class in Java?**

    - The purpose of the Runtime class in Java is to provide access to the Java runtime system. The runtime information like memory availability and system environment details can be obtained using this class.

54. **What are Wrapper Classes in Java?**

    - Wrapper classes convert the Java primitives into the reference types (objects). Each primitive data type has a class dedicated to it, these are known as wrapper classes because they "wrap" the primitive data type into an object of that class.

55. **What is autoboxing and unboxing in Java?**

    - Autoboxing is the automatic conversion of primitive types to the object of their corresponding wrapper classes. Unboxing is the conversion of an object of a wrapper type to its corresponding primitive value.

56. **What is an enum in Java?**

    - Enum in Java is a keyword, a feature which is used to represent fixed number of well-known values in Java, For example, Number of days in Week, Number of planets in Solar system etc.

57. **What is the difference between break and continue statements in Java?**

    - The break statement terminates the loop immediately when it is encountered. The continue statement skips the current iteration of the loop and continues with the next iteration.

58. **What is the difference between the public, protected, and private keywords in Java?**

    - Public, protected, and private are access modifiers in Java. Public members are accessible everywhere, protected members are accessible within the same package and also from subclasses, and private members are accessible only within the same class.

59. **What is the difference between an array and an ArrayList in Java?**

    - An array is basic functionality provided by Java. ArrayList is part of collection framework in Java. Therefore array members are accessed using [], while ArrayList has a set of methods to access elements and modify them.

60. **What is the difference between a static and a non-static method in Java?**

    - A static method belongs to the class rather than the object. There is no need of creating an instance to call the static method. A non-static method belongs to an object of the class and you need to create an instance of class to access it.

61. **What is the difference between a shallow copy and a deep copy in Java?**

    - A shallow copy in Java is bitwise copy of an object. A new object is created that has an exact copy of the values in the original object. A deep copy copies all fields, and makes copies of dynamically allocated memory pointed to by the fields.

62. **What is the difference between an abstract class and an interface in Java?**

    - Abstract class in Java is used to provide a common type for all subclasses, so it can't be instantiated and it can have non-abstract methods (method with body). An interface is a contract/template/blueprint and is used to achieve full abstraction and multiple inheritance in Java.

63. **What is the default size of the load factor in hashing based collection?**

    - The default load factor of a HashMap in Java is 0.75f (75% of the map size).

64. **What are different ways to create an object in Java?**

    - Objects in Java can be created in several ways: Using new keyword, Using Class.forName(), Using clone() method, Using new Instance() method and Using deserialization.

65. **What are different ways to create a string object in Java?**

    - There are two ways to create String object: By string literal and By new keyword.

66. **What is the purpose of the toString() method in Java?**

    - The toString() method returns a string representation of an object. It is often used for debugging purposes.

67. **What is the hashCode() and equals() method in Java?**

    - The hashCode() method returns a hash code value for the object. This method is supported for the benefit of hash tables. The equals() method indicates whether some other object is "equal to" this one.

68. **What is the difference between a Stack and a Queue?**

    - A Stack is a data structure where the last element added is the first one to be removed (LIFO). A Queue is a data structure where the first element added is the first one to be removed (FIFO).

69. **What is the difference between an error and an exception in Java?**

    - An error is a serious problem that a reasonable application should not try to catch, whereas an exception is a condition that a reasonable application might want to catch.

70. **What is the difference between the throw and throws keywords in Java?**

    - The 'throw' keyword in Java is used to explicitly throw an exception from a method or any block of code. 'throws' keyword is used to declare an exception.

71. **What is the difference between a Java library and a Java framework?**

    - The key difference between a library and a framework is "Inversion of Control". When you call a method from a library, you are in control. But with a framework, the control is inverted: the framework calls you.

72. **What are the different types of memory areas allocated by JVM?**

    - Different types of memory areas allocated by JVM are: Method Area, Heap Area, Stack Area, Program Counter Register, and Native Method Stack.

73. **What is ClassLoader in Java?**

    - The ClassLoader is a part of the Java Runtime Environment that dynamically loads Java classes into the Java Virtual Machine.

74. **What is the default value of the local variables?**

    - The local variables are not initialized to any default value, neither primitives nor object references.

75. **What is a marker interface?**

    - A marker interface in Java is interfaces with no field or methods. An example in Java is the Serializable interface. They are used to provide some essential information to the JVM so that JVM can perform some useful operations.

76. **What is the purpose of the clone() method in Java?**

    - The purpose of the clone() method in Java is to create and return a copy of an object.

77. **What is the Singleton pattern in Java?**

    - The singleton pattern is a design pattern that restricts the instantiation of a class to one single instance. This is useful when exactly one object is needed to coordinate actions across the system.

78. **What is the Factory pattern in Java?**

    - The factory pattern is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

79. **What is the difference between overloading and overriding in Java?**

    - Method overloading is when multiple methods have the same name but different parameters. Method overriding is when a subclass provides a specific implementation of a method that is already provided by its superclass.

80. **What is the difference between == and equals() in Java?**

    - The '==' operator compares the memory location of two references, not their values. It checks to see if the two operands point to the same object, not equivalent objects. On the other hand, the equals() method actually compares the two objects.

81. **What is the difference between an ArrayList and a Vector in Java?**

    - ArrayList is not synchronized while Vector is. This means two threads can call the methods of an ArrayList simultaneously while only one thread can call the methods of a Vector at a time.

82. **What is the difference between a HashSet and a TreeSet in Java?**

    - The HashSet class in Java makes no guarantees as to the iteration order of the set; in particular, it does not guarantee that the order will remain constant over time. A TreeSet is a NavigableSet implementation based on a TreeMap. The elements are ordered using their natural ordering, or by a Comparator provided at set creation time, depending on which constructor is used.

83. **What is the difference between a HashMap and a Hashtable in Java?**

    - Hashtable is synchronized, whereas HashMap is not. This makes HashMap better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones. Hashtable does not allow null keys or values. HashMap permits a null key and any number of null values.

84. **What is Polymorphism in Java?**

    - Polymorphism in Java is a concept by which we can perform a single action in different ways. So polymorphism means many forms.

85. **What is Encapsulation in Java?**

    - Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit.

86. **What is Inheritance in Java?**

    - Inheritance in Java is a mechanism in which one object acquires all the properties and behaviors of a parent object.

87. **What is a local, member and a class variable?**

    - Local variables are defined in the method and scope of the variables exist only within the method. Member Variable is a variable that is declared inside the class but outside the method. Class Variables are variables declared with in a class, outside any method, with the static keyword.

88. **What is Constructor Overloading and Method Overloading in Java?**

    - Constructor overloading in Java is a technique of having more than one constructor with different parameter lists. They are arranged in a way that each constructor performs a different task. Method Overloading is a feature that allows a class to have more than one method having the same name, if their argument lists are different.

89. **What is Association, Aggregation, and Composition in Java?**

    - Association is a relationship where all objects have their own lifecycle and there is no owner. Aggregation is a specialized form of Association where all objects have their own lifecycle but there is ownership. Composition is a specialized form of Aggregation and we can call this as a “death” relationship.

90. **What is the difference between Path and Classpath?**

    - The Path is the system variable that your operating system uses to locate needed executables from the command line or Terminal window. The Classpath is the parameter in the Java Virtual Machine or the Java compiler that specifies the location of user-defined classes and packages.

91. **What is a Java package and how is it used?**

    - A Java package is a namespace that organizes a set of related classes and interfaces. Conceptually you can think of packages as being similar to different folders on your computer.

92. **What are Java Annotations?**

    - Java Annotations provide information about the code and they have no direct effect on the code they annotate.

93. **What is the use of the super keyword in Java?**

    - The super keyword in Java is a reference variable that is used to refer parent class objects.

94. **What is the use of the this keyword in Java?**

    - In Java, this is a reference variable that refers to the current object.

95. **What is the difference between a JDK and a JVM?**

    - JDK stands for Java Development Kit. It is a software development environment which is used to develop Java applications and applets. JVM stands for Java Virtual Machine. It is an abstract machine. It is a specification that provides a runtime environment in which Java bytecode can be executed.

96. **What is a JVM and what does it do?**

    - JVM stands for Java Virtual Machine. It is a specification that provides a runtime environment in which Java bytecode can be executed. JVMs are available for many hardware and software platforms.

97. **What are the different types of inheritance in Java?**

    - In Java, there are three types of inheritance; single, multilevel, and hierarchical. Java does not support multiple inheritance with classes, although it is possible to achieve with interfaces.

98. **What is the difference between a Window and a Frame?**

    - The Frame extends Window to define a main application window that can have a menu bar. A Frame object is a top-level window with a title and a border.

99. **What is the purpose of a private constructor in Java?**

    - A private constructor is used to prevent the class from being instantiated and to be subclassed.

100. **What is garbage collection in Java, and when is it used?**


    - Garbage Collection in Java is a process by which the programs perform automatic memory management. Java programs compile into bytecode that can be run on a Java Virtual Machine. When Java programs run on the JVM, objects are created on the heap, which is a portion of memory dedicated to the program.

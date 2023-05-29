# Static & Final

> Static: belonging to a class

Static variable is a variable that is shared across all instances of class that declared it

- Stays the same
- Example: keeping count of all class instances
- all subclasses can have access of the static count

Static function is one that doesn't modify variables or take in fields that are in the class

- Staic method are mostly used for utility functions
- Children have access to static
- Ex. Sum function that sums any two numbers you pass in
- Class can call static method without having to create an instance
- other methods are instance methods

# Final

> Is a constant in Java (it's value can't change or be reassigned)

```java
public static final double TAX = 0.13;
```

In this example since it is `static` new `TAX` varibales won't be created everytime you make an instance of the class in.

They will all point to the same one in memory whcih is the only one

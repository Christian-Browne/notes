# Object Types

For any object type you can do this `Example.AnyMethod()` because it is a object and a object can have methods

- Big decimal, string, and other objects can have methods
- Any method on a object type makes a copy and modifies it unless you pass in a reference type like an array

You can't do methods on primitives such as ints, double
`num.toString()` won't work because a int is not a object

```java
int num = 24
num.toString()
```

Have to do this instead because primitive int isn't a object

```java
int num = 24
Int.toString(num)
```

This works because i'm using the Integer object type that has built-in methods

```java
Integer num = 2;
num.toString();
System.out.println(num);
```

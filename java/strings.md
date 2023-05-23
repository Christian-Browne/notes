# Strings

The reason why you can convert a string to an array using
`s.toCharArray()` is because the String class has certain methods that are relevant and useful for strings like `.trim()`

- The strings class still builds strings using arrays behind th escenes

Arrays have there own special methods as well

Strings are immutable in Java. using `.trim()` will create a copy

- This returns a reference to a new object

## String pool

Declaring strings using string literals the value will always be the same because the previous string is stored in the string pool so the second string will point to the same address of the first string

thats why this is true

```java
String s = "christian";
String s2 = "christian";

System.out.println(s == s2); // true
```

This is false because it creates a new string object in the heap that points to a different address

```java
String s = "christian";
String s2 = new String("christian");

System.out.println(s == s2); // false
```

Have to use equals if you want to check each char value in string

```java
String s = "christian";
String s2 = new String("christian");

System.out.println(s.equals(s2)); // true
```

# Generics

Allows a class to take in different **types** without having to specify

```java
public class Printer <T> {
    // this value field now can be any type
    private T value;

    // this constructer can take it many types
    public Printer(T value) {
        this.value = value;
    }

    public printValue() {
        System.out.println(this.value);
    }
}
```

Now this `Printer` class is sort of **generic** as you can now print any value/type you pass in

```java
Printer<Integer> printer = new Printer<>(23);
Printer<Double> dPrinter = new Printer<>(13.54);
```

You can't pass in primitives into a generic

- int, long, double won't work
- you have to use wrapper classes/objects

## Generics Extending Classes / Bounding Generics

The `T` type can now be any instance/child of animal like dog, cat, parrot.

This is better for type safety if you know that there are going to different child classes or instances of Animal class

```java
public class Printer <T extends Animal> {
    // know we know T can be a inmstance of animal
    private T value;

    public Printer(T value) {
        this.value = value;
    }

    public printValue() {
        /*
        We can call .eat() because all
        instances has the eat() method
        */
        value.eat()
        System.out.println(this.value);
    }
}
```

### Question

What's the point of `T extends animal` if I could could just make the field like this?

```java
private Animal value;
```

### Answer

TLDR: The reason for a generic in this case is that Java wouldn't know if it is a Dog or Cat class. It would only know that it is an instance of `Animal`.

- You woudn't be able to call **Dog** or **Cat** specific methods because it wouldn't know what type of Animal instance it is

The generic `T extends Animal` is useful when you need to ensure at compile time that the specific subtype of Animal is preserved for certain operations. It might be overkill for this simple scenario, but in more complex programs, generics can provide a powerful tool for type safety and code reusability.

## Multiple Bounds

- Generics can extend one class
- Can extend many interfaces
- use `&` for multiple bounds

```java
<T extends Animal & ExampleInterface>
```

## Generic Methods

Put generic type right before `return` type to let Java know that this is a function that will take in a generic type

```java
private static <T> void shout(T thingToShout) {
    System.out.println(sound + "!!!")
}

shout("john") // John!!!
shout(52) // 52!!!
```

## Multiple types

```java
private static <T, V> void shout(T thingToShout, V other) {}
```

## Return Generic Type

```java
private static <T, V> T shout(T thingToShout, V other) {}
```

## Wildcards

```Java
private static void printList(List<Object> myList) {
    system.out.println(myList)
}

// This wouldn't work because List<Integer> isn't a subclass
// It won't accept this type
List<Integer> intList = new ArrayList<>();
intList.add(3)
```

Even though Integer is a subclass of object `List<Integer>` isn't a subclass of List<Object>

### Have to use a wildcard instead

- Question mark is type of unkown when you don't know what type the `List` will be.

```Java
private static void printList(List<?> myList) {
    system.out.println(myList)
}
```

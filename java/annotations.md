# Annotations

- Annotations are like meta data that describe your code and can perform special things to chunk of code that has it.

## How to Make Custom Annotations

1. Defining a custom annotation MethodController

```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface MethodController {
    int times() default 1;
}
```

This defines a new annotation `MethodController`. The `@Target` meta-annotation specifies that this annotation can only be used on methods `(ElementType.METHOD)`. The `@Retention` meta-annotation specifies that this annotation is available at runtime `(RetentionPolicy.RUNTIME)`, which is necessary for our reflection-based approach to find and use this annotation later. This annotation has a single property times, which defaults to 1.

2.Using the annotation MethodController in class Dog

```java
public class Dog {
    private String name;

    public Dog(String name) {
        this.name = name;
    }

    @MethodController(times = 5)
    public void printDog() {
        System.out.println("This dog goes by: " + name);
    }
}
```

Here, a class `Dog` is created with a single private field name, and a public method `printDog` is annotated with our custom `MethodController `annotation. The `times` property is set to 5, which means we want to invoke this method 5 times.

3. Analyzing annotations at runtime in the `Main` class

```java
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Dakota");

        for (Method method : myDog.getClass().getDeclaredMethods()) {
            if (method.isAnnotationPresent(MethodController.class)) {
                MethodController annotation = method.getAnnotation(MethodController.class);

                for (int i = 0; i < annotation.times(); i++) {
                    try {
                        method.invoke(myDog);
                    } catch (Exception e) {
                        e.printStackTrace();
                    }
                }
            }
        }
    }
}
```

The `main` method creates a `Dog` instance named "Dakota". It then gets all declared methods of the `Dog` class and checks each method for the presence of the `MethodController` annotation. If the annotation is present, it retrieves the annotation from the method, gets the times property, and invokes the method as many `times` as specified by the `times` property. If anything goes wrong during the method invocation (such as an access violation, which shouldn't happen here as the method is public), it catches and prints the stack trace of the exception.

# Inner classes

keeps closely related code grouped together

Inner classes, or nested classes, in Java have several purposes:

Encapsulation:

- Inner classes can access the private variables of the outer class, which can keep the code more secure and clear.

Organization:

- If a class is useful to only one other class, then it's logical to embed it in that class and keep the two together. This kind of organization makes the code more readable.

Maintaining a Many-To-One relationship:

- If multiple instances of a class (the inner class) are associated with a single instance of another class (the outer class), then it's useful to nest the former within the latter.

Let's illustrate these points with two examples.

## Anonymous

- One time use class that can only be created one time
- Can't instanstiate class
- it's more so convinete

```java
Animal myAnimal = new Animal();
Animal.makeNoise()

// anonymous class
Animal big foot = new Animal () {
    // overides original methods
    public void makeNoise() {
        System.out.println("Grwalwlwe")
    }
}
```

Another way to do it using threads (runnable)

- look it up

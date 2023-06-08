# Constructors

## Private Constructors

private constructors make it so that you can't create a new instance of this class

- mostly used for utility classes or classes that you just want to use without creating a new instance.
- private constructors prevents new instances from being created (more so for safety)

```java
public class Constants {
    private Constants() {
    }
}
```

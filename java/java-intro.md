# Intro

## Primitve

- Store actual value

## Reference Types

- Store addresses to value
  - classes, arrays, etc

## Autoboxing and referencing

`int` stores the actual value

`Integer` stores the referenc/address to the value

- This is called autoboxing
- You can actually change the value when you pass it in to functions because you have the address/pointer to the value

### Example

```java
public class HelloWorld {
    // test comment

    public static void main(String[] args) {
        int i = 1;
        Integer i2 = 2;
    }
}
```

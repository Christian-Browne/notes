# Intro to Java

## Primitve

- Store actual value

## Reference Types

- Store addresses to value
  - classes, arrays, etc
- TIP: Arrays are automatically passed by reference into functions

## Autoboxing and referencing

`int` stores the actual value

`Integer` stores the reference/address to the value

- This is a Integer class
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

### Comparisons

`equals`

- Allows you to compare to reference types
- arrays, objects, etc

```java
int[] arr1 = {1, 2, 3};
int[] arr2 = {1, 2, 3};

System.out.println(Arrays.equals(arr1, arr2)); // true

```

# For Each

for each loop edits a copy of the array

- This doesn't work because num is a copy of the ith elemnt odf the array so it's not changing the original array

```java
public static void main(String[] args) {
		int[] arr = {1, 2, 3, 4};
        sum(arr);
        System.out.println(Arrays.toString(arr));
	}

    public static void sum(int[] array) {
        for (int num : array) {
            num *= 4;
        }
    }
```

This will work because it's changing the original array

```java
public static void main(String[] args) {
		int[] arr = {1, 2, 3, 4};
        sum(arr);
        System.out.println(Arrays.toString(arr));
	}

    public static void sum(int[] array) {
        for (int i = 0; i < array.length; i++) {
            array[i] *= 4;
        }
    }
```

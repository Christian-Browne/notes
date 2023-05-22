# Reference and Value

## Passing in Reference vs Value in a Function

In C, all function arguments are passed by value, which means that the function creates local copies of the passed variables and works with these copies. When you modify these copies inside the function, the original variables are not changed.

Here's an example of a swap function that won't work because it operates on copies of the original variables:

```c
#include <stdio.h>

void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int x = 5;
    int y = 10;

    printf("Before swap: x = %d, y = %d\n", x, y);
    swap(x, y);
    printf("After swap: x = %d, y = %d\n", x, y);

    return 0;
}
```

In the above example, the swap function swaps **a** and **b**, but since a and b are local copies of x and y, the original **x** and **y** variables remain unchanged.
Therefore, even after calling the swap function, **x** and **y** will have their original values.

> TIP: x & y are unchanged becuase the swap function is popped of the stack when it is done and the local variables a and b only changed.

### Solution

To make the swap function work, you need to pass pointers to the variables, essentially passing by reference. Here's the correct version of the swap function:

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5;
    int y = 10;

    printf("Before swap: x = %d, y = %d\n", x, y);
    swap(&x, &y);
    printf("After swap: x = %d, y = %d\n", x, y);

    return 0;
}
```

In this version, we're passing the addresses of **x** and **y** to the `swap()` function. Inside the function, we dereference these pointers to access the actual variables and perform the swap. After this function call, **x** and **y** will have swapped their values, because the function has modified them directly via their memory addresses.

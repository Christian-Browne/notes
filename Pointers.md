# Pointers

> 💡 Pointers in C allow us to poke around the computers hardware such as its memory.

> “C is the closest to the computers’ hardware you can get before things get **_scary_** such as using assembly languages”

## Pointers

- P is a variable that is stored in memory whose value is the address of n
  - It’s a variable that points to another variable

**IMPORTANT:**

- **_Everytime you create a pointer variable for the first time you are saying that this variable is a pointer_**

- **_Everytime/instance you use the `*` after that is when you are dereferencing the pointer by gettin the value at the address_**

```c
int n = 50;
// '*' lets C know that the p variable is a pointer
// '&n' means the address of n
int *p = &n;

pointer p = address of n // What it basically is
// p = 0x123

printf("%i\n", *p)
// *p here points to value at the address
// It's basically saying go to the address and get its value

printf("%p", p)
// This prints the value of the address p is pointing too
```

## Pointers and const

```c
int num = 45;

// Value pointed to by pointer cant be changed (Value: 45)
const int *p = &num
// WON'T WORK: *p = 50
// WORKS: p = &newNum


// pointer can't be changed
int const *p = &num
// WON'T WORK: p = &newNum
// WORKS: *p = 50

// Double Const: Can't change nothing
const int num2 = 45
const int const *p2 = &num2
```

## Void Pointers

Great if you are going to store pointers of different types inside of a single pointer variable.

Sort of a one pointer fits all

- char, int, double

You have to remember to cast the type to defeference it

### Example

```c
int i = 10;
float f = 2.34;
char ch = 'k';

void vptr;

/*
"int *" says that is a int pointer
The extra "*"outside of the cast derefereces the value so you can get the value
*/
vtpr = &i;
printf("i Value:%d\n", *(int *)vtpr);
// i Value: 10

vtpr = &f;
printf("f value:", *(float *)vtpr);
```

## Pointer and Arrays

Use pointers for arrays as they are generally more efficient because they use less memory and execute faster

- Character array is fixed size
- Pointer arrays can be dynamic in size

> character array is when you make a string using array. character pointer is made with pointers

```c
int values[100];
int *valptr;

// valptr now points to the first element in the array
valptr = values;
// or can do this which is more readable
valptr = &values[0];
```

## Pointers in Functions

- For functions parameters when you use a pointer you are just passing in the pointer type which should be an address

- If you do pass "const" pointer into a function that function is basically termed as a readonly as it doesn't modify or change the pointer

- If you want to modify the pointer don't make it a const in the function arguments

```c
void squareNum(int *num);

int main() {
    int num = 5;
    squareNum(&num);
    printf("Value: %d\n", num);

    return 0;
}

// Return void because it's changing the original values
void squareNum(int *num) {
    *num *= *num;
}
```

## Pointer Arithemetic

### How this code works

1. (Parenthesis first) Goes to the third address in the array
2. '\*' means to dereference it, so it goes to it's value
3. Changes it's value to 20

```c
int main() {
    int vals[100];
    vals[0] = 25;
    int *ptr = (int*)(malloc(3 * sizeof(int)));

    // 1. (Parenthesis first) Goes to the third address in the array
    // 2. '*' means to dereference it and to go to it's value
    // 3. changes it's value to 20

    *(ptr + 3) = 20;

    printf("%d", *(ptr + 3));

    free(ptr);

    return 0;
}
```

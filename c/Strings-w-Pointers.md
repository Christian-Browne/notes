# Strings with Pointers

> Remember the string data type value is just a **pointer to first address** in a string

## Return Pointers

- Some string functions in c return pointer as a value

### Code Example

- If you want to find a character inside of a string using the `strchr()` function
- It searches through the string for the character 'q' and then it returns a pointer to the the 'q' character in the string
  - The pointer is stored in a variable
  - After that in the `printf()` function I dereference the pointer and print it as a character

```c
int main () {
    char str[] = "The quick brown fox";
    char ch = 'q';

    char *pointer = NULL;
    pointer = strchr(str, ch);
    printf("Found ::: %c", *pointer);
    // Found ::: q

    return 0;
}
```

- Remember the pointer stores the address of something else that is already in memory
  - \*pointer on the right side of the equal sign means to dereference the pointer
  - Derefercing a pointer: Go to the address and get its value

## Returning strings from functions

- Return `char*` from a function beacuse you have to return pointer to first character in string
- Return char works when you just want to return a single character

```c
char* reverse(char str[]) {
    return "string";
}
```

## String Copying

- t is not it's own string
- **s** and **t** are pointers to the same string
- if i were to change/edit **t** it would also change **s** since they are both pointing to the same string in memory

```c
char s[] = "string1";
char t[] = s;
t[0] = 'A'
```

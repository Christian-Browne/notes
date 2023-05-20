# Memory Allocation

## Backround

How memory is laid out from top to bottom

| Memory           | Description                                    |
| ---------------- | ---------------------------------------------- |
| machine code     | Where your program runs                        |
| globals          | global variables                               |
| heap             | memory you can use (malloc grabs memory here)  |
| overflow section | if heap or stack collide here it's an overflow |
| call stack       | Where functions are called 3                   |

`malloc()`

- Specify how much memory you want allocated by byte
- Returns the address of the first byte allocated in memory

`calloc(), realloc()`

`free()`

- When you allocate memory with `malloc()` you have to free it when you're done with it
- Pass the variable to the function that is pointing to the first address you allocated

NULL

- Is address 0 in memory
- nothing there

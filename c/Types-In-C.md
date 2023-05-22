# Types in C

## Ints

- Integers are 4 bytes which is 32 bits
- 0000 0000 0000 0000 0000 0000 0000 0000

# How does C know it’s reading a character vs reading a integer from RAM?

### F**oundation:**

- char: 1 byte/ 8-bits
- intr: 4 bytes / 32-bits

### Binary representaion

- **char/ASCII: A** in binary: 01000001
    - stores ASCII A in 1 bytes/8-bits
- **int: 65** in binary: 0000 0000 0000 0000 0000 0000 01000001
    - stores the integer 65 across 4 bytes/32-bits
- RAM just stores the data, it doesn’t know how to interprwet it
- When C is reading through the RAM on your computer the compiler(clangg/gcc) gives it instructions on how to interpret the data. How we delare the variable lets the C compiler know what to do with that data.
- When C sees 0100001 in 1 byte it retireves the value and based on how you declared the varibale the compiler interprets it as a **character** or **integer**

```c
#include <stdio.h>

int main (void) {
    char a = 'A';

		/* 
		As you can see here 65 is stored as 01000001 in RAM, 
		printf() can interpret it as a character or a integer.
		*/
		printf("%c", a) // A
		printf("%i", a) // 65

}
```

# So, how does C-compiler tell my computer to read 4-bytes in RAM for a integer.

**Foundation: You have to know how C compiles code:** 

1. When code is compiled the code is converted to machine code 
2. Then executed from top to bottom.
3. In the machine code, compiler will tell computer where integer is in memory based on address
4. Machine code knows to read 4 bytes for a integer based on the compiler
5. Then it does whatever to int based on machine code instructions

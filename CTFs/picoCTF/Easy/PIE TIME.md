# PIE TIME

## Description
Can you try to get the flag? Beware we have PIE!

## Solution
Description says that we have PIE. PIE is a Position Independent Executable, which means that the binary is loaded at a random address in memory each time it is executed and thus the addresses of functions and variables are not fixed.

Using `nm` which displays the symbol table of an executable, we can see the addresses of functions and variables in the binary.

![](Images/pie-time.png)

I subtracted the address of `main` from the address of `win` to get the offset between them.

`0x133d - 0x12a7 = 0x96`

The program tells us that the address of main is at 0x62acdba6133d so we can find the address of win by subtracting the offset from it.

`0x62acdba6133d - 0x96 = 0x62acdba612a7`
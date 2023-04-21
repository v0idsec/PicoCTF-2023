# PicoCTF 2023 Challenge: babygame01

## Description
The goal of babygame01 is to reach the end by avoiding obstacles and enemies. Can you figure out how to win and get the flag?

## Steps Taken
1. Downloaded and Inspected the File: I downloaded the file for the challenge and inspected it to gain a better understanding of how the game works.

2. Realized the Position of '@': While inspecting the code, I noticed that the position of the '@' in the game was similar to the code snippet provided:

```c
puts("You win!");
if (local_aa4 != '\0') {
  puts("flage");
  win();
  fflush(stdout);
}
```

The next line checks whether a character variable `local_aa4` is not equal to the null character (`'\0'`). If it is not null, it executes the following code block:

- `puts("flage");` outputs the string "flage" to the standard output.
- `win();` calls a function named `win()`. Presumably, this function performs some actions related to winning the game.
- `fflush(stdout);` flushes any buffered output to the standard output.

3. Input the Solution: Using this information, I decided to input the solution by typing `w,w,w,w,a,a,a,a,a,a,a,a` to move the character to the top row and -4 back. Finally, I pressed `p` to get the flag.

4. Got the Flag: After inputting the solution, I was able to get the flag which was:

```
picoCTF{gamer_m0d3_enabled_0a880baf}
```

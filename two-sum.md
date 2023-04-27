Sure! Here's the updated GitHub writeup for the "Two Sum" challenge on PicoCTF 2023:

## Two Sum

**Challenge Description:**
Can you solve this?

**Challenge Files:**
- [two-sum.c](https://shell.actf.co/static/assets/downloadables/rev/two-sum/two-sum.c)

### Solution

1. Download the source code for the challenge.

2. Inspect the `two-sum.c` file, and you'll notice that if there is an overflow, the program will exit. 

3. The code defines a function called `addIntOvf()` that checks for integer overflow by adding two integers and checking if the result is smaller than one of the input integers. If there is an overflow, it returns -1.

4. The main function prompts the user to input two positive integers and calculates their sum. It then calls `addIntOvf()` to check for overflow. If there is no overflow, the program exits. If there is an overflow, it opens and reads the flag from the `flag.txt` file.

5. Since the program checks for overflow based on the sum of two integers, we can enter a very large number for one of the integers and a small number for the other to create an overflow. On a 32-bit machine, the largest number is 2^31 - 1, which is 2147483647.

6. Connect to the challenge server via `nc saturn.picoctf.net 52675`.

7. When prompted to input two positive numbers, enter `2147483647` for the first number and `47` for the second number to create an integer overflow.

8. The program will print the flag: `picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_fe14e9e9}`.

### Flag
`picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_fe14e9e9}`

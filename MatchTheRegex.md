# PicoCTF2023 Writeup: MatchTheRegex

## Challenge Description

The challenge is called "MatchTheRegex" and the description reads, "How about trying to match a regular expression".

## Solution

1. Launch the instance.

2. Inspect the website and find the function `send_request()` in the webpage source code. It contains the following regular expression: `^p.....F!?`.

3. Note that the regular expression expects a string starting with `p`, followed by 5 any characters, and ending with `F!`.

4. Enter the string `picoCTF` in the input field.

5. This will create an alert in your browser with the flag:
   ```
   picoCTF{succ3ssfully_matchtheregex_f89ea585}
   ```


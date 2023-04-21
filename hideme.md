

# PicoCTF2023 Writeup: hideme

## Challenge Description

The challenge is called "hideme" and the description reads, "Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye".

## Solution

1. Download the file, `flag.png`.

2. Open the file and see that it only contains the PicoCTF logo.

3. Use `binwalk` command to extract any hidden files: 
   ```
   $ binwalk flag.png
   ```
   This reveals that there is an `e: secret/` directory and some zip archives.

4. Extract these files using:
   ```
   $ binwalk -e flag.png
   ```
   This creates a new directory named `_flag.png.extracted`.

5. Enter the extracted directory using:
   ```
   $ cd _flag.png.extracted
   ```

6. Navigate to the `secret` directory:
   ```
   $ cd secret
   ```

7. Use the `ls` command to see that there is a file called `flag.png`.

8. Open that file to retrieve the flag:
   ```
   $ open flag.png
   ```

The flag is: 
```
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_cda72af0}
```

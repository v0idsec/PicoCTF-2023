# PicoCTF2023 Writeup: HideToSee

## Challenge Description

The challenge is called "HideToSee" and the description reads, "How about some hide and seek heh?".

## Solution

1. Download the file `atbash.jpg`.

2. Open the file and see that it is a cipher for atbash.

3. Use `steghide` command to extract any hidden files. `steghide` is a steganography program that is used to hide data in various kinds of images and audio files.
   ```
   $ steghide extract -sf atbash.jpg
   ```
   This command extracts any hidden files from the image file.

4. This will create a file called `encrypted.txt`.

5. Open the `encrypted.txt` file in a text editor. 
   ```
   $ subl encrypted.txt
   ```
   This reveals a string of seemingly random characters with the same format as the flag (picoCTF{xxx_xxx_xxx}):
   ```
   krxlXGU{zgyzhs_xizxp_7142uwv9}
   ```

6. Use an online cipher tool, such as https://www.boxentriq.com/code-breaking/atbash-cipher, to decode the atbash cipher. this leaves us with the flag:
   ```
   picoCTF{atbash_crack_7142fde9}
   ```




# GitHub CTF Writeup: PicoCTF2023 Challenge - Rotation

## Challenge Description
You will find the flag after decrypting this file

## Process
To solve this challenge, I followed these steps:

1. I downloaded the `encrypted.txt` file to my local machine.
2. I opened the file using the `nano` command, and found the following encrypted text:
```
xqkwKBN{z0bib1wv_l3kzgxb3l_555957n3}
```
3. Since the encrypted text seemed to be a ROT cipher, I used the `dcode.fr` website to brute force the encryption by trying all possible rotations of the alphabet.
4. After trying multiple rotations, I finally found the flag on the `a-z+8` rotation, which revealed the flag:
```
picoCTF{r0tat1on_d3crypt3d_555957f3}
```

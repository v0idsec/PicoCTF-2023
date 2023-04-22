

# GitHub CTF Writeup: PicoCTF2023 Challenge - Safe Opener 2

## Challenge Description
The `Safe Opener 2` challenge requires you to retrieve the lost key to unlock the safe. You have been provided with a file named `SafeOpener.class`, which is supposed to help you retrieve the lost key.

## Process
To solve this challenge, I followed these steps:

1. I downloaded the `SafeOpener.class` file.
2. I opened the file using a Java decompiler called `jd-gui` by running the command `jd-gui SafeOpener.class`.
3. The Java decompiler revealed the flag within the file, which was:
```
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_3dae8463}
```

## Flag
The flag for the `Safe Opener 2` challenge is:
```
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_3dae8463}
```

# PicoCTF2023 Writeup: money-ware

## Challenge Description

The challenge is called "money-ware". The flag format is `picoCTF{Malwarename}`, and the first letter of the malware name should be capitalized, and the rest lowercase. Your friend got hacked and was asked to pay some bitcoins to `1Mz7153HMuxXTuR2R1t78mGSdzaAtNbBWX`. He doesn’t seem to understand what is going on and asks you for advice. Can you identify what malware he’s a victim of?

## Solution

1. Enter the Bitcoin wallet `1Mz7153HMuxXTuR2R1t78mGSdzaAtNbBWX` into a search engine.

2. Search for information about malware that uses this Bitcoin wallet as a payment address.

3. After researching, we find out that the Bitcoin wallet `1Mz7153HMuxXTuR2R1t78mGSdzaAtNbBWX` is associated with the Petya malware.

4. The flag format requires that the first letter of the malware name be capitalized, and the rest lowercase. Therefore, the flag is:
   ```
   picoCTF{Petya}
   ```

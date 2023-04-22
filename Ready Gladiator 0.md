Sure, here's the updated GitHub markdown syntax:

# CTF Writeup: Ready Gladiator 0

## Challenge Description
The challenge was to create a CoreWars warrior that always loses with no ties. The opponent was "Imp". The source code was provided and it was required to download the Imp and connect to the CoreWars server.

## CoreWars
CoreWars is a programming game where two or more programs run in a simulated computer (Mars) memory called "Core." Each program tries to eliminate its opponent by overwriting their code with its own. The last program running is the winner.

## Solution
1. Download the source file.
2. Modify the `imp.red` file by changing `mov` to `dat`. The modified `imp.red` code:
    ```redcode
    ;redcode
    ;name Imp Ex
    ;assert 1
    dat 0, 1
    end
    ```
3. Connect to the CoreWars server using the `nc` command: `nc saturn.picoctf.net 62815 < imp.red`.
4. Submit the modified `imp.red` file.
5. The result showed that the modified warrior always loses.
```
;redcode
;name Imp Ex
;assert 1
dat 0, 1
end
Submit your warrior: (enter 'end' when done)

Warrior1:
;redcode
;name Imp Ex
;assert 1
dat 0, 1
end

Rounds: 100
Warrior 1 wins: 0
Warrior 2 wins: 100
Ties: 0
You did it!
picoCTF{h3r0_t0_z3r0_4m1r1gh7_e1610ed2}
```


## Flag
The flag was:
```
picoCTF{h3r0_t0_z3r0_4m1r1gh7_e1610ed2}
```


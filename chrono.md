# PicoCTF 2023: Challenge "chrono"

This challenge explores the topic of automating tasks to run at intervals on Linux servers. The task is to use SSH to connect to the provided server and find the flag by navigating to the crontab.

## Challenge Details

- **Challenge Name:** chrono
- **Description:** How to automate tasks to run at intervals on Linux servers?
- **SSH Connection Details:**
  - Server: saturn.picoctf.net
  - Port: 59194
  - Username: picoplayer
  - Password: a-8nJGZCTa

## Solution

To start the challenge, I used the following command to log in to the provided server:

```
ssh picoplayer@saturn.picoctf.net -p 59194
```

After entering the correct password, I searched for the crontab. In case you don't know what crontab is, it is a file that contains a list of commands that will be executed automatically on a schedule. To navigate to the crontab, I used the following command:

```
cat /etc/crontab
```

This command allowed me to see the contents of the crontab file, which in turn contained the flag:

```
picoCTF{Sch3DUL7NG_T45K3_L1NUX_7754e199}
```

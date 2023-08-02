# PicoCTF 2023 Challenge Writeup: Email Origin

### Challenge Description:
You receive an email that claims to be from Google's co-founder, Larry Page, but you are suspicious that it might be a scam. Your task is to investigate the email file and identify the mail server from which the email actually originated. Can you help us uncover the truth? Download the email file [here](https://artifacts.picoctf.net/c/499/email-export.eml). The flag format is `picoCTF{FirstnameLastname}`.

### Challenge Steps:

1. **Download the Challenge File:**
Start by downloading the challenge file `email-export.eml`. You can use the `wget` command in the terminal to download it:
```bash
wget https://artifacts.picoctf.net/c/499/email-export.eml
```

2. **Inspect the File:**
Open the downloaded file with a text editor like Sublime Text to analyze its contents:
```bash
subl email-export.eml
```

3. **Find the Origin Mail Server:**
Carefully inspect the lines of the email file to find information about the mail server from which the email was sent.

4. **Extract the Flag:**
The flag format is `picoCTF{FirstnameLastname}`, meaning the flag will be in the format `picoCTF{}` followed by the first name and last name of the mail server's owner.

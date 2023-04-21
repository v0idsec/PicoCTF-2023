Sure, here's the same write-up formatted like the one you provided:

# PicoCTF 2023 Challenge: findme

## Description
Help us test the form by submiting the username as test and password as test!

## Steps Taken
1. Visited the Website: I visited the website provided and entered "test" as both the username and password.

2. Inspected the Network Tab: Before submitting, I opened the network tab in my browser to see if any requests were being made. As soon as I clicked submit, the network tab flashed, indicating that I was being redirected to another page. This was the first hint that the flag might be hidden in the subsequent requests.

3. Used Burp Suite: Next, I opened the site in Burp Suite, intercepted the request, and clicked forward one request at a time.

4. Found the Flag: In the second request, I found a GET request to 
```
/next-page/id=cGljb0NURntwcm94aWVzX2Fs
```

I decoded the string `cGljb0NURntwcm94aWVzX2Fs` from base64, which gave me the first half of the flag, `picoCTF{proxies_al`.

Going one step further and intercepting the third request, I found a GET request to 
```
/next-page/id=bF90aGVfd2F5XzAxZTc0OGRifQ
```

Decoding the string `bF90aGVfd2F5XzAxZTc0OGRifQ` gave me the second half of the flag, `l_the_way_01e748db}`.

5. Got the Flag: Putting it all together, the flag for this challenge was 

```
picoCTF{proxies_all_the_way_01e748db}`.
```

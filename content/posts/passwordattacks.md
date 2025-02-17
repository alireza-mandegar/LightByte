+++
date = '2025-02-17T13:45:19+03:30'
draft = false
title = 'Passwordattacks'
+++

# Password Attacks

### PASSWORD SPRAY

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/cad4c73462916cb67e69c2eb50fd9dcdca59cfbe.png)

This technique attempts to gain access to a system by ‘spraying’ a few commonly used passwords across a large number of accounts. For example, a cybercriminal uses 'Password123' with many usernames before trying again with a second commonly-used password, such as ‘qwerty.’

This technique allows the perpetrator to remain undetected as they avoid frequent account lockouts.

### DICTIONARY ATTACKS

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/cd79e882e9efe6d568118ae43f447a500c9955d6.png)

A hacker systematically tries every word in a dictionary or a list of commonly used words as a password in an attempt to break into a password-protected account.

### BRUTE-FORCE ATTACKS

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/d62ba4eb77ce4f60c69a8c5c2c843de3fa7ac769.png)

The simplest and most commonly used way of gaining access to a password-protected site, brute-force attacks see an attacker using all possible combinations of letters, numbers and symbols in the password space until they get it right.

### RAINBOW ATTACKS

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/34a110cd33e1aeac5108f201e497706b546fccb9.png)

Passwords in a computer system are not stored as plain text, but as hashed values (numerical values that uniquely identify data). A rainbow table is a large dictionary of precomputed hashes and the passwords from which they were calculated.

Unlike a brute-force attack that has to calculate each hash, a rainbow attack compares the hash of a password with those stored in the rainbow table. When an attacker finds a match, they identify the password used to create the hash.

### TRAFFIC INTERCEPTION

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/11ccc1f6f9152fb001ad44a4b7e1ea3586c15d68.png)

Plain text or unencrypted passwords can be easily read by other humans and machines by intercepting communications.

If you store a password in clear, readable text, anyone who has access to your account or device, whether authorized or unauthorized, can read it.

---
title: Crack the hash: TryHackMe
description: cracking hashes challenges
image: https://tryhackme.com/img/banners/default_tryhackme.png
author: 'Andrews Boateng Okyere'
publishedAt: 28/08/2023,
tags: 'john the ripper, hashcat, rockyou, hashcat'
---

Basically cracking the hashes

## Task 1
Answer the questions below
(repeat step 1 for all the questions except for number 3)

1. 48bb6e862e54f2a795ffc4e541caed4d
using [crackstation.net](crackstation.net) we find the hash is md5 and get the result below
```
easy
```
2. CBFDAC6008F9CAB4083784CBD1874F76618D2A97 
repeat the same process
```sh
password123
```

3. $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom
We will use hashcat, it is pre-installed on kali linux.


create a file called hash and paste the hashed text in it
### Identify the hash type
Try 
[online](https://www.onlinehashcrack.com/hash-identification.php)

```sh
hashid -m hash
```
##### results
<pre>
--File 'hash'--
Analyzing '$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom'
[+] Blowfish(OpenBSD) [Hashcat Mode: 3200]
[+] Woltlab Burning Board 4.x 
[+] bcrypt [Hashcat Mode: 3200]
--End of file 't1_4'--  
</pre>

### Crack
```sh
hashcat -m 3200 -a 0 hash /usr/share/wordlists/rockyou.txt
```
-m for to  hash type and -a for the attack mode. Go to [here](https://hashcat.net/wiki/doku.php?id=hashcat) and [here](https://hashcat.net/wiki/doku.php?id=example_hashes) for more information

##### result
```sh
bleh

```

4. Try it on your own


##

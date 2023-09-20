---
title: Crack the hash - TryHackMe
description: cracking hashes challenges
image: https://tryhackme.com/img/banners/default_tryhackme.png
author: 'Andrews Boateng Okyere'
publishedAt: 28/08/2023,
tags: 'john the ripper, hashcat, rockyou, hashcat'
---

::cy-sources
---

items: [
  {
    label: 'TryHackMe',
    to: "https://tryhackme.com/room/crackthehash"
  }
]
---

::

## Description

Basically cracking the hashes provided by tryhackme

## Task 1: Level 1

Answer the questions below

(repeat the process of step 1 for all the questions except for number 3)

 **1. 48bb6e862e54f2a795ffc4e541caed4d**
using [crackstation.net](crackstation.net) we find the hash is md5 and get the result below

```
easy
```

**2. CBFDAC6008F9CAB4083784CBD1874F76618D2A97**
repeat the same process

```sh
password123
```

**3. $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom**
We will use hashcat, it is pre-installed on kali linux.

create a file called hash and paste the hashed text in it
**Identify the hash type**
You can first try to identify the hash type with this
[online](https://www.onlinehashcrack.com/hash-identification.php) resource.

Identify hash type using cmd

```sh
hashid -m hash
```

**results**
<pre>
--File 'hash'--
Analyzing '$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom'
[+] Blowfish(OpenBSD) [Hashcat Mode: 3200]
[+] Woltlab Burning Board 4.x
[+] bcrypt [Hashcat Mode: 3200]
--End of file 't1_4'--  
</pre>

 **Crack**

```sh
hashcat -m 3200 -a 0 hash /usr/share/wordlists/rockyou.txt
```

-m for to  hash type and -a for the attack mode. Go to [here](https://hashcat.net/wiki/doku.php?id=hashcat) and [here](https://hashcat.net/wiki/doku.php?id=example_hashes) for more information

**result**

```sh
bleh

```

1. Try it on your own

## Task 2: Level 2

Instruction

This task increases the difficulty. All of the answers will be in the classic [rock you](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt) password list.

You might have to start using hashcat here and not online tools. It might also be handy to look at some example hashes on [hashcats page](https://hashcat.net/wiki/doku.php?id=example_hashes).

 Answer the questions below

**Hash: F09EDCB1FCEFC6DFB23DC3505A882655FF77375ED8AA2D1C13F640FCCC2D0C85**
**Answer:**
We want to use john the ripper this time around.

- Identify hash type: Mostly, you will get a lot of possible options for the result. It is at your discretion to choose which one  to start with and try cracking the hashed text. You can also try **hash-identifier**

```sh
hashid -j hash1
```

Our hash is in file hash1. Notice we -j instead of -m, this is so we get the format specified for john the ripper. if you use -m, you get the format in hashcat mode. Ok then,

- Crack it

```sh
john --wordlist=/usr/share/wordlists/rockyou.txt --format=Raw-SHA256
```

**Final results**

```md
paule
```

**Hash: 1DFECA0C002AE40B8619ECF94819CC1B**
Try this on your own with the above steps.
Expected result

```sh
n63umy8lkf4i
```

**Hash: $6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.**
salt: Salt: aReallyHardSalt

**Answer:**

- Identify hash type: We already know salt was used to make the hash more difficult to crack. We will be using hashcat for this question
Running hashid, we already have an idea that it is sha512crypt.

```sh
hashcat -m 1800 -a 0 hash3 /usr/share/wordlists/rockyou.txt
```

###### Expected result

```sh
waka99
```

**Try Hash: e5d8870e5bdd26602cab8dbe07a942c8669e56d6**

Salt: tryhackme

**Expected result:**

```sh
481616481616
```

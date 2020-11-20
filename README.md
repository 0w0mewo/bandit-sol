##### My Bandit wargame solution

###### Level 0 solution

```bash
ssh -2 -p 2220 bandit0@bandit.labs.overthewire.org
```

Flag:

```
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```



###### Level 1 solution

```bash
cat ./-
```

Flag:

```
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```



###### Level 2 solution

```bash
cat "spaces in this filename"
```

Flag:

```
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```



###### Level 3 solution

```bash
bandit3@bandit:~$ ls  -altr inhere/
total 12
drwxr-xr-x 3 root    root    4096 May  7 20:14 ..
-rw-r----- 1 bandit4 bandit3   33 May  7 20:14 .hidden
drwxr-xr-x 2 root    root    4096 May  7 20:14 .
bandit3@bandit:~$ cat inhere/.hidden 
pIwrPrtPN36QITSp3EQaw936yaFoFgAB

```

Flag:

```
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```



###### Level 4 solution

```bash
for f in $(find ./inhere); do echo $f && awk '{print}' $f; done
```

Flag:

```
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```



###### Level 5 solution

```bash
find ./inhere/ -readable -size 1033c -not -executable -exec cat {} +
```

Flag:

```
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```



###### Level 6 solution

```bash
cat $(find / -group bandit6 -user bandit7 2>/dev/null)
```

Flag:

```
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```



###### Level 7 solution

```bash
awk '/millionth/{ print }' data.txt
```

Flag:

```
cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```



###### Level 8 solution

```bash
cat data.txt | sort | uniq -u
```

Flag:

```
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```



###### Level 9 solution

```bash
strings data.txt | grep =
```

Flag:

```
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```



###### Level 10 solution

```bash
base64 -d < data.txt
```

Flag:

```
IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```



###### Level 11 solution

```bash
str=$(cat data.txt); python3 -c "import codecs; s = '$str'; print(codecs.decode(s, 'rot13'))"
```

Flag:

```
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```



###### Level 12 solution

```bash
xxd -r data.txt | gzip -d | bzip2 -d | gzip -d | tar -xO| tar -xO | bzip2 -d | tar -xO | gzip -d 
```

Flag:

```
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```



###### Level 13 solution

```bash
ssh -i sshkey.private -l bandit14 -t 127.0.0.1 'cat /etc/bandit_pass/bandit14'
```

Flag:

```
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```



###### Level 14 solution

```bash
echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc 127.0.0.1 30000
```

Flag:

```
BfMYroe26WYalil77FoDi9qh59eK5xNr
```



###### Level 15 solution

```bash
echo BfMYroe26WYalil77FoDi9qh59eK5xNr | openssl s_client -quiet -connect 127.0.0.1:30001
```

Flag:

```bash
cluFn7wTiGryunymYOu4RcffSxQluehd
```



###### Level 16 solution

```
nmap -p 31000-32000 --script ssl-enum-ciphers 127.0.0.1
```

Output:

```
bandit16@bandit:~$ nmap -p 31000-32000 --script ssl-enum-ciphers 127.0.0.1

Starting Nmap 7.40 ( https://nmap.org ) at 2020-10-26 10:09 CET
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00027s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
| ssl-enum-ciphers: 
|   TLSv1.0: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|   TLSv1.1: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|   TLSv1.2: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|_  least strength: A
31691/tcp open  unknown
31790/tcp open  unknown
| ssl-enum-ciphers: 
|   TLSv1.0: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|   TLSv1.1: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|   TLSv1.2: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors: 
|       NULL
|     cipher preference: client
|     warnings: 
|       Weak certificate signature: SHA1
|_  least strength: A
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 1.45 seconds
```

It turns out that port 31790 is the one we need.

Then:

```
echo cluFn7wTiGryunymYOu4RcffSxQluehd | openssl s_client -quiet -connect 127.0.0.1:31790
```

Flag:

The flag is a SSH private key

```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```



###### Level 17 solution

```bash
diff passwords.new passwords.old
```

Flag:

```bash
kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```



###### Level 18 solution

```bash
ssh -t -2 -p 2220 bandit18@bandit.labs.overthewire.org cat ./readme
```

Flag:

```
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```



###### Level 19 solution

```bas
./bandit20-do cat /etc/bandit_pass/bandit20
```

Flag:

```
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```


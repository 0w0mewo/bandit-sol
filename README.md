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




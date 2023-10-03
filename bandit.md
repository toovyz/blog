# Level 0 → 1
Run: `ssh bandit0@bandit.labs.overthewire.org -p 2220`.
Enter password: bandit0.
![image](https://github.com/toovyz/blog/assets/90684283/9cab98dd-703b-40fc-a223-e44d64834ae7)
Flag: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
# Level 1 → 2 
Run: `ssh bandit1@bandit.labs.overthewire.org -p 2220`.
Enter password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL.
![image](https://github.com/toovyz/blog/assets/90684283/00ef0e05-728a-485d-8529-27035c72c0d0)
Flag: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
# Level 2 → 3
Run: `ssh bandit2@bandit.labs.overthewire.org -p 2220`.
Enter password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi.
![image](https://github.com/toovyz/blog/assets/90684283/f670f5c2-4782-4df6-8b8c-624e9479ad31)
Flag: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG.
# Level 3 → 4
Run: `ssh bandit3@bandit.labs.overthewire.org -p 2220`.
Enter password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG.
![image](https://github.com/toovyz/blog/assets/90684283/9f52108f-4dc4-45c8-9c36-dc8d0f5a7665)
Flag: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe.
# Level 4 → 5
Run: `ssh bandit4@bandit.labs.overthewire.org -p 2220`.
Enter password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe.
![image](https://github.com/toovyz/blog/assets/90684283/820b7c76-b8b4-4308-bc56-80377ee25fdb)
Flag: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR.
# Level 5 → 6
Run: `ssh bandit5@bandit.labs.overthewire.org -p 2220`.
Enter password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR.
![image](https://github.com/toovyz/blog/assets/90684283/c8484436-f8a7-4dc2-8233-9f45692d3bf8)
Flag: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU.
# Level 6 → 7
Run: `ssh bandit6@bandit.labs.overthewire.org -p 2220`.
Enter password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU.
```
bandit6@bandit:/$ find / -type f -size 33c -user bandit7 -group bandit6 2>>dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:/$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vz
```
Flag: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S.
# Level 7 → 8
Run: `ssh bandit7@bandit.labs.overthewire.org -p 2220`.
Enter password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S.
```
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
Flag: TESKZC0XvTetK0S9xNwm25STk5iWrBvP.
# Level 8 → 9
Run: `ssh bandit8@bandit.labs.overthewire.org -p 2220`.
Enter password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP.
```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
``` 
Flag: EN632PlfYiZbn3PhVK3XOGSlNInNE00t.
# Level 9 → 10
Run: `ssh bandit9@bandit.labs.overthewire.org -p 2220`.
Enter password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t.
```
bandit9@bandit:~$ strings data.txt | grep "="
``` 
Flag: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s.
# Level 10 → 11
Run: `ssh bandit10@bandit.labs.overthewire.org -p 2220`.
Enter password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s.
```
bandit10@bandit:~$ base64 -d data.txt
``` 
Flag: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM.
# Level 11 → 12
Run: `ssh bandit11@bandit.labs.overthewire.org -p 2220`.
Enter password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM.
```
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
``` 
Flag: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv.
Được thực hiện bởi: https://mayadevbe.me/posts/overthewire/bandit/level12/.
# Level 12 → 13
Run: `ssh bandit12@bandit.labs.overthewire.org -p 2220`.
Enter password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv.
```
bandit12@bandit:~$ mkdir /tmp/level1213
bandit12@bandit:~$ cd /tmp/level1213
bandit12@bandit:/tmp/level1213$ cp ~/data.txt .
bandit12@bandit:/tmp/level1213$ xxd -r data.txt > data.gz
bandit12@bandit:/tmp/level1213$ gzip -d data.gz
bandit12@bandit:/tmp/level1213$ bzip2 -d data
bzip2: Can't guess original name for data -- using data.out
bandit12@bandit:/tmp/level1213$ mv data.out data4.gz
bandit12@bandit:/tmp/level1213$ gzip -d data4.gz
bandit12@bandit:/tmp/level1213$ tar xfv data4
bandit12@bandit:/tmp/level1213$ tar xfv data5.bin
bandit12@bandit:/tmp/level1213$ bzip2 -d data6.bin
bandit12@bandit:/tmp/level1213$ tar xfv data6.bin.out
bandit12@bandit:/tmp/level1213$ mv data8.bin data8.gz
bandit12@bandit:/tmp/level1213$ gzip -d data8.gz
bandit12@bandit:/tmp/level1213$ cat data8
``` 
Flag: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw.
Được thực hiện bởi: https://burakb.net/writeup/overthewire-bandit-level-12-level-13/.
# Level 13 → 14
Run: `ssh bandit13@bandit.labs.overthewire.org -p 2220`.
Enter password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw.
```
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
``` 
# Level 14 → 15
Run: `ssh bandit14@bandit.labs.overthewire.org -p 2220`.
Enter password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq.
```
bandit14@bandit:~$ nc localhost 30000
``` 
# Level 15 → 16
Run: `ssh bandit15@bandit.labs.overthewire.org -p 2220`.
Enter password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq.
```

``` 

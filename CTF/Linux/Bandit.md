# Bandit

## Level 0

> commands
ssh  bandit0@bandit.labs.overthewire.org -p 2220

> password

```bash
bandit0
```

## Level 0-1

> commands
ssh  bandit1@bandit.labs.overthewire.org -p 2220
ls  - list all files
cat - read a file

> password

```bash
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

## Level 1-2    

> commands
ssh  bandit2@bandit.labs.overthewire.org -p 2220
ls  - list all files
cat - read a file

> password 

```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

## Level 2-3

> commands
ssh  bandit3@bandit.labs.overthewire.org -p 2220
cat "./--spaces in this filename--"

> password

```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

```

## Level 3-4

> commands

ssh  bandit4@bandit.labs.overthewire.org -p 2220
ls  - list all files
cat inhere ---cat: inhere: Is a directory
cd inhere ---cd: inhere: Is a directory
ls -a  - list all files, including hidden ones
cat ...Hiding-From-You

> password

```bash
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

## Level 4-5

> commands

ssh  bandit5@bandit.labs.overthewire.org -p 2220
cd inhere
pwd -- print working directory
ls - list all files
file ./* --- list all files
./-file07

> password

```bash
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

## Level 5-6

> commands

ssh  bandit6@bandit.labs.overthewire.org -p 2220
cd inhere
pwd
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2

> password

```bash
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

## Level 6-7

> commands

ssh  bandit7@bandit.labs.overthewire.org -p 2220
cd / --- root directory
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
We will use:

/ → search entire system

-type f → files only

-user bandit7 → owned by bandit7

-group bandit6 → group bandit6

-size 33c → exactly 33 bytes (c = bytes)

2>/dev/null → hide permission errors (VERY important)

cat /var/lib/dpkg/info/bandit7.password

> password

```bash
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
## Level 7-8

> commands

ssh  bandit8@bandit.labs.overthewire.org -p 2220
ls
grep millionth data.txt

What this does:

grep → searches text

millionth → word to search

data.txt → file to search in

> password
```bash
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
## Level 8-9

> commands

ssh  bandit9@bandit.labs.overthewire.org -p 2220
sort data.txt
sort data.txt | uniq -u

sort → groups same lines together

uniq -u → shows only lines that appear once

| → passes output from one command to another

> password

```bash
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
## Level 9-10

> commands

ssh  bandit10@bandit.labs.overthewire.org -p 2220
strings data.txt | grep "==="

strings data.txt → gets readable lines

| → sends them forward

grep "===" → filters only lines with ===

> password

```bash
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## Level 10-11

> commands

ssh  bandit11@bandit.labs.overthewire.org -p 2220

cat data.txt //This confirms it is Base64, not normal text.//

base64 -d data.txt

base64 // Tool used to encode or decode Base64 data//

-d // Means decode //

data.txt // File containing encoded data //

> password

```bash

dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

## Level 11-12

> commands

ssh  bandit12@bandit.labs.overthewire.org -p 2220

cat data.txt  //You’ll see something unreadable — that’s ROT13 text.//

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

cat data.txt // Reads the file content //
| // Pipe: sends output of one command to another //
tr 'A-Za-z' 'N-ZA-Mn-za-m' // Translates letters using ROT13: 
                             // 'A-Za-z' = all uppercase & lowercase letters 
                             // 'N-ZA-Mn-za-m' = rotate each letter by 13 positions 
                             // A->N, B->O, ..., Z->M; a->n, b->o, ..., z->m //

> password

```bash
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
## Level 12-13

> commands

ssh  bandit13@bandit.labs.overthewire.org -p 2220

WORKDIR=$(mktemp -d)        // Creates a temporary working directory //
cd $WORKDIR                // Moves into the temp directory //

cp ~/data.txt .            // Copies the given hexdump file to work safely //

xxd -r data.txt > file     // Reverses the hexdump back to original binary //

file file                  // Checks the file type (gzip) //

mv file file.gz            // Renames file to .gz so gunzip can read it //
gunzip file.gz             // Decompresses gzip file //

file file                  // Checks next compression type (bzip2) //

mv file file.bz2           // Renames file to .bz2 //
bunzip2 file.bz2           // Decompresses bzip2 file //

file file                  // Checks file type (tar archive) //

mv file file.tar            // Renames file to .tar //
tar -xf file.tar            // Extracts tar archive //

file data5.bin             // Checks extracted file type (tar) //

mv data5.bin data5.tar     // Renames to tar //
tar -xf data5.tar          // Extracts tar archive //

file data6.bin             // Checks file type (bzip2) //

mv data6.bin data6.bz2     // Renames to bzip2 //
bunzip2 data6.bz2          // Decompresses bzip2 file //

file data6                 // Checks file type (tar archive) //

mv data6 data6.tar         // Renames to tar //
tar -xf data6.tar          // Extracts tar archive //

file data8.bin             // Checks file type (gzip) //

mv data8.bin data8.gz      // Renames to gzip //
gunzip data8.gz            // Decompresses gzip file //

file data8                 // Confirms ASCII text (final password file) //

cat data8                  // Displays password for Bandit Level 13 //


> password

```bash
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

```

## Level 13-14

> commands

ssh  bandit14@bandit.labs.overthewire.org -p 2220
exit // log out first
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14 

> password

```bash
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

## Level 14-15

> commands

ssh  bandit15@bandit.labs.overthewire.org -p 2220
nc localhost 30000
//nc → netcat tool (connect to ports)
localhost → your own machine
30000 → port number//
It will just wait.
 Now paste the bandit14 password
 Press Enter

> password

```bash
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

## Level 15-16

> commands

ssh  bandit16@bandit.labs.overthewire.org -p 2220
openssl s_client -connect localhost:30001

openssl → cryptography tool
s_client → SSL client mode
-connect → connect to server

> password

```bash
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

## Level 16-17

> commands

ssh  bandit17@bandit.labs.overthewire.org -p 2220
nmap -p 31000-32000 localhost
openssl s_client -connect localhost:PORT
<bandit16_password>
nano key17
chmod 600 key17
ssh -i key17 bandit17@bandit.labs.overthewire.org -p 2220

> password

```bash
BMIOFKM7CRSLI97voLp3TD80NAq5exxk
```

## Level 17-18

> commands

ssh  bandit18@bandit.labs.overthewire.org -p 2220
ls
diff passwords.old passwords.new



> password

```bash
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

## Level 18-19

> commands

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme //- This will connect, run cat readme, and print the contents (the password) before disconnecting.
//
ssh  bandit19@bandit.labs.overthewire.org -p 2220

> password

```bash
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

## Level 19-20

> commands

ssh  bandit20@bandit.labs.overthewire.org -p 2220

ls -l
./bandit20-do
./bandit20-do cat /etc/bandit_pass/bandit20

> password

```bash
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

## Level 20-21

> commands

ssh  bandit21@bandit.labs.overthewire.org -p 2220
echo -n '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -l -p 1234 &
./suconnect 1234

> password

```bash
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

## Level 21-22

> commands

ssh  bandit22@bandit.labs.overthewire.org -p 2220
ls /etc/cron.d/
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/some_random_filename

> password

```bash
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

## Level 22-23

> commands

ssh  bandit23@bandit.labs.overthewire.org -p 2220
ls /etc/cron.d/
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
echo I am user bandit23 | md5sum
cat /tmp/8ca319486bfbbc3663ea0fbe81326349

> password

```bash
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

## Level 23-24

> commands

ssh  bandit24@bandit.labs.overthewire.org -p 2220
cd /etc/cron.d/
ls -l
cat cronjob_bandit24
cat /usr/bin/cronjob_bandit24.sh
cd /var/spool/bandit24/foo/
echo '#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/bandit23_pw.txt' > myscript.sh
chmod +x myscript.sh
cat /tmp/bandit23_pw.txt

> password

```bash
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

## Level 24-25

> commands

ssh  bandit25@bandit.labs.overthewire.org -p 2220
for i in $(seq -w 0000 9999); do
    echo "$(cat /etc/bandit_pass/bandit24) $i"
done | nc localhost 30002

> password

```bash
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

## Level 25-26

> commands

ssh  bandit26@bandit.labs.overthewire.org -p 2220

> password

```bash
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

## Level 26-27

> commands

ssh  bandit27@bandit.labs.overthewire.org -p 2220
ls
text.txt
file bandit27-do
./bandit27-do whoami
./bandit27-do cat /etc/bandit_pass/bandit27
> password

```bash
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

## Level 27-28

> commands

ssh  bandit28@bandit.labs.overthewire.org -p 2220
mkdir /tmp/bandit27repo
cd /tmp/bandit27repo
GIT_SSH_COMMAND='ssh -i sshkey.private -p 2220' git clone ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo
cd repo
ls -la
cat README
> password

```bash
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

## Level 28-29

> commands

ssh  bandit29@bandit.labs.overthewire.org -p 2220
mkdir /tmp/bandit28repo
cd /tmp/bandit28repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit28-git@bandit.labs.overthewire.org/home/bandit28-git/repo
cd repo
ls -la
cat README
git log
git show <commit-hash>
git log -p

> password

```bash
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

## Level 29-30

> commands

ssh  bandit30@bandit.labs.overthewire.org -p 2220
mkdir /tmp/bandit29repo
cd /tmp/bandit29repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo
cd repo
ls -la
cat README.md
git branch -a
git checkout dev
cat README.md

> password

```bash
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

## Level 30-31

> commands

ssh  bandit31@bandit.labs.overthewire.org -p 2220
mkdir /tmp/bandit30repo
cd /tmp/bandit30repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo
cd repo
ls -la
cat README.md
git tag
git show secret //secret --tag name--//

> password

```bash
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

## Level 31-32

> commands

ssh  bandit32@bandit.labs.overthewire.org -p 2220
mkdir /tmp/bandit31repo
cd /tmp/bandit31repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo
cd repo
echo "May I come in?" > key.txt
git add -f key.txt
git config user.email "bandit31@example.com"
git config user.name "Bandit Player"
git commit -m "Add key.txt with required content"
GIT_SSH_COMMAND='ssh -p 2220' git push origin master


> password

```bash
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

## Level 32-33

> commands

ssh  bandit33@bandit.labs.overthewire.org -p 2220
WELCOME TO THE UPPERCASE SHELL
>>(To exit from this shell use  $0)
cat /etc/bandit_pass/bandit33
Again login as bandit33

> password

```bash
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

## Level 33 - 34

Congratulations cmpltd
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



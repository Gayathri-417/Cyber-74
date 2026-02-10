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




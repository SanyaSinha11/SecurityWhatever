Given: URL/Domain

# Pages
- Login Page
- Home Page
- Payment Gateway

## Login Page
1. View Page Source Code
   - Look for hardcoded credentials
   - Secret keys
   - Comments
   - Scripts
   - Endpoints or paths
     
2. Look for the user interactive points, like:
   username, password, forget password, captcha, OTP, etc
   
3. Check for SQLi
   Try payloads
    If CSRF token is present then `BruteForce` cannot be performed
    This can be bypassed by MACRO of Burp Suite
   
4. Authentication
   If you can directly go to another page by parsing the URL 
   
5. Forget Password
   We can check for rate limiting
   Username enumeration - check by entering wrong/attacker username/email
   Change the parameters like email to attacker's email to get otp or reset password.
   
6. OTP Bypass
   Check for ways to perform OTP Bypass apart from Brute Force
   
7. Check for Rate Limiting

## Home Page
1. View Page Source Code
   JS file often contains - API
   
2. Application browsing - information gathering and understanding the platform
   This will also help in polluting the Target of Burp Suite
   
3. Understand the Input fields, User interaction points, Entry points
   
4. Determine the attack surfaces
   
5. Start with understanding Headers and testing them
   - If the header is required
   - If the values can be changed
   
6. Then move towards the request body
   Manipulate the parameters with the types:
     - SQLi
     - XSS
     - CSRF
     - SSRF
     - Redirects
     - Path Traversal
     - IDOR

## Payment Gateway
1. Amount Manipulation
2. Receiver Manipulation
3. Type/Mode of Payment Manipulation

---
# Questions
1. How will manually pen test a payment gateway page?
2. 
  
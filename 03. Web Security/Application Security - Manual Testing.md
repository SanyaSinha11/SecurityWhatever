# Universal Manual Testing Methodology

Regardless of vulnerability type, start with:
```
1. Browse the application
2. Map functionality
3. Identify inputs
4. Intercept requests in Burp
5. Modify parameters
6. Observe responses
7. Compare behavior
8. Verify impact
```

Always look for:
##### User-controlled inputs
- URL parameters
- POST body parameters
- JSON parameters
- Cookies
- Headers
- File uploads
- Search bars
- Profile fields
- Feedback forms

These are your attack surfaces.

---
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
# Most Common Path to Follow

```
1. XSS
   - Reflected
   - Stored
   - DOM

2. CSRF

3. IDOR

4. File Upload Vulnerabilities

5. Path Traversal

6. SSRF

7. CORS Misconfiguration

8. SSTI

9. Authentication & Session Weaknesses

10. Business Logic Vulnerabilities
```

---
# Questions
1. How will manually pen test a payment gateway page?
2. 
  
### Q1. What is Application Security?
"Application Security is the practice of identifying, preventing, and fixing security vulnerabilities throughout the software development lifecycle. It includes secure design, secure coding, security testing, vulnerability management, and continuous monitoring to protect applications from attacks."

### Q2. Why do you want to work in Application Security?
"I enjoy understanding how applications work and how attackers can misuse them. Application Security allows me to improve product security proactively rather than reacting after incidents occur."

### Q3. What is OWASP Top 10?
"The OWASP Top 10 is a list of the most critical web application security risks published by the OWASP community. It helps organizations focus on the most common and impactful vulnerabilities."

### Q4. What are the OWASP Top 10 vulnerabilities?

### Q5. Which OWASP vulnerability is most common?
"Broken Access Control is currently considered one of the most common and impactful vulnerabilities because it can allow users to access resources or perform actions they should not be authorized to."

### Q6. What is SQL injection?
"SQL Injection occurs when user input is included in SQL queries without proper validation or parameterization, allowing attackers to modify database queries."
*Example:*
Instead of:
```
SELECT * FROM users WHERE id='1'
```

Attacker sends:
```
1' OR '1'='1
```

### Q7. How do you prevent SQL Injection?
- Parameterized queries
- Prepared statements
- Input validation and sanitization
- Least privilege database accounts
- WAF

### Q8. What is XSS?
"Cross-Site Scripting occurs when attacker-controlled JavaScript executes inside another user's browser."
##### Types
- Reflected XSS
- Stored XSS
- DOM XSS

### Q9. How do you prevent XSS?
- Output encoding
- Input validation
- Content Security Policy (CSP)
- Avoid unsafe JavaScript functions -  using DOM safe methods
- WAF

### Q10. What is CSRF?
"Cross-Site Request Forgery tricks an authenticated user into performing unintended actions."
##### Prevention
- CSRF tokens
- SameSite cookies
- Re-authentication

### Q11. What is SSRF?
"Server-Side Request Forgery occurs when the server makes requests to attacker-controlled destinations."
##### Impact
- Access internal systems
- Access cloud metadata services
- Internal port scanning

### Q12. What is IDOR?
"Insecure Direct Object Reference occurs when users can access resources belonging to other users by changing identifiers."

*Example:*
```
/user/123/profile
```
changing to:
```
/user/124/profile
```

### Q13. Difference between Authentication and Authorization.
Authentication = Who are you?
Authorization = What can you access?

### Q14. What is MFA?
"Multi-Factor Authentication requires multiple verification methods such as password plus OTP."
- What you have?
- What you know?
- What you are?

### Q15. What is JWT?
"JSON Web Token is a signed token used to securely transmit user identity information."
##### Components
- Header
- Payload
- Signature

### Q16. What is OAuth?
"OAuth is an authorization framework that allows users to grant limited access to applications without sharing passwords."

### Q17. Difference between Encryption and Hashing.
Encryption is reversible.
Hashing is one-way.

*Examples:*
Encryption:
- AES
- RSA

Hashing:
- SHA-256
- bcrypt

### Q18. Why should passwords not be encrypted?
"They should be hashed because encryption can be reversed if keys are compromised."

### Q19. How should passwords be stored?
Using:
- bcrypt
- Argon2
- PBKDF2
with salting.

### Q20. What is Secure SDLC?
"Secure SDLC integrates security activities into every stage of software development."
##### Stages
Requirements
→ Design
→ Development
→ Testing
→ Deployment
→ Maintenance

### Q21. Security activities during SDLC?
- Threat modeling
- Secure code review
- SAST
- DAST
- Penetration testing
- Dependency scanning

### Q22. What is SAST?
"Static Application Security Testing analyzes source code without running the application."
*Example:*
Semgrep
SonarQube
Checkmarx

### Q23. What is DAST?
"Dynamic Application Security Testing analyzes a running application."
*Example:*
Burp Suite
OWASP ZAP

### Q24. What is SCA?
"Software Composition Analysis identifies vulnerable third-party dependencies."
*Examples:*
Snyk
Dependabot

### Q25. Difference between SAST and DAST.
| SAST        | DAST        |
| ----------- | ----------- |
| Source code | Running app |
| Early SDLC  | Later SDLC  |
| White-box   | Black-box   |

### Q26. Why use Burp Suite?
"Burp Suite allows interception, modification, replay, and analysis of HTTP requests and responses."

### Q27. Most used Burp modules?
- Proxy
- Repeater
- Intruder
- Decoder
- Comparer

### Q28. What is Repeater and Intruder?
**Repeater:** Allows manual modification and replay of requests.
**Intruder:** Used for automated fuzzing and payload testing.

### Q29. What is SonarQube and what can it detect?
"A static code analysis platform used to identify security issues, bugs, and code quality problems."
##### It can detect:
- SQL Injection patterns
- Hardcoded secrets
- Weak cryptography
- Security hotspots

### Q30. What is shared responsibility model?
"Cloud providers secure the cloud infrastructure, while customers secure their data, applications, configurations, and access."

### Q31. Common AWS services?
- IAM
- CloudTrail
- GuardDuty
- Security Hub
- WAF
- KMS

### Q32. What is IAM?
"IAM controls who can access cloud resources and what actions they can perform."

### Q33. What is the principle of least privilege?
"Users should only receive the minimum permissions necessary to perform their tasks."

### Q34. What is DevSecOps?
"DevSecOps integrates security into development and deployment pipelines."

### Q35. How would you integrate security into CI/CD? Provide an example pipeline.
- SAST
- SCA
- Secret scanning
- Container scanning
- DAST
- Security gates

*Example pipeline:*
Developer Commit
↓
SAST
↓
SCA
↓
Build
↓
Container Scan
↓
Deploy to Test
↓
DAST
↓
Production

### Q36. What is Threat Modeling?
"A process of identifying threats during the design phase and implementing controls before development."

### Q37. What is STRIDE?
- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

### Q38. Explain Vulnerability Lifecycle.
Discovery
↓
Validation
↓
Risk Assessment
↓
Prioritization
↓
Remediation
↓
Retesting
↓
Closure

### Q39. How do you prioritize vulnerability?
Based on:
- CVSS score
- Exploitability
- Business impact
- Asset criticality

### Q40. You found a High vulnerability. What next?
1. Validate finding.
2. Assess impact.
3. Create report.
4. Inform development team.
5. Track remediation.
6. Retest.
7. Close.

### Q41. Developer says vulnerability is not important. What do you do?
"Explain the technical and business impact, provide proof of concept, discuss risk, and work collaboratively to reach a remediation plan."

---
# Other Questions:
- Describe a security assessment you performed.
- Describe a vulnerability you found.
- How did you validate findings?
- How did you communicate issues to developers?
- Which tools did you use daily?
- How did you prioritize vulnerabilities?
- Did you perform secure code reviews?
- What was your biggest learning?
- Tell me about a challenging vulnerability.
- Explain your complete assessment methodology.
- What is ISO 27001?
- What is HIPAA?

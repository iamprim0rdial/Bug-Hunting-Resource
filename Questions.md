## Questions to Ask About the Application

1. **What languages/stack/technology are used?**
2. **What server is running the application?**
3. **Is there a Web Application Firewall (WAF)?**
4. **What additional libraries are used? Are there known exploits for these libraries? Custom JS Libraries?**
5. **Is there Authentication?** (Basic, OAuth, JWT, OpenId,)
6. **How is session established?**
7. **Is the source code publicly available?**
8. **Are there useful comments in the code?**
9. **How does it handle special characters?**
10. **Can you trigger any error messages?**
11. **What common features are present?**
12. **How is a user identified?**
13. **Are there multiple user roles?**
14. **Is there an API?**
15. **Is there a Content Management System (CMS)?**
16. **Is there a Content Security Policy (CSP)?**
17. **Is Cross-Origin Resource Sharing (CORS) implemented?**
18. **Is CAPTCHA used?**
19. **Are WebSockets used?**
20.  **What ports are open?**
21.  **What services are running on those ports?**
22.  **Is it hosted in the cloud?**
23.  **Is it hosting multiple apps using Virtual Hosting (VHosting)?**
24.   **What is the operating system (OS)?**
25.   **Can you get the kernel version?**

---

## Questions to Ask for Every Page

1. **What part of CRUD (Create, Read, Update, Delete)?**
2. **What HTTP request methods can be used?** (GET/POST/PUT/DELETE/etc.)
3. **What parameters can be used?**


# Find Chaining Bugs

## 1. Open Redirect?
   **Check for open redirect vulnerabilities:**
   - **If yes:**
     - Can you redirect to different paths?
     - Can you redirect to different subdomains?
     - Can you redirect to different domains?
     - Can you chain multiple redirects (e.g., redirect -> redirect)?
     - Can you use the open redirect for phishing or bypassing authentication?
     - Can the redirect target a malicious file or service?

## 2. Reflected User-Controlled Data?
   **Examine if user-controlled data is reflected in the response:**
   - **If yes:**
     - **HTMLi?** (HTML Injection): Can you inject HTML that’s reflected back on the page?
     - **XSS?** (Cross-Site Scripting): Can you inject JavaScript that gets executed in the user's browser?
     - **SSTI?** (Server-Side Template Injection): Can you inject template syntax that is processed server-side (e.g., using Jinja2, Thymeleaf)?
     - Can you chain XSS and bypass filters by using complex payloads (e.g., double URL encoding)?
     - Can you chain XSS with open redirects to send the victim to a malicious page?

## 3. CSRF? (Cross-Site Request Forgery)
   **Look for CSRF vulnerabilities where actions can be triggered without user consent:**
   - **If yes:**
     - What can we do with this endpoint? Can we initiate sensitive actions (e.g., change user data, make transactions)?
     - Is this endpoint an open redirect (can it be used to redirect the victim to a malicious site after the attack)?
     - Can we chain CSRF with another vulnerability, like privilege escalation (e.g., changing user roles)?
     - Are there any ways to escalate this attack by combining with other flaws (e.g., XSS or SSRF)?
     - **Are CSRF Tokens properly validated?** (Make sure tokens are invalidated when the user logs out or after session expiry)
     - Can we bypass CSRF protection by manipulating headers (e.g., Referer, Origin)?
     
## 4. Change HTTP Verb?
   **Test if changing the HTTP request method causes unintended behavior:**
   - **If yes:**
     - Does the endpoint work the same way when the verb is changed (e.g., from `GET` to `POST`, `DELETE`, `PATCH`)?
     - Are any parameters rejected or modified when changing the HTTP verb?
     - Does changing the verb expose new actions or bypass security controls?
     - Can we trigger a security flaw like a state-changing request by switching from `POST` to `GET` or vice versa?
     - Can changing the verb help bypass authorization or access control checks (e.g., change a `GET` request to a `POST` to modify data)?

## 5. URL Parameters & Data Exposure
   **Investigate if sensitive data is exposed through URL parameters or insecure routes:**
   - **If yes:**
     - Are sensitive data, like API keys or session IDs, passed in URL parameters?
     - Can the data be manipulated or tampered with to escalate privileges (e.g., changing user IDs)?
     - Can you chain this vulnerability with SQL Injection, XSS, or other attacks to escalate or compromise the system?

## 6. Insecure Direct Object References (IDOR)?
   **Check for direct object reference issues where users can access resources they should not have permission to:**
   - **If yes:**
     - Can you change the resource identifier (e.g., user ID, document ID) in the request to access other users' data?
     - Can you chain this with privilege escalation vulnerabilities by modifying the ID or resource type?
     - Can you discover hidden endpoints or unauthorized resources by iterating over IDs?
  
## 7. Authentication Bypass (via Chained Vulnerabilities)?
   **Check for weak authentication and chaining vulnerabilities to bypass authentication:**
   - **If yes:**
     - Can you bypass login or authentication using IDOR, session fixation, or CSRF?
     - Can you escalate privileges or bypass multi-factor authentication by chaining authentication flaws with session management issues?
     - Can you perform authentication bypass through URL manipulation, like changing the `user` or `role` parameter?

## 8. Input Validation & Data Injection
   **Look for weak or missing input validation that could lead to chained attacks:**
   - **If yes:**
     - Can you inject malicious input (e.g., SQL, XSS, or command injection) to escalate an attack?
     - Can invalid input lead to data corruption or leakage of sensitive information (e.g., file paths, user data)?
     - Can an attacker chain multiple input validation flaws together to bypass security checks?

## 9. Error Handling and Information Disclosure
   **Investigate if error messages or incorrect error handling lead to vulnerabilities:**
   - **If yes:**
     - Do error messages disclose sensitive information such as stack traces, file paths, or database details?
     - Can you chain error messages with other vulnerabilities (e.g., SQL Injection or XSS) to gain more information about the system?
     - Can you use error handling flaws to redirect users to a malicious site or escalate your privileges?

## 10. Server-Side Request Forgery (SSRF)?
   **Check if SSRF vulnerabilities exist, where the server can make arbitrary requests:**
   - **If yes:**
     - Can you make the server send requests to internal or unauthorized services (e.g., internal APIs or databases)?
     - Can you chain SSRF with other vulnerabilities (e.g., open redirects, unauthorized access to private services)?
     - Can SSRF be used to gather internal network information or access other internal systems?
     - Can you manipulate the request headers or body to exploit SSRF more effectively?

## 11. Parameter Pollution
   **Check if multiple parameters of the same name can cause unexpected behavior:**
   - **If yes:**
     - Can you use multiple parameters with the same name to bypass validation or gain unauthorized access?
     - Can you chain this with other bugs, such as IDOR or authentication bypass, to exploit the system?
     - Does the application handle duplicated parameters correctly, or does it allow unexpected data to pass through?

## 12. Sensitive Data Exposure through Logs or Responses
   **Test for vulnerabilities where sensitive data might be exposed through logs or responses:**
   - **If yes:**
     - Does the system log sensitive data like passwords, API keys, or PII in error logs or server logs?
     - Can you access logs (through path traversal, insecure endpoints) to extract sensitive data?
     - Can you chain this exposure with other bugs like authentication bypass or data tampering?

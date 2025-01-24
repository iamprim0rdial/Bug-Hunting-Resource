# A# Security Testing Questions

## Questions to Ask About the Application

1. **What stack/languages are used?**
2. **What server is running the application?**
3. **Is there a Web Application Firewall (WAF)?**
4. **What additional libraries are used? Are there known exploits for these libraries? Custom JS Libraries?**
5. **Is there Authentication?** (OAuth, JWT, etc.)
6. **What Objects are used?**
7. **How is session established?**
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
20. **Is the source code publicly available?**

---

## Questions to Ask About the Server Hosting the Application

1. **What ports are open?**
2. **What services are running on those ports?**
3. **Is it hosted in the cloud?**
4. **Is it hosting multiple apps using Virtual Hosting (VHosting)?**
5. **What is the operating system (OS)?**
6. **Can you get the kernel version?**

---

## Questions to Ask for Every Page

1. **What part of CRUD (Create, Read, Update, Delete)?**
2. **What HTTP request methods can be used?** (GET/POST/PUT/DELETE/etc.)
3. **What parameters can be used?**


# Find Chaining Bugs

1. Open Redirect?
    - If yes:
        ~ Can you redirect to different paths?
        ~ Can you redirect to different subdomains?
        ~ Can you redirect to different domains?
2. Reflected user controlled data?
    - If yes:
        ~ HTMLi?
        ~ XSS?
        ~ SSTI?
3. CSRF?
    - CSRF Tokens do not appear to be invalidated when sent or when the user logs out
    If yes:
        ~ What can we do with this endpoint?
        ~ Is this endpoint an open redirect?
4. Change HTTP Verb?
    If yes:
        ~ Does the endpoint work the same way when the verb is changed?
        ~ Are any parameters rejected?

# Bug Hunting Checklist 🐞🔍

## Pre-Testing Setup 📝
- [ ] Set up the testing environment (local, staging, production) 🌐
- [ ] Ensure the app is running the latest version or the version under investigation 🔄
- [ ] Reproduce the reported bug or gather test cases 🔍

---

## Reverse Proxy & HTTP Vulnerabilities 🛠️

### Reverse Proxy Testing 🔄
- [ ] Test for improper reverse proxy configurations 🏗️
- [ ] Verify that sensitive routes are not leaked via the reverse proxy 🔑

### Abusing Hop Headers 🌐
- [ ] Test if HTTP hop-by-hop headers can be abused for unauthorized actions 📡

### Web Cache Poisoning 🍽️
- [ ] Check for caching mechanisms that could be poisoned (e.g., by injecting malicious content) 🧑‍🍳

### Web Cache Deception 🧳
- [ ] Test if attackers can deceive the cache into storing unsafe content 📦

### HTTP Request Smuggling 🛠️
- [ ] Check if HTTP request smuggling can be exploited by manipulating request boundaries 🧳

### H2C Smuggling 🔥
- [ ] Test for H2C (HTTP/2 Cleartext) smuggling attacks via misconfigured proxies 🌐

### XSLT Server-Side Injection 📜
- [ ] Check if malicious XSLT input could cause server-side injection attacks 🕵️‍♂️

### Edge Side Inclusion (ESI) Injection ⚡
- [ ] Test if ESI tags can be manipulated to include untrusted content 🧑‍🍳

### Host Header Poisoning 🏴‍☠️
- [ ] Test for host header poisoning attacks that might impact security mechanisms 🏴‍☠️

### IP Address Spoofing 🌐
- [ ] Verify that the app properly validates incoming IP addresses to prevent spoofing 🕵️‍♂️

---

## Infrastructure & DevOps Testing 🔧

### Cloud-Specific Testing ☁️

#### AWS Misconfigurations ⚠️
- [ ] Test for AWS S3 bucket misconfigurations (e.g., open buckets with sensitive data) 🗂️
- [ ] Check for AWS CloudFront misconfigurations (e.g., allowing unauthorized access) 🔐
- [ ] Verify AWS IAM/STS misconfigurations that could lead to privilege escalation 🔑
- [ ] Test for misconfigured AWS Elastic Beanstalk environments 🛠️
- [ ] Check AWS API Gateway misconfigurations (e.g., exposing sensitive routes) 🌐
- [ ] Verify AWS Cognito misconfigurations (e.g., improper authentication or access control) 🔒
- [ ] Test for exposed sensitive AWS DocumentDB 🗂️
- [ ] Check for misconfigured AWS EC2 instances (e.g., open ports, insecure configurations) 🌐
- [ ] Verify AWS SNS misconfigurations (e.g., exposed notification topics) 📧
- [ ] Test AWS RDS misconfigurations (e.g., open database access or weak access controls) 🗃️

---

### Web Server Testing 🔥

#### Common Vulnerabilities and Exposures (CVE's) 💥
- [ ] Check for known CVEs related to the web server, application, or libraries 📜

#### Exposed Configuration Files 📂
- [ ] Test for exposed configuration files (e.g., `config.php`, `.env`, `wp-config.php`) 🗂️

#### Server Side Includes (SSI) Injection 💥
- [ ] Test for SSI injection vulnerabilities that can execute arbitrary commands on the server 🧑‍💻

#### Information Disclosure 📢
- [ ] Verify that no sensitive information (e.g., error logs, server details) is disclosed 🛑

---

### Domain Name System (DNS) Testing 🌍

#### DNS Rebinding 🌐
- [ ] Test for DNS rebinding vulnerabilities that might expose internal services 🔑

#### Subdomain Takeover 🏴‍☠️
- [ ] Check for unused subdomains that might be vulnerable to takeover 👀

---

## Core Application Testing 💻

### Global Application Config Testing 🌍

#### Content Security Policy (CSP) 🛡️
- [ ] Ensure a strong Content Security Policy (CSP) is in place to prevent XSS attacks 🛑

#### Cross-Origin Resource Sharing (CORS) 🚫
- [ ] Test for misconfigured CORS policies that could allow unauthorized cross-origin requests 🌍

#### Dependency Confusion / Abuse 🧩
- [ ] Test for dependency confusion vulnerabilities in package management (e.g., NPM, Pip) 📦

#### JSON Web Token (JWT) Misconfiguration 🛠️
- [ ] Check for improperly configured JWT tokens that could lead to session hijacking or unauthorized access 🔑

#### Missing Security Headers 🛡️
- [ ] Ensure critical security headers are set (e.g., `X-Content-Type-Options`, `X-XSS-Protection`) ⚠️

---

### Client-Side Codebase Testing 🖥️

#### Content Injection 💥
- [ ] Test for content injection vulnerabilities in user inputs 📝

#### Cross-Site Scripting (XSS) 💥
- [ ] Test for reflected XSS vulnerabilities on input fields 📝
- [ ] Test for stored XSS vulnerabilities where malicious scripts are persisted 🔥
- [ ] Test for blind XSS where the payload is triggered later 🔓
- [ ] Test for DOM-based XSS vulnerabilities (where client-side JS manipulates the DOM) 🖱️

#### Dangling Markup 🧩
- [ ] Check if untrusted data is reflected as HTML markup without proper sanitization 🛑

#### Client-Side JavaScript Injection 📜
- [ ] Test for JavaScript injection vulnerabilities in client-side code 🧑‍💻

#### DOM-Based Open Redirect 🔄
- [ ] Test for open redirect vulnerabilities where untrusted URLs are being used in redirects 🔀

#### Client-Side Template Injection (CSTI) 🧩
- [ ] Check for template injection vulnerabilities in client-side frameworks (e.g., Angular, React) 🧑‍💻

#### PostMessage Vulnerabilities 📡
- [ ] Test for potential issues with the `window.postMessage` API 📨

#### Privileged Credentials Exposed 🔑
- [ ] Check if privileged credentials (e.g., API keys, secrets) are exposed in client-side code 🛑

#### Insecure Data Storage 💾
- [ ] Test if sensitive data is being stored insecurely on the client-side (e.g., localStorage, cookies) 📂

#### Client-Side Denial of Service (DoS) / Breaking The DOM ⚡
- [ ] Check if the app can be easily crashed by overwhelming the client-side with requests 🛑

---

### Server-Side Codebase Testing 🧑‍💻

#### Command Injection ⚠️
- [ ] Test for command injection vulnerabilities where user input can execute system commands 🧑‍💻

#### Code Injection 📝
- [ ] Test for code injection vulnerabilities in dynamic eval functions 🧑‍💻

#### Insecure Deserialization 🧩
- [ ] Check for insecure deserialization issues that could allow remote code execution 🔓

#### LDAP Injection 🏗️
- [ ] Test for LDAP injection vulnerabilities where malicious input could bypass authentication 🛑

#### Server-Side Request Forgery (SSRF) 🔌
- [ ] Test for SSRF vulnerabilities that could access internal resources via user-controlled input 🛠️

#### File Inclusion / Path Traversal 🔐
- [ ] Test for local or remote file inclusion vulnerabilities that can compromise the server 🔒

#### XPATH Injection 🔍
- [ ] Test for XPath injection vulnerabilities in web apps using XML queries 🧑‍💻

#### Unrestricted File Upload 🗂️
- [ ] Check for unrestricted file uploads that could allow attackers to upload malicious files 🖥️

#### Web Shell via File Upload 🖥️
- [ ] Test for the possibility of uploading web shells via file uploads 💥

#### Server-Side Template Injection (SSTI) 📜
- [ ] Test for template injection vulnerabilities in server-side rendering engines 🧑‍💻

#### XML External Entity (XXE) ⚡
- [ ] Test for XXE vulnerabilities that can lead to file disclosures or remote code execution 🧩

#### WebSocket Injection 🔌
- [ ] Test for WebSocket injection vulnerabilities that can affect real-time communication 🧑‍💻

---

### Database Operation Testing 💾

#### SQL Injection 🧪
- [ ] Test for SQL injection vulnerabilities in form inputs or URLs 🔒

#### NoSQL Injection 🧑‍💻
- [ ] Test for NoSQL injection vulnerabilities, especially in MongoDB or similar databases 🌐

#### GraphQL Injection 🧩
- [ ] Test for injection vulnerabilities in GraphQL queries 📝

#### Denial of Service (DoS) ⚡
- [ ] Test if the database is vulnerable to DoS attacks by overloading it with queries 🧩

#### Information Disclosure 🔓
- [ ] Test for database information leaks (e.g., error messages revealing database details) 📜

---

### Creative Application Testing 🎨

#### External Identity Access Management (IAM) Testing 🌐
- [ ] Test for OAuth, SAML, and other IAM misconfigurations in third-party integrations 🔑
- [ ] Check for misconfigurations in Google Firebase and Keycloak IAM systems 🌍

#### Application Logic Testing 🧩
- [ ] Test for logic flaws, such as IDOR, insufficient access control, 2FA/MFA bypass 🔐
- [ ] Check for rate-limiting or brute-force protection bypasses 🧑‍💻

#### Public Repository & OSINT Testing 🔍
- [ ] Search for internal source code or credentials in public repositories (e.g., GitHub, GitLab) 🕵️‍♂️
- [ ] Check for any exposed sensitive data found via web scraping or in public GitHub repos 📂

---

## Post-Bug Hunting 🏁
- [ ] Verify the fix works on staging or production 💡
- [ ] Ensure the vulnerability doesn't reappear after the fix ✅
- [ ] Update or close the issue on GitHub 🗂️
- [ ] Review the application for any new potential vulnerabilities 🔍

---

# 🐾

# Web Application Security Testing Notes

## Login Forms
- **Description**: Areas where users enter credentials to access accounts.
- **URL Pattern**: `/login` or `/user/signin`
- **Vulnerability**: SQL Injection
- **Test Example**: `username' OR '1'='1' --`
- **Mitigation**: Test for weak passwords and brute force attacks.

---

## Registration Forms
- **Description**: Pages for new users to create accounts.
- **URL Pattern**: `/register` or `/user/signup`
- **Vulnerability**: Cross-Site Scripting (XSS)
- **Test Example**: `<script>alert('XSS')</script>`
- **Mitigation**: Validate input to ensure proper sanitization.

---

## Search Functionality
- **Description**: Input fields that allow users to search for content.
- **URL Pattern**: `/search?q=keyword`
- **Vulnerability**: Reflected XSS
- **Test Example**: `/search?q=<script>alert(1)</script>`
- **Mitigation**: Inject scripts to test for XSS vulnerabilities.

---

## File Uploads
- **Description**: Forms that permit users to upload files.
- **URL Pattern**: `/upload` or `/profile/upload`
- **Vulnerability**: Remote Code Execution (RCE)
- **Test Example**: Uploading a `.php` file that executes code.
- **Mitigation**: Attempt to upload malicious files.

---

## Contact Forms
- **Description**: Forms used for user inquiries or feedback submissions.
- **URL Pattern**: `/contact` or `/support`
- **Vulnerability**: Email Injection
- **Test Example**: `name=test&email=test@example.com%0ARecipient: admin@example.com`
- **Mitigation**: Test for header injections.

---

## API Endpoints
- **Description**: URLs exposing application functionalities via API.
- **URL Pattern**: `/api/v1/users` or `/api/v1/products`
- **Vulnerability**: Insecure Direct Object Reference (IDOR)
- **Test Example**: Accessing another user’s data via `/api/v1/users/2`
- **Mitigation**: Manipulate IDs in requests to test for IDOR vulnerabilities.

---

## Comment Sections
- **Description**: Areas where users can leave comments or feedback.
- **URL Pattern**: `/blog/post?id=123`
- **Vulnerability**: Stored XSS
- **Test Example**: Commenting with `<script>alert('XSS')</script>`
- **Mitigation**: Test comments for XSS injection.

---

## Payment Processing
- **Description**: Pages for processing payments or handling transactions.
- **URL Pattern**: `/checkout` or `/payment`
- **Vulnerability**: CSRF (Cross-Site Request Forgery)
- **Test Example**: Making unauthorized payments through crafted requests.
- **Mitigation**: Use CSRF tokens to test against CSRF vulnerabilities.

---

## Admin Panels
- **Description**: Interfaces for administrators to manage the application.
- **URL Pattern**: `/admin` or `/dashboard`
- **Vulnerability**: Broken Access Control
- **Test Example**: Accessing `/admin/users` without authentication.
- **Mitigation**: Check for unauthorized access to admin functionalities.

---

## Profile Pages
- **Description**: User-specific pages displaying account details.
- **URL Pattern**: `/profile` or `/user/settings`
- **Vulnerability**: Insecure Direct Object Reference (IDOR)
- **Test Example**: Viewing another user’s profile by manipulating the URL.
- **Mitigation**: Manipulate parameters to access other users' profiles.

---

## Redirects
- **Description**: Links that redirect to other resources or pages.
- **URL Pattern**: `/redirect?url=http://malicious-site.com`
- **Vulnerability**: Open Redirect
- **Test Example**: Redirecting to a malicious site via manipulated URL parameter.
- **Mitigation**: Test redirect functionality with untrusted URLs.

---

## Cookie Settings
- **Description**: Options for users to manage cookies or preferences.
- **URL Pattern**: `/cookie-policy` or `/settings/cookies`
- **Vulnerability**: Session Fixation
- **Test Example**: Exploiting session IDs to hijack user sessions.
- **Mitigation**: Test session management and cookie security.

---

## Third-Party Integrations
- **Description**: External services integrated into the application.
- **URL Pattern**: `/auth/google` or `/oauth/facebook`
- **Vulnerability**: OAuth Misconfiguration
- **Test Example**: Using a compromised redirect URI to access tokens.
- **Mitigation**: Test for proper handling of redirect URIs.

---

## Help/FAQ Sections
- **Description**: Pages providing user support and common questions.
- **URL Pattern**: `/help` or `/faq`
- **Vulnerability**: Information Disclosure
- **Test Example**: Exposing sensitive system information through FAQs.
- **Mitigation**: Review FAQs for exposure of sensitive info.

---

## Admin APIs
- **Description**: APIs designed for administrative tasks.
- **URL Pattern**: `/admin/api/v1/users`
- **Vulnerability**: Unauthenticated Access
- **Test Example**: Accessing sensitive admin functions without credentials.
- **Mitigation**: Test for access control on admin APIs.

---

## Unprotected Pages
- **Description**: Pages accessible without authentication.
- **URL Pattern**: `/public-data`
- **Vulnerability**: Unprotected Access
- **Test Example**: Accessing sensitive data without login.
- **Mitigation**: Use scanners like Burp Suite to find unprotected pages.

---

## Unvalidated User Input
- **Description**: User input that is not properly sanitized.
- **Vulnerability**: SQL Injection, Command Injection, XSS
- **Test Example**: Injecting SQL commands or scripts into inputs.
- **Mitigation**: Test for injection vulnerabilities by injecting payloads.

---

## Broken Authentication
- **Description**: Improperly implemented authentication mechanisms.
- **Vulnerability**: Weak Passwords
- **Test Example**: Users with weak passwords easily compromised.
- **Mitigation**: Test for weak passwords and missing security headers.

---

## Clickjacking
- **Description**: Trick users into clicking hidden elements.
- **Vulnerability**: Clickjacking
- **Test Example**: User clicks on a disguised button.
- **Mitigation**: Test by embedding the page in an iframe and manipulating layout.

---

## Insecure Communication
- **Description**: Insecure protocols or unencrypted connections.
- **Vulnerability**: Data Exposure
- **Test Example**: Sensitive data transmitted without encryption.
- **Mitigation**: Test for insecure communication channels and recommend secure alternatives.

---

## Missing Security Headers
- **Description**: Missing headers to mitigate web attacks.
- **Vulnerability**: Information Disclosure
- **Test Example**: Potential for attacks like XSS, clickjacking.
- **Mitigation**: Use tools like Burp Suite to scan for missing security headers.

---

## Unencrypted Sensitive Data
- **Description**: Data that should be encrypted but is not.
- **Vulnerability**: Data Exposure
- **Test Example**: Sensitive data visible in transit.
- **Mitigation**: Check for HTTPS and weak encryption methods.

---

## Insecure File Uploads
- **Description**: Allows uploading of malicious files.
- **Vulnerability**: RCE, Unrestricted File Upload
- **Test Example**: Uploading an executable or script file.
- **Mitigation**: Test by uploading various file types.

---

## Server-Side Request Forgery (SSRF)
- **Description**: Ability to make unauthorized requests from the server.
- **Vulnerability**: SSRF
- **Test Example**: Accessing internal resources from the server.
- **Mitigation**: Manipulate URL parameters to test for SSRF vulnerabilities.

---

## Cross-Site Scripting (XSS)
- **Description**: Vulnerabilities allowing injecting malicious scripts.
- **Vulnerability**: XSS
- **Test Example**: Injecting `<script>alert('XSS')</script>`
- **Mitigation**: Inject scripts into input fields to test for XSS vulnerabilities.

---

## Insecure Direct Object References
- **Description**: URLs that can be manipulated to access unauthorized resources.
- **URL Pattern**: `/resource?id=123`
- **Vulnerability**: IDOR
- **Test Example**: Accessing resource with ID 124 instead of 123.
- **Mitigation**: Change IDs in the URL to check for access control.

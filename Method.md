
### **Step 1: Reconnaissance** 
1. **Understand the Scope and Rules**:    - Carefully read the **Atlassian Security Policy** on the bug bounty platform they’re using.    - Make sure company-specific endpoints (like hosted repositories, pipelines, or API interactions) are in scope. 
 2. **Subdomain Enumeration**:    - Bitbucket uses multiple subdomains—like `bitbucket.org`, `api.bitbucket.org`, and more. Check for related Atlassian or Bitbucket-hosted resources.      - Tools: `Subfinder`, `Amass`, or `Assetfinder`      - Example:          ```bash        subfinder -d bitbucket.org        
  3. **Check Public Repos for Sensitive Data**:   
  		- Look for **public repositories** with misconfigurations or leaked secrets.   
  	   - Use dorks like:        ```        site:bitbucket.org password        site:bitbucket.org config.yml        ```    - Tools: **GitTools**, **truffleHog**, **git-secrets**.
  	  ---
    ###   **Step 2: Enumeration & Asset Discovery** 
   1. **Identify Endpoints and Features**:  
    	 - Focus on the **Bitbucket API**: 
         - Check the API docs: https://developer.atlassian.com/bitbucket/api/2/
         - Look for **repository, user, and admin endpoints**.  
   3. **Analyze Web Functionality**:  
   			  - Explore key areas:  	
   						    - Repository creation, management, and settings 
   					 	    - Pull requests, forks, and pipeline triggers
               ⇒ User roles: admin vs. read-only vs. collaborators  
               			 - Watch out for:
                        → Weak access controls: Can a non-collaborator access private repos?
                         - Repository settings bypasses 
    3. **Check for OAuth Apps / Integrations**:  
         → Look for potential flaws in **third-party integrations** (like Slack, Jenkins). 
         →    - Test OAuth flows for open redirects, misconfigurations, or scope escalation. 
          ---  ### 
    **Step 3: Vulnerability Hunting**
     1. **Common Vulnerabilities**:  
       - **IDOR (Insecure Direct Object References)**:      - Example: Accessing another user's repository or pipeline without permission.      - Try changing `repository_id` or `user_id` in API calls:        
    ```bash        curl -X GET "https://api.bitbucket.org/2.0/repositories/{org}/{repo}"        ```  
       - **SSRF (Server-Side Request Forgery)**:  
       - Check if Bitbucket pipelines allow importing resources via URLs (e.g., `curl` commands in `.yml` files).    
        - If so, try SSRF payloads to access internal services:    
         ```bash        curl http://169.254.169.254/latest/meta-data        ```    
          - **API Key Leaks / Hardcoded Secrets**:      - Use tools like **truffleHog** to scan for accidentally exposed API keys, OAuth tokens, or SSH keys. 
      2. **CICD Pipeline Weaknesses**:
            → Look for:      - **Malicious pipeline injection**—can you modify a pipeline triggered by another user? 
             - Exposed artifacts or logs containing sensitive data.  
       3. **Cross-Site Scripting (XSS)**:    - Test various inputs in comments, pull requests, or repository descriptions:      
       ```html      <script>alert(document.cookie)</script>      ``` 
        4. **Access Control Bypass**:    - Test if **guest users** can access restricted endpoints.   
         - Try:      - Making API requests with invalid tokens to identify permissions leakage.     
         -  - Manipulating roles—can a read-only user push code or delete repos? 
         --- 
       ### **Step 4: Tools & Payloads** 
        1. **Tools**:    - **Burp Suite**: For intercepting and analyzing API calls.  
          - **GitTools**: To clone, extract, and analyze repository history.   
           - **TruffleHog**: To find secrets in repositories.  
             - **HTTPie / cURL**: For interacting with Bitbucket’s APIs. 
         2. **Payloads to Use**:   
            → SSRF Payload:     
             ```bash      http://169.254.169.254/latest/meta-data/iam 
                  ```    - XSS Payload:      ```html      <img src=x onerror=alert(1)>      ``` 
                   ---
  ### **Step 5: Reporting Your Findings**
   - Provide a **detailed PoC (Proof of Concept)**.
   - Structure your report well: 
    1. **Title**: Clear and descriptive  
     2. **Summary**: Brief description of the vulnerability  
      3. **Steps to Reproduce**: Easy-to-follow steps 
       4. **Impact**: Why it matters (data leakage, access control, etc.)  
        5. **Mitigation Recommendations**: Suggested fixes  \

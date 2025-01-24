# Web Application Penetration Testing Process

## 1. Choose the Target
- Select your target for testing and confirm it is within your scope.

## 2. Check In-scope Domain
- Ensure the domain is part of the engagement’s in-scope targets.

## 3. Search About Target Work & Their Assets
- Understand the purpose and functionality of the target system.
- Identify any related assets and components that might be relevant for the testing.

---

## **4. Conduct Reconnaissance**  
*(Gather as much information as possible about the target system.)*

### Tasks for Reconnaissance:
1. **Enumerate the possible and alive subdomains, child or sibling domains.**
   - Use tools to discover related subdomains and associated services.

2. **Collect technical details**  
   - Identify the server type, software versions, and dependencies used by the target.

3. **Network Configuration**  
   - Investigate firewalls, routing tables, DNS, and other networking configurations.

4. **Publicly Available Information**  
   - Gather data from Whois records, SSL/TLS certificates, and publicly available source code.

5. **Social Media and Other Online Presence**  
   - Look for information shared on social media platforms or other online presence (e.g., blogs, forums).

---

## 5. Give Time and Try to Test on All Sub-domains
- Perform thorough testing across all discovered subdomains to ensure no part of the target system is overlooked.

---

## **6. Map the Attack Surface**  
*(Greater the collected information, helps to create a larger attack surface area, which increases the likelihood of successful exploitation.)*

- Identify and map out the various services, applications, and components to form a broader attack surface.

---

## 7. **Identify Potential Entry Points**
### Key Areas to Focus on:
1. **Unprotected Network Services**  
   - Look for services such as FTP, SSH, Telnet, etc., that may be exposed and unprotected.

---

## 8. Automate Testing for Entry Points
- Use automated tools to scan and test for vulnerabilities in each identified entry point.

## 9. **Manual Testing on Each Entry Point**
- After automation, manually test each entry point to uncover complex vulnerabilities that automated tools may miss.

---

## 10. Recheck and Revisit Vulnerability Checkpoints
- Regularly review previously tested points to confirm the persistence of vulnerabilities and any changes over time.

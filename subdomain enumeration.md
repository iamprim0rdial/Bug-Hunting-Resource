## Subdomain Enumeration Feel 

### **1. All Subdomains**

- **subfinder**  
  Enumerate subdomains and get all results:  
  `subfinder -d example.com -all -recursive -o subdomain.txt`  

- **assetfinder**  
  Retrieve a list of subdomains using Assetfinder:  
  `sudo assetfinder -subs-only example.com > assetfinder.txt`

- **shodanx**  
  Use ShodanX for subdomain enumeration:  
  `shodanx subdomain -d example.com -ra -o shodax.txt`

- **amass**  
  Perform active subdomain enumeration with Amass:  
  `amass enum -active -norecursive -noalts -d example.com -o amass.txt`
  
- **alienvault**   
  Query AlienVault for passive DNS data:  
  `curl -fs "https://otx.alienvault.com/api/v1/indicators/hostname/granularinsurance.com/passive_dns" | jq -r '.passive_dns[]?.hostname' | grep -Ei "^[a-zA-Z0-9.-]+\.granularinsurance\.com$" | anew | tee alienvault_subs.txt`

---

- **web.archive.org (Wayback Machine)**    
  Use the Wayback Machine to discover historical subdomains:  
  `curl -fs "http://web.archive.org/cdx/search/cdx?url=*.example.com/*&output=json&collapse=urlkey" | jq -r '.[1:][] | .[2]' | grep -Ei '([a-zA-Z0-9_-]+\.)?example\.com' | anew | tee webarchive_subs.txt`

---

- **urlscan.io**    
  Extract subdomains using URLScan.io API:  
  `curl -fs "https://urlscan.io/api/v1/search/?q=domain:example.com&size=10000" | jq -r '.results[]?.page?.domain' | grep -Ei "^[a-zA-Z0-9.-]+\.example\.com$|^example\.com$" | anew | tee urlscan_subs.txt`

---

- **gobuster**    
  Use Gobuster for DNS subdomain brute force:  
  `gobuster dns -d example.com -w /usr/share/wordlists/subdomain_megalist.txt -o gobuster.txt`

---

- **Combine results**  
  Aggregate all discovered subdomains:
  `cat *.txt | anew all_subdomain.txt`

---
  - **crt.sh**  
  Retrieve subdomains from Certificate Transparency logs this is bash script:  
  ```bash
      curl -s https://crt.sh/?q=%.$1&output=json | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u | tee -a crtsh.txt     




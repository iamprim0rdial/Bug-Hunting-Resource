## Subdomain Enumeration Feel 

### **1. All Subdomains**

- **subfinder**    **: Note: [ -all ] use all sources for enumeration (Need API)**  
    Enumerate subdomains and get all results:   
  `subfinder -d example.com -all -recursive -o subdomain.txt`  
  `subfinder -dL domain.txt -all  -o subdomain.txt`  

- **assetfinder**  
  Retrieve a list of subdomains using Assetfinder:  
  `sudo assetfinder -subs-only example.com > assetfinder.txt`

- **shodanx**  
  Use ShodanX for subdomain enumeration:  
  `shodanx subdomain -d example.com -ra -o shodax.txt`

- **amass**  
  Perform active subdomain enumeration with Amass:  
  `amass enum -active -norecursive -noalts -d example.com -o amass.txt`

- **dnsrecon**  
  DNS Recon tool for additional subdomain and DNS information gathering:  
  `dnsrecon -d example.com -t std`
  
- **alienvault**   
  Query AlienVault for passive DNS data:
  ```bash  
  curl -fs "https://otx.alienvault.com/api/v1/indicators/hostname/example.com/passive_dns" | jq -r '.passive_dns[]?.hostname' | grep -Ei "^[a-zA-Z0-9.-]+\.example\.com$" | anew | tee alienvault_subs.txt`

---

- **web.archive.org (Wayback Machine)**    
  Use the Wayback Machine to discover historical subdomains:
  ```bash  
  curl -fs "http://web.archive.org/cdx/search/cdx?url=*.example.com/*&output=json&collapse=urlkey" | jq -r '.[1:][] | .[2]' | grep -Ei '([a-zA-Z0-9_-]+\.)?example\.com' | anew | tee webarchive_subs.txt`

---

- **urlscan.io**    
  Extract subdomains using URLScan.io API:
  ```bash
  curl -fs "https://urlscan.io/api/v1/search/?q=domain:example.com&size=10000" | jq -r '.results[]?.page?.domain' | grep -Ei "^[a-zA-Z0-9.-]+\.example\.com$|^example\.com$" | anew | tee urlscan_subs.txt`

---

  - **crt.sh**  
  ``Retrieve subdomains from Certificate Transparency logs this is bash script:  
  ```bash
     curl -s https://crt.sh/?q=%.$1&output=json | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u | tee -a crtsh.txt     
```
---
- **gobuster**    
  Use Gobuster for DNS subdomain brute force:  
  `gobuster dns -d example.com -w /usr/share/wordlists/subdomain_megalist.txt -o gobuster.txt`

---

- **Combine results**    
  Aggregate all discovered subdomains:  
  `cat *.txt | anew all_subdomain.txt`  
  
--- 

## Filter live subdomains
   ```bash
   cat all_subdomain.txt | httpx-toolkit -td -title -sc -ip > live.txt

```
### Extract live subdomains:  
`cat live.txt | awk '{print $1}' > live_subdomain.txt`  


### Check for open ports on the subdomains:  
```bash
httpx-toolkit -l all_subdomain.txt -ports 80,81,3000,3001,8443,10000,9000,9443,443,8080,8000,8888,4443,2075,2076,6443,3868,3366,9091,5900,8081,6000,8181,3306,5000,4000,5432,15672,9999,161,4044,7077,4040,8089 -threads 80 -o alive.txt
```

### Check for WAF ( web application firewall )
```
cat subdomains.txt | httpx-toolkit -waf -v -ua "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36" -timeout 5 -o waf-httpx.txt
```



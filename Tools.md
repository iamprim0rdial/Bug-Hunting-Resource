**After [Subdomain enumeration](https://github.com/iamprim0rdial/Bug-Hunting-Resource/blob/main/Subdomain%20Enum.md)**

---

- **Nikto**   

`nikto -h live_subdomains.txt -output nikto_results.txt`  

---

- **Subdomain takeover**

`subzy run --targets live_subdomains.txt --concurrency 100 --hid_fails -verify_ssl`

---

- **Katana**

`katana -u https://www.example.com -d 5 -kf -jc -fx -ef woff,svg,png,jpg,jpeg,woff2,gif,css -o katana.txt` 

`cat katana.txt| grep ".js$"`  `Note: grepping js file from katana.txt ` 



---

- **Broken Link Hijacking**

`socialhunter -f live_subdomains.txt`

---

- **Screenshotting**

`eyewitness --web -f live_subdomains.txt -threads 5 -d screenshots`

---

- **N-map**
```
nmap -sV -sC -T4 -iL live_subdomains.txt -ON nmap_results.txt
sudo nmap --script http-wordpress-* -p 80 <domain or ip> -Pn
sudo nmap --script=vuln <domain or ip> -Pn
sudo nmap --script http-wordpress-enum --script-args type="plugins",search-limit=1500 -p 80  <domain or ip> -Pn
nmap --script http-wordpress-brute  <domain or ip> -Pn
nmap -Pn -p- -A -iL live_subdomains.txt -sV -T4 | tee -a nmap_result.txt
{
Useful script categories:

    default - The default set of scripts.
    discovery - Scripts related to network discovery.
    vuln - Scripts for vulnerability scanning.
    exploit - Exploit-related scripts.
    intrusive - Scripts that are potentially intrusive, meaning they may affect the target.
}

```
---

- **Nuclei Automated Live Subdomains Spray (with rate limit)**
```
nuclei -l live_subdomains.com.txt -rl 10 -bs 2 -c 2 -as-silent -s critical, high, medium`
nuclei -l subdomain.txt -t /nuclei-templates/http/misconfiguration`
nuclei -l subdomain.txt -t /nuclei-templates/http/exposures

```

---

- **Subdomains without WAF**

`cat httpx_domain.com.txt | grep -v -i -E 'cloudfront imperva|cloudflare' > nowaf_subdomain.txt`

- **Visit All Non-WAF Subdomains Manually**  
`cat nowaf_subdomain.txt | grep 403 | awk '{print $1}'`

---

- **Prepare the List of 403 Subdomains for Fuzzing✪**  
 `cat nowaf_subdomain.txt | grep 403 | awk '{print $1}' > 403_subdomain.com.txt`

---

- **403 Fuzzing - Default Wordlist Fuzzing**

```
dirsearch -u https://sub.domain.com -x 403,404,500, 400, 502,503, 429  —random-agent
dirsearch -l subdomains_alive.txt -x 500,502,429,404,400 R 5 --random-agent -t 100 -o directory.txt -w /root/Desktop/tools/oneListForall/onelistforallshort.txt
dirsearch -u https://sub.domain.com -e xml, json, sql, db, log, yml, yaml, bak, txt,tar.gz, zip -x 403,404,500, 400, 502,503,429 --random-agent
dirsearch -u https://www.play.com -e conf, config, bak, backup, swp, old, db, sql, asp, aspx, aspx, asp, py, rb, rb, php, php, bak, bkp, cache, cgi, conf, csv, html, inc, jar, js, json, jsp, jsp, lock, log, rar, old, sql, sql. gz, http://sql.zip,sql.tar.gz, sql~, swp~, swp, tor, tar.bz2, tar.gz, txt, wadl, zip, .log,.xml,.js.,.json

```

---

- **WordPress Enumeration/ WPScan one-liners**
```
sudo wpscan --url http://192.168.57.121/wordpress -e u   #enumerate users
sudo wpscan --url http://192.168.57.121/wordpress/ --usernames admin --passwords /usr/share/wordlists/dirb/big.txt #bruteforce one user
sudo wpscan --url http://192.168.101.174/wordpress —enumerate ap, at, cb, dbe -o wpscan.txt #enumerate plugins and redirect output to file
wpscan --disable-tls-checks --url https://red:12388/blogblog/ —enumerate ap --plugins-detection #aggressive aggressive plugins detection
wpscan --disable-tls-checks --url https://red:12380/blogblog/ -e u #disable checks
wpscan --disable-tls-checks --url https://granularinsurance.com/ -e --force --wp-content-dir https://granularinsurance.com/wp-content/

```

---


# Google Dorks for Security Testing

## **1. General Google Dorks**

- **Sensitive Information Exposure**  
  `inurl:example.com "MYSQL_ROOT_PASSWORD:" ext:env OR ext:yml -git`
  
- **Index of Directories**  
  `inurl:example.com intitle:"index of"`
  
- **Config/Backup Files**  
  `inurl:example.com intitle:"index of /" "config.db"`
  
- **File Extensions for Sensitive Data**  
  `inurl:example.com intitle:"index of" ext:sql|xls|xml|json|csv`
  
- **API Secrets Exposure**  
  `inurl:example.com allintext:"API_SECRET*" ext:env | ext:yml`
  
- **Potential SQL Injection**  
  `inurl:example.com intext:admin ext:sql inurl:admin`

- **Sensitive Key Exposure**  
  `inurl:example.com allintext:username,password filetype:log site:example.com "-----BEGIN RSA PRIVATE KEY-----" -inurl:id_rsa`

---

## **2. Cloud Storage & File Sharing Dorks**

- **Google Docs Exposure**  
  `site:docs.google.com inurl:”/d/” “Target”`

- **OneDrive Exposure**  
  `site:onedrive.live.com “Target”`
  
- **Dropbox Exposure**  
  `site:dropbox.com/s “Target”`
  
- **Box.com Exposure**  
  `site:box.com/s “Target”`

- **Pastebin Exposure**  
  `site:pastebin.com “Target”`

---

## **3. Vulnerability & Exploitation Dorks**

- **Sensitive Parameter Exposure**  
  `inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example.com`
  
- **XSS Prone Parameters**  
  `inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:example.com`
  
- **SQL Injection Prone Parameters**  
  `inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com`
  
- **SSRF Prone Parameters**  
  `inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain= | inurl:page= inurl:& site:example.com`

---

## **4. Code and Sensitive Data Exposure**

- **GitHub Secret Exposure**  
  `site:github.com "Target" inurl:secret`

- **GitHub Token Exposure**  
  `site:github.com "Target" inurl:token`
  
- **GitHub Key Exposure**  
  `site:github.com "Target" inurl:key`

- **JFrog Artifactory Exposure**  
  `site:jfrog.io “Target”`
  
- **Firebase Exposure**  
  `site:firebaseio.com “Target”`

---

## **5. Cloud Storage Recon**

- **Amazon S3 Exposure**  
  `site:s3.amazonaws.com “Target”`

- **Google Drive Exposure**  
  `site:drive.google.com “Target”`
  
- **Azure Blob Storage Exposure**  
  `site:blob.core.windows.net “Target”`

- **DigitalOcean Spaces Exposure**  
  `site:digitaloceanspaces.com “Target”`

---

## **6. Well Some Other Dorks**

- **GitLab Exposure**  
  `inurl:gitlab "keyword"`

- **GitHub Exposure**  
  `inurl:github "keyword"`

- **CodePen Exposure**  
  `site:codepen.io "keyword"`

- **Bitbucket Exposure**  
  `site:bitbucket.org "keyword"`

- **Trello Exposure**  
  `site:trello.com "keyword"`

- **Prezi Exposure**  
  `site:prezi.com "keyword"`

- **Product Forums Exposure**  
  `site:productforums.google.com "keyword"`

- **Gitter Exposure**  
  `site:gitter.im "keyword"`

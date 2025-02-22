# Google Dorks for Security Testing

## **1. General Google Dorks**

- **Sensitive Information Exposure**  
  `inurl:example.com "MYSQL_ROOT_PASSWORD:" ext:env OR ext:yml -git`
  
- **Index of Directories**  
  `inurl:example.com intitle:"index of"`
  
- **Config/Backup Files**  
  `inurl:example.com intitle:"index of /" "config.db"`
  
- **File Extensions for Sensitive Data**
  - **Database Files**  
    `inurl:example.com  ext:sql | ext:db  | ext:env | ext:cfm | ext:pl | ext:rb | ext:dbf | ext:mdb | ext:sql.gz | ext:sql.gz | ext:db.gz | ext:db.gz `
  - **Config Files**  
    `inurl:example.com intitle:"index of" | ext:spx | ext:asp | ext:env | ext:cfm | ext:config | ext:xml | ext:conf | ext:cnf | ext:reg | ext:inf | ext:rdp | ext:cfg | ext:txt | ext:ora | ext:env | ext:ini`
  - **Documents File**  
     `inurl:example.com ext: xls | ext:csv | ext:pdf | ext:doc | ext:ppt | ext:xlsx | ext:log  | ext:odt | ext:rtf | ext:sxw | ext:psw | ext:ppt | ext:pptx | ext:pps | ext:docx`
  - **Backup Files**  
      `inurl:example.com ext:zip | ext:tar | ext:gz | ext:bz2 | ext:7z | ext:rar  | ext:txt | ext: bak | ext:old | ext:swp | ext:tmp | ext:bkf | ext:bkp | ext:backup | ext:dmp`
  - **Other ext**    
    ```bash
    inurl:example.com intitle:index.of | ext:log | ext:php intitle:phpinfo "published by the PHP Group" | inurl:shell | inurl:backdoor | inurl:wso | inurl:cmd | shadow | passwd | boot.ini |  inurl:backdoor | inurl:readme | inurl:license | inurl:install | inurl:setup | inurl:config | inurl:"/phpinfo.php" | inurl:".htaccess" | ext:swf
    
  
- **API Secrets Exposure**  
  `inurl:example.com allintext:"API_SECRET*" ext:env | ext:yml`
  
- **Potential SQL Injection**  
  `inurl:example.com intext:admin ext:sql inurl:admin`

- **Sensitive Key Exposure**  
  `inurl:example.com allintext:username,password filetype:log`  
  `site:example.com "-----BEGIN RSA PRIVATE KEY-----" -inurl:id_rsa`

- **Juicy Endpoint**  
  `site:Target ext:jsp | ext:asp | ext:aspx | ext:pl | ext:cfm | ext:py | ext:rb` 

- **File Upload**
  `site:Target/.com "choose file"` 
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

- **LFI Prone Parameters**  
  `inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:Target`

- **Open Redirect prone Param**    
  `inurl:url | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= | inurl:url | inurl:location= | inurl:dest= | inurl:src=http | inurl:r=http | inurl:& inurl:http site:Target`  

- **RCE prone Parameter**  
  `inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read= | inurl:ping= inurl:& site:Target`

- **Error prone Parameter**  
  `inurl:"error" | intitle:"exception" | intitle:"failure" | intitle:"server at" | inurl:exception | "database error" | "SQL syntax" | "undefined index" | "unhandled exception" | "stack trace" site:example[.]com`
  
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
  ```
  site:*.s3.amazonaws.com
  site:*.s3.amazonaws.com "company"
  site:*.s3.amazonaws.com "domain.com"
  site:*.s3.amazonaws.com inurl:company
  site:*.edu.s3.amazonaws.com
  site:*.edu.*.s3.amazonaws.com
  site:*.gov.*.s3.amazonaws.com
  site:*.gov.s3.amazonaws.com


  1. Use extensions like pdf,doc,docx,xls,xlsx,txt,....
  2. Use keywords like CONFIDENTIAL,HIGHLY CONFIDENTIAL,COMPANY SENSITIVE,etc..
  3. Use sensitive strings like "date of birth","default credential", "password",etc..
  4. Use financial keywords like "bank account", "credit card", "IFSC",etc..
  

  site:s3-external-1.amazonaws.com
  site:*.s3.eu-north-1.amazonaws.com
  site:*.s3.eu-north-2.amazonaws.com
  site:*.s3-*.amazonaws.com
  site:s3.amazonaws.com “Target” ```

- **Google Drive Exposure**  
  ```bash
  site:drive.google.com inurl:/drive/folders "company"
  site:domain.com "drive.google.com/drive/folders"
  site:domain.com "drive.google.com/drive/"
  site:domain.com "drive.google.com"
  site:domain.com "drive.google.com/drive/file/d"
  site:domain.com "drive.google.com/drive/file"
  site:domain.com "drive.google.com/drive/u/0"
  site:domain.com "drive.google.com/drive/u/1"
  site:drive.google.com “Target” ```
  
- **Azure Blob Storage Exposure**    
  `site:blob.core.windows.net “Target”`
  
  `site:*.core.windows.net “Target”`  

- **DigitalOcean Spaces Exposure**  
  `site:digitaloceanspaces.com “Target”`

- **Amazon Dual stack Exposure**
  ```bash
  site:s3.dualstack.us-east-*.amazonaws.com
  site:s3.dualstack.ap-southeast-*.amazonaws.com
  site:*.s3.dualstack.us-west-*.amazonaws.com

  ```
- **Google Cloud Storage**  
  `site:firebasestorage.googleapis.com`  

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

- **High % inurl keyword**  
  `inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:Target`

- **Slack**  
  `site:domain.com "join.slack"`  
  `site:domain.com "join.slack ext:DIFF_FILE_EXT"`  


  - **Note**
    ```bash
    Reshuffle the terms according to your need
    ```
- **Terms to be added**  
`Confidential`, `Privileged`, `Internal Use Only`, `Not for Public Release`, `Restricted Access, Classified`, `Top Secret`, `Proprietary`, `Sensitive Information`, `For Internal Distribution`, `Eyes Only`, `Do Not Distribute`, `Confidential Information`, `For Authorized Personnel`, `Confidential Report`, `Private`, `Limited Access`, `Non-Disclosure`, `Secret`, `Restricted`, `Sensitive`, `For Official Use Only`, `Internal Memo`, `Secure`, `Private Use`, `Classified Information`, `Do Not Share`, `Restricted Distribution`, `Company Confidential`, `Not For External Distribution`, `Confidentiality Agreement`, `Internal Document`, `Company Secrets`, `Protected`, `For Authorized Use`, `Proprietary Information`, `Top-Secret`, `Limited Distribution`, `Non-Disclosure Agreement`, `For Internal Circulation`.

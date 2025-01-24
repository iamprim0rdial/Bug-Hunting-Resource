# Google Dorks for Security Testing

## **1. General Google Dorks**

- **GD SSRF**  
  `inurl:http | inurl:proxy= | inurl:html= | inurl:data= | inurl:resource= inurl:& site:Target`

- **GD High % Inurl Keywords**  
  `inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:Target`

- **GD Juicy Endpoints**  
  `site:Target ext:jsp | ext:asp | ext:aspx | ext:pl | ext:cfm | ext:py | ext:rb`

- **GD Sensitive Info**  
  `inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:Target`

- **GD XSS Parameters**  
  `inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:Target`

---

## **2. Cloud Storage & File Sharing Dorks**

- **Google Docs**  
  `site:docs.google.com inurl:”/d/” “Target”`

- **OneDrive**  
  `site:onedrive.live.com “Target”`

- **Dropbox**  
  `site:dropbox.com/s “Target”`

- **Box.com**  
  `site:box.com/s “Target”`

- **Dev Azure**  
  `site:dev.azure.com “Target”`

- **SSL Certificate Information**  
  `ssl.cert.subject.cn:target.com`

- **SSL Certificate Issuer Information**  
  `ssl.cert.issuer.cn:target.com`

- **Pastebin**  
  `site:pastebin.com “Target” api`

- **JSFiddle**  
  `site:jsfiddle.net “Target” api`

- **CodeBeautify**  
  `site:codebeautify.org “Target” api`

- **CodePen**  
  `site:codepen.io “Target” api`

---

## **3. Vulnerability & Exploitation Dorks**

- **XSS Prone Parameters**  
  `inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:Target`

- **SQL Injection (SQLi) Prone Parameters**  
  `inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:Target`

- **SSRF Prone Parameters**  
  `inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain= | inurl:page= inurl:& site:Target`

- **Remote Code Execution (RCE) Prone Parameters**  
  `inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read= | inurl:ping= inurl:& site:Target`

- **Local File Inclusion (LFI) Prone Parameters**  
  `inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= | inurl:& site:Target`

- **Open Redirect Prone Parameters**  
  `inurl:url | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= inurl:& inurl:http site:Target`

---

## **4. Code and Sensitive Data Exposure**

- **Exposed Code Leaks**  
  `site:pastebin.com “Target”`  
  `site:jsfiddle.net “Target”`  
  `site:codebeautify.org “Target”`  
  `site:codepen.io “Target”`

---

## **5. Cloud Storage Recon**

- **Amazon S3**  
  `site:s3.amazonaws.com “Target”`

- **Microsoft Azure Blob Storage**  
  `site:blob.core.windows.net “Target”`

- **Google APIs**  
  `site:googleapis.com “Target”`

- **Google Drive**  
  `site:drive.google.com “Target”`

- **Azure Dev**  
  `site:dev.azure.com “Target”`

- **OneDrive**  
  `site:onedrive.live.com “Target”`

- **DigitalOcean Spaces**  
  `site:digitaloceanspaces.com “Target”`

- **SharePoint**  
  `site:sharepoint.com “Target”`

- **AWS S3 External**  
  `site:s3-external-1.amazonaws.com “Target”`

- **S3 Dualstack**  
  `site:s3.dualstack.us-east-1.amazonaws.com “Target”`

- **Dropbox (File Share)**  
  `site:dropbox.com/s “Target”`

- **Box (File Share)**  
  `site:box.com/s “Target”`

- **Google Docs (File Share)**  
  `site:docs.google.com inurl:”/d/” “Target”`

---

## **6. Additional Dorks**

- **JFrog Artifactory**  
  `site:jfrog.io “Target”`

- **Firebase**  
  `site:firebaseio.com “Target”`

- **File Upload Endpoints**  
  `site:Target ”choose file”`

- **Broad Domain Search with Negative Keywords**  
  `site:Target -www -shop -share -ir -mfa`

- **PHP Extensions with Parameters**  
  `site:Target ext:php inurl:?`

- **Sensitive Parameters**  
  `inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:Target`

- **API Docs**  
  `inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api-explorer site:”Target”`

---

- **GitHub Dorks**:  
  `site:github.com "Target" inurl:secret`  
  `site:github.com "Target" inurl:token`  
  `site:github.com "Target" inurl:key`

- **Bug Bounty Platforms**:  
  `site:openbugbounty.org inurl:reports intext:”Target”`
  
---

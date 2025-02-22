# Default Directory Listing

```
http.html:"index of /"
```

# Backup Files

```
http.html:"index of /" http.html:"backup"
```

# Compressed Achives

```
http.html:"index of /" http.html:"tar.gz"
```

# Database Files

```
http.html:"index of /" http.html:"database"
http.html:"index of /" http.html:"sql.gz"
http.html:"index of /" http.html:".sql"
http.html:"index of /" http.html:".db"
http.html:"index of /" http.html:"db_backup"
http.html:"index of /" http.html:"mysql.dump"
http.html:"index of /" http.html:".mdb"
```

# Configuration Files

```
http.html:"index of /" http.html:".xml"
http.html:"index of /" http.html:"config.xml"

#tomcat: db connection strings
http.html:"index of /" http.html:"server.xml"
```

# Wordpress Configuration Files

```
http.html:"index of /" http.html:"wp-config.php.txt"
http.html:"index of /" http.html:"wp-config.txt"
http.html:"index of /" http.html:"wp-config.php.bak"
http.html:"index of /" http.html:"wp-config.php.old"
http.html:"index of /" http.html:"wp-config.php.backup"
http.html:"index of /" http.html:"wp-config.php.zip"
http.html:"index of /" http.html:"wp-config.php.tar.gz"
```

# Passwords

Passwords related to database, FTP, SSH, admin panel, email accounts, CMS login, network devices, RDP, VNC,etc…

```
http.html:"index of /" http.html:"pwd"
http.html:"index of /" http.html:"pass.txt"
http.html:"index of /" http.html:"password"
http.html:"index of /" http.html:"password.txt"
http.html:"index of /" http.html:"passwords.txt"
http.html:"index of /" http.html:"passwords.zip"
```

# Windows Server Config Files

Configuration file of Microsoft IIS Windows Server.

```
http.html:"index of /" http.html:"web.config"
```

# Exposed Logs

```
http.html:"index of /" http.html:".log"
http.html:"index of /" http.html:"access.log"
http.html:"index of /" http.html:"error.log"
http.html:"index of /" http.html:"php_error.log"
http.html:"index of /" http.html:"debug.log"
```

# Configuration and Version Control Files

**`.env` File**:
 This is a configuration file typically used in development environments
 to store sensitive environment variables. Commonly found in web 
applications, `.env` files may contain:

- **Database credentials** (username, password, host, and port)
- **API keys and tokens** for third-party services
- **Secret keys** for session handling or encryption
- **SMTP credentials** for email servers
- **Debugging and logging settings**

**`.svn` Directory**: This is a directory created by the Subversion (SVN) version control system. When exposed, it can leak:

- **Source code** and **historical versions** of files, revealing internal application logic
- **Commit messages** that may describe vulnerabilities or sensitive changes
- **Developer notes** that may include hardcoded credentials, server paths, or deployment details
- **File metadata** that can give attackers insight into the structure of the application and directories

```
http.html:"index of /" http.html:".env"
http.html:"index of /" http.html:".svn"
```

# Git Repositories

[Google Dork Alternative](https://www.youtube.com/watch?v=7QRH-SYprgk&list=PLqOQy6wxttBju5pKnatxQRY3fTejOkgZ9&index=2)

- **`.git` Directory**: Exposing the `.git` folder allows attackers to access the full codebase, commit history,
and branches, which can reveal sensitive information like hardcoded
credentials and the app’s internal logic.
- **`gitconfig` File**: This file contains Git configuration settings, user information, and possibly stored credentials

```
http.html:"index of /" http.html:".git"
http.html:"index of /" http.html:"gitconfig"
```

*Note:
 Shodan Database Results keeps changing from time to time , as it 
regularly scans the entire internet and picks up new devices , ports, 
and systems connected along with detailed device details with 
country,location,time and meta-data of it as well :)*

## DJANGO DROPLET

```
http.html:"Your Django Droplet"
```

## ONEINSTACK

```
http.html:"Congratulations, OneinStack installed successfully"
```

## GITEA INSTALLATION

```
http.html:"Installation - Gitea: Git with a cup of tea"
http.title:"Installation - Gitea: Git with a cup of tea"
```

## DIRECTORY BROWSING MODE

```
http.title:"directory browsing mode"
```

## CANNOT RESOLVE
```
http.title:"Cannot resolve"
http.html:"Cannot resolve"
```

**Source:[Abhirup Konwar ](https://osintteam.blog/shodan-secrets-hack-hidden-files-easily-94de007def73)**

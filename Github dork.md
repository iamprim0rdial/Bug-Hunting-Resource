### GitHub Dorks for Sensitive Information

```bash
1. `extension:pem private` -- [Private SSH Keys]  
2. `extension:sql mysql dump` -- [MySQL dumps]  
3. `extension:sql mysql dump password` -- [MySQL dumps with passwords]  
4. `filename:wp-config.php` -- [WordPress config file]  
5. `filename:.htpasswd` -- [.htpasswd]  
6. `filename:.git-credentials` -- [Git stored credentials]  
7. `filename:.bashrc password` -- [.bashrc files containing passwords]  
8. `filename:.bash_profile aws` -- [AWS keys in .bash_profile files]  
9. `extension:json mongolab.com` -- [Keys/Credentials for mongolab]  
10. `HEROKU_API_KEY language:json` -- [Heroku API Keys]  
11. `filename:filezilla.xml Pass` -- [FTP credentials]  
12. `filename:recentservers.xml Pass` -- [FTP credentials]  
13. `filename:config.php dbpasswd` -- [PHP Applications database credentials]  
14. `shodan_api_key language:python` -- [Shodan API Keys (try other languages)]  
15. `filename:logins.json` -- [Firefox saved password collection (key3.db usually in the same repo)]  
16. `filename:settings.py SECRET_KEY` -- [Django secret keys (usually allows for session hijacking, RCE, etc.)]  
17. `.mlab.com password` -- [Mlab database password]  
18. `access_key` -- [Exposed access keys]  
19. `access_token` -- [Exposed access tokens]  
20. `amazonaws` -- [Exposed AWS credentials]  
21. `api.googlemaps AIza` -- [Exposed Google Maps API key]  
22. `api_key` -- [Generic exposed API keys]  
23. `api_secret` -- [Exposed API secrets]  
24. `apidocs` -- [API documentation potentially exposing keys]  
25. `apikey` -- [Exposed API key]  
26. `apiSecret` -- [Exposed API secret]  
27. `app_key` -- [Exposed application key]  
28. `app_secret` -- [Exposed application secret]  
29. `appkey` -- [Exposed app key]  
30. `appkeysecret` -- [Exposed app key secret]  
31. `application_key` -- [Exposed application key]  
32. `appsecret` -- [Exposed application secret]  
33. `appspot` -- [Exposed Google App Engine keys]  
34. `auth` -- [Exposed authentication tokens]  
35. `auth_token` -- [Exposed authentication token]  
36. `authorizationToken` -- [Exposed authorization tokens]  
37. `aws_access` -- [Exposed AWS access keys]  
38. `aws_access_key_id` -- [AWS access key ID]  
39. `aws_key` -- [AWS access key]  
40. `aws_secret` -- [AWS secret key]  
41. `aws_token` -- [AWS tokens]  
42. `AWSSecretKey` -- [AWS secret keys]  
43. `bashrc password` -- [.bashrc files with passwords]  
44. `bucket_password` -- [AWS bucket password]  
45. `client_secret` -- [Client secret keys]  
46. `cloudfront` -- [AWS CloudFront credentials]  
47. `codecov_token` -- [Codecov API token]  
48. `config` -- [Configuration files potentially containing secrets]  
49. `conn.login` -- [Connection login credentials]  
50. `connectionstring` -- [Database connection strings]  
51. `consumer_key` -- [Consumer API keys]  
52. `credentials` -- [Exposed credentials]  
53. `database_password` -- [Database passwords]  
54. `db_password` -- [Database passwords]  
55. `db_username` -- [Database usernames]  
56. `dbpasswd` -- [Database passwords]  
57. `dbpassword` -- [Database passwords]  
58. `dbuser` -- [Database user information]  
59. `dot-files` -- [Exposed dotfiles]  
60. `dotfiles` -- [Exposed dotfiles]  
61. `encryption_key` -- [Encryption keys]  
62. `fabricApiSecret` -- [Fabric API secret]  
63. `fb_secret` -- [Facebook secrets]  
64. `firebase` -- [Firebase credentials]  
65. `ftp` -- [FTP credentials]  
66. `gh_token` -- [GitHub tokens]  
67. `github_key` -- [GitHub API key]  
68. `github_token` -- [GitHub API token]  
69. `gitlab` -- [GitLab credentials]  
70. `gmail_password` -- [Gmail account password]  
71. `gmail_username` -- [Gmail username]  
72. `herokuapp` -- [Heroku application credentials]  
73. `internal` -- [Internal credentials]  
74. `irc_pass` -- [IRC server passwords]  
75. `JEKYLL_GITHUB_TOKEN` -- [Jekyll GitHub token]  
76. `key` -- [Exposed keys]  
77. `keyPassword` -- [Exposed key passwords]  
78. `ldap_password` -- [LDAP passwords]  
79. `ldap_username` -- [LDAP usernames]  
80. `login` -- [Login credentials]  
81. `mailchimp` -- [Mailchimp API credentials]  
82. `mailgun` -- [Mailgun API credentials]  
83. `master_key` -- [Master keys]  
84. `mydotfiles` -- [Exposed dotfiles]  
85. `mysql` -- [MySQL credentials]  
86. `node_env` -- [Node.js environment variables]  
87. `npmrc _auth` -- [NPM authentication token]  
88. `oauth_token` -- [OAuth tokens]  
89. `pass` -- [Passwords]  
90. `passwd` -- [Password files]  
91. `password` -- [Password files or strings]  
92. `passwords` -- [Exposed passwords]  
93. `pem private` -- [Private PEM files]  
94. `preprod` -- [Pre-production keys or credentials]  
95. `private_key` -- [Private keys]  
96. `prod` -- [Production credentials]  
97. `pwd` -- [Password files]  
98. `pwds` -- [Passwords]  
99. `rds.amazonaws.com password` -- [Amazon RDS credentials]  
100. `redis_password` -- [Redis password]  
101. `root_password` -- [Root password]  
102. `secret` -- [Exposed secret tokens or values]  
103. `secret.password` -- [Exposed password secrets]  
104. `secret_access_key` -- [Secret access keys]  
105. `secret_key` -- [Secret keys]  
106. `secret_token` -- [Secret tokens]  
107. `secrets` -- [General secret files]  
108. `secure` -- [Secure key or token]  
109. `security_credentials` -- [Security credentials]  
110. `send.keys` -- [Send key files]  
111. `send_keys` -- [Send keys]  
112. `sendkeys` -- [Send key files]  
113. `SF_USERNAME salesforce` -- [Salesforce username]  
114. `sf_username` -- [Salesforce username]  
115. `site.com FIREBASE_API_JSON=` -- [Exposed Firebase API JSON]  
116. `site.com vim_settings.xml` -- [Vim settings files with sensitive information]  
117. `slack_api` -- [Slack API keys]  
118. `slack_token` -- [Slack tokens]  
119. `sql_password` -- [SQL password]  
120. `ssh` -- [SSH credentials]  
121. `ssh2_auth_password` -- [SSH authentication password]  
122. `sshpass` -- [SSH password exposed]  
123. `staging` -- [Staging environment credentials]  
124. `stg` -- [Staging credentials]  
125. `storePassword` -- [Stored passwords]  
126. `stripe` -- [Stripe API keys]  
127. `swagger` -- [Swagger credentials]  
128. `testuser` -- [Test user credentials]  
129. `token` -- [API token]  
130. `x-api-key` -- [API key exposed]  
131. `xoxb` -- [Slack Bot token]  
132. `xoxp` -- [Slack User token]  
133. `[WFClient] Password=` extension:ica -- [WF Client password in ICA extension]  
134. `access_key` -- [Exposed access keys]  
135. `bucket_password` -- [Bucket password]  
136. `dbpassword` -- [Database password]  
137. `dbuser` -- [Database username]  
138. `extension:avastlic support.avast.com` -- [Avast license file]  
139. `extension:bat` -- [Batch files containing passwords or sensitive info]  
140. `extension:cfg` -- [Configuration files exposing sensitive info]  
141. `extension:env` -- [Environment configuration files exposing secrets]  
142. `extension:exs` -- [Elixir configuration files]  
143. `extension:ini` -- [INI configuration files]  
144. `extension:json api.forecast.io` -- [Forecast.io API credentials]  
145. `extension:json googleusercontent client_secret` -- [Google API client secrets]  
146. `extension:json mongolab.com` -- [Mongolab API keys]  
147. `extension:pem` -- [PEM files containing private keys]  
148. `extension:pem private` -- [Private PEM keys]  
149. `extension:ppk` -- [Putty private keys]  
150. `extension:ppk private` -- [Private Putty key files]  
151. `extension:properties` -- [Java property files exposing secrets]  
152. `extension:sh` -- [Shell script files exposing credentials]  
153. `extension:sls` -- [Serverless configuration files exposing secrets]  
154. `extension:sql` -- [SQL files containing sensitive information]  
155. `extension:sql mysql dump` -- [MySQL dump files exposing credentials]  
156. `extension:yaml mongolab.com` -- [MongoLab YAML configuration files]  
157. `extension:zsh` -- [Zsh configuration files exposing secrets]  
158. `filename:.bash_history DOMAIN-NAME` -- [Bash history containing domain info]  
159. `filename:.bash_profile aws` -- [AWS credentials in bash profile]  
160. `filename:.bashrc mailchimp` -- [Mailchimp credentials in .bashrc]  
161. `filename:.bashrc password` -- [Passwords in .bashrc]  
162. `filename:.cshrc` -- [C shell configuration files with credentials]  
163. `filename:.dockercfg auth` -- [Docker authentication credentials]  
164. `filename:.env DB_USERNAME NOT homestead` -- [Exposed database username in .env file]  
165. `filename:.env MAIL_HOST=smtp.gmail.com` -- [Gmail SMTP credentials in .env]  
166. `filename:.esmtprc password` -- [Email configuration with passwords]  
167. `filename:.ftpconfig` -- [FTP configuration files exposing credentials]  
168. `filename:.git-credentials` -- [Git credentials]  
169. `filename:.history` -- [Command history files exposing sensitive data]  
170. `filename:.htpasswd` -- [.htpasswd file containing credentials]  
171. `filename:.netrc password` -- [NetRC files with passwords]  
172. `filename:.npmrc _auth` -- [NPM authentication files with credentials]  
173. `filename:.pgpass` -- [PostgreSQL password file]  
174. `filename:.remote-sync.json` -- [Remote sync configuration files exposing passwords]  
175. `filename:.s3cfg` -- [Amazon S3 configuration files with credentials]  
176. `filename:.sh_history` -- [Shell history files exposing credentials]  
177. `filename:.tugboat NOT _tugboat` -- [Tugboat config files exposing sensitive data]  
178. `filename:_netrc password` -- [Exposed NetRC password]  
179. `filename:apikey` -- [API key files]  
180. `filename:bash` -- [Bash configuration files with credentials]  
181. `filename:gitconfig` -- [Git configuration files exposing sensitive data]  
182. `filename:global` -- [Global configuration files with secrets]  
183. `filename:history` -- [Shell command history files exposing sensitive data]  
```
---

**info**
```
- PASSWORD
- PWD
- KEY
- API
- TOKEN
- ACCESS_TOKEN
- SECRETKEY
- CLIENT-SECRET
- CLIENT_SECRET
- SECRET@target.com
- DEV
- PROD
- JENKINS
- CONFIG
- SSH
- FTP
- MYSQL
- ADMIN
- AWS
- DASHBOARD
- BUCKET
- ST NO
- CVV
- GITHUB_TOKEN
- =http
- OTP
- OAUTH
- AUTHORIZATION
- LDAP
- INTERNAL
- language:sql
- language:json
- language:txt
```
**Note**: All we need to do is search for these keywords in GitHub after "target.com". For example, to look for passwords, we can search **` "target.com" password `** or **` "target.com" pwd `** in GitHub. These dorks are intended to aid you in the search for sensitive files or credentials that might have accidentally been leaked on GitHub. Always ensure that your sensitive data is not committed to public repositories in order to avoid security vulnerabilities.

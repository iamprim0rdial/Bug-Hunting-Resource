### GitHub Dorks for Sensitive Information

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
17. `extension:env API_KEY` -- [Exposed environment configuration files containing API keys]  
18. `extension:json private_key` -- [Exposed private keys in JSON files]  
19. `filename:docker-compose.yml password` -- [Docker Compose files with password credentials]  
20. `extension:log password` -- [Log files that may contain sensitive data like passwords]  
21. `filename:config.json dbpassword` -- [Configuration files containing database passwords]  
22. `filename:.gitmodules` -- [Git submodule configuration file that may expose private repos or keys]  
23. `filename:server_config.yaml api_key` -- [Server configuration files with exposed API keys]  
24. `filename:server.conf password` -- [Server configuration files containing passwords]  
25. `filename:credentials.json` -- [Google Cloud credentials exposed in JSON files]  
26. `extension:csv credit_card` -- [CSV files containing credit card information]  

---



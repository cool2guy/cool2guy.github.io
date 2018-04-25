---
layout: post
title: set up mariadb
---

1 Check Config of mariadb 
- /etc/my.cnf
- /etc/my.cnf.d/server.cnf
  Change #max_connections, wait_timeout
---  
  [mariadb]
  max_connections=500
  wait_timeout=60
---

2. Host 'xxx.xxx.xxx.xxx' is not allowed to connect to this MariaDB server
- mysql -u root  :   -- Log on root 
- insert into mysql.user (Host, User, Password, ssl_cipher, x509_issuer, x509_subject, authentication_string) values('%','root', password('ROOT_USER_PWD'),'','','','');
- grant all privileges on *.* 
- flush privileges;

3.1. CREATE DATABASE
CREATE DATABASE `DATABASE_NAME` /*!40100 COLLATE 'utf8_unicode_ci' */;
//grant all privileges on *.* to 'root'@'%' with grant option;
flush privileges;

-- CREATE ACCESS USERS 
root	  	ROOT_USER_PWD
DEV_USER	DEV_USER_PWD
WEB_USER	WEB_USER_PWD




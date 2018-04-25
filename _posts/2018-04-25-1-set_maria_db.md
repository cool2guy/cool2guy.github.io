---
layout: post
title: First Step !
---

How to set up mariadb

1 Check Config of mariadb 
- /etc/my.cnf
- /etc/my.cnf.d/server.cnf
  [mariadb]
  # Change #max_connections, wait_timeout
  max_connections=500
  wait_timeout=60

2. Host 'xxx.xxx.xxx.xxx' is not allowed to connect to this MariaDB server
- mysql -u root  :   -- Log on root 
- insert into mysql.user (Host, User, Password, ssl_cipher, x509_issuer, x509_subject, authentication_string) values('%','root', password('ROOT_PASS_WORD'),'','','','');
- grant all privileges on *.* 
- flush privileges;

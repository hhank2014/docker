centos mysqld services

#create a centos  6.5 sshd images

docker build -t 192.168.221.100:5000/centos:mysql .

# docker images
# docker images
REPOSITORY                      TAG                 IMAGE ID            CREATED             SIZE
192.168.221.100:5000/centos     mysql               6f698e8c0242        8 minutes ago       1.06 GB

docker run -d -P --name mysql 192.168.221.100:5000/centos:mysql

# docker ps -a
# docker ps -a
CONTAINER ID        IMAGE                               COMMAND                  CREATED             STATUS              PORTS                                            NAMES
b7dbb0c5b6ea        192.168.221.100:5000/centos:mysql   "/run.sh"                5 minutes ago       Up 5 minutes        0.0.0.0:32805->22/tcp, 0.0.0.0:32804->3306/tcp   mysql

# ssh 127.0.0.1 -p 32805
[root@b7dbb0c5b6ea ~]# 

# mysql -h 192.168.221.100 -u hank -p -P 32804
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 5
Server version: 5.6.34 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 


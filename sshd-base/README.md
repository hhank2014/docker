centos sshd services

#create a centos  6.5 sshd images

docker build -t sshd .

# docker images
REPOSITORY                      TAG                 IMAGE ID            CREATED             SIZE
sshd                            latest              bcf8959350d4        3 minutes ago       829.9 MB

docker run -d -P sshd

# docker ps -a
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                         PORTS                    NAMES
263f50de7003        sshd                              "/run.sh"                3 minutes ago       Up 3 minutes                   0.0.0.0:32770->22/tcp    fervent_varahamihira

# ssh 127.0.0.1 -p 32770
Last login: Sat Oct 22 10:55:40 2016 from 172.17.0.1
[root@263f50de7003 ~]# 

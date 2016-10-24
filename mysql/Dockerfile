from 192.168.221.100:5000/centos:sshd
MAINTAINER @gmail.com

ENV TZ "Asia/Shanghai"

RUN rpm -ivh http://repo.mysql.com/yum/mysql-5.6-community/el/7/x86_64/mysql-community-release-el7-5.noarch.rpm && \
    yum install -y mysql-community-server.x86_64 mysql-community-client.x86_64 mysql-community-devel.x86_64 && \
    yum clean all

RUN mkdir -p /root/.ssh
ADD authorized_keys /root/.ssh/authorized_keys

ADD run.sh /run.sh
RUN chmod +x /run.sh

EXPOSE 3306
#CMD ["/usr/bin/mysql_install_db", "--user=mysql","/usr/bin/mysqld_safe &","/usr/sbin/sshd","-D"]
CMD ["/run.sh"]

from 192.168.221.100:5000/centos:sshd
MAINTAINER @gmail.com

ENV TZ "Asia/Shanghai"

#RUN yum install -y curl wget tar bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \
#    yum install -y gcc gcc-c++ git make automake cmake patch logrotate openssl-devel&& \
#    rpm  -ivh http://nginx.org/packages/mainline/centos/7/x86_64/RPMS/nginx-1.9.0-1.el7.ngx.x86_64.rpm && \
#    yum clean all

RUN mkdir -p /root/.ssh
ADD authorized_keys /root/.ssh/authorized_keys

RUN yum install -y php php-fpm && \
    yum clean all 

ADD run.sh /run.sh
RUN chmod +x /run.sh

EXPOSE 22 9000

CMD ["/run.sh"]

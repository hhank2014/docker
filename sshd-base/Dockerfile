from 192.168.221.100:5000/centos:6.5
MAINTAINER huang.jie.yellow@gmail.com

ENV TZ "Asia/Shanghai"

RUN yum install -y curl wget tar bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \
    yum install -y gcc gcc-c++ git make automake cmake patch logrotate python-devel libpng-devel libjpeg-devel && \
    yum clean all 

RUN mkdir -p /var/run/sshd
RUN mkdir -p /root/.ssh

ADD authorized_keys /root/.ssh/authorized_keys
ADD run.sh /run.sh
RUN chmod +x /run.sh

EXPOSE 22

CMD ["/run.sh"]

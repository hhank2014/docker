from 192.168.221.100:5000/centos:sshd
MAINTAINER @gmail.com

ENV TZ "Asia/Shanghai"

RUN mkdir -p /root/.ssh
ADD authorized_keys /root/.ssh/authorized_keys
ADD nginx.repo /etc/yum.repos.d/nginx.repo
ADD nginx_signing.key /tmp/nginx_signing.key

RUN rpm --import /tmp/nginx_signing.key && \
    yum install -y nginx && \
    yum clean all 

ADD nginx.conf /etc/nginx/nginx.conf
ADD run.sh /run.sh
RUN chmod +x /run.sh

#VOLUME ["/usr/share/nginx/html"]
COPY "www" "/usr/share/nginx/html"

EXPOSE 22 80 443

CMD ["/run.sh"]

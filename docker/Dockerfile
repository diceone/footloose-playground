FROM quay.io/footloose/centos7

LABEL com.owner="www.dev-ops.de" \
      com.version="0.1.3"

RUN yum update -y && yum install -y epel-release && yum install -y vim netstat htop lsof rsync screen telnet ncdu nmap wget && yum clean all
RUN mkdir -p /www/bin
COPY config/bashrc /root/.bashrc
RUN rm -f /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Berlin /etc/localtime

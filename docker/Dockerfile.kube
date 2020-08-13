FROM quay.io/footloose/centos7

LABEL com.owner="www.dev-ops.de" \
      com.version="0.1.5"

RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl &&  chmod +x ./kubectl && mv ./kubectl /usr/local/bin/kubectl

RUN yum update -y && yum install -y epel-release && yum install -y kubectl vim netstat htop lsof rsync screen telnet ncdu nmap wget httpd-tools && yum clean all
RUN wget https://storage.googleapis.com/kubernetes-helm/helm-v2.12.2-linux-amd64.tar.gz
RUN tar -zxvf helm-v2.12.2-linux-amd64.tar.gz
RUN mv linux-amd64/helm /usr/local/bin/helm2 && mv linux-amd64/tiller /usr/local/bin/tiller
RUN wget https://get.helm.sh/helm-v3.3.0-rc.2-linux-amd64.tar.gz && tar -zxvf helm-v3.3.0-rc.2-linux-amd64.tar.gz  && mv linux-amd64/helm /usr/local/bin/helm
RUN yum install -y https://github.com/cdr/code-server/releases/download/3.4.1/code-server-3.4.1-amd64.rpm
RUN mkdir -p /www/bin
COPY config/bashrc /root/.bashrc
COPY config/code-server.service /lib/systemd/system/code-server.service
RUN systemctl enable code-server
RUN rm -f /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Berlin /etc/localtime

EXPOSE 8080 443

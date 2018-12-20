FROM centos/systemd:latest

COPY ./src /src

WORKDIR /src

RUN yum -y update
RUN yum -y install http://rpms.famillecollet.com/enterprise/remi-release-7.rpm \
  && yum -y install --enablerepo=remi-php73 php php-cli php-common php-devel php-mbstring php-pear php-pecl-apcu php-soap php-xml php-xmlrpc php-zip

RUN yum -y install httpd httpd-devel \
  && yum clean all \
  && systemctl enable httpd.service

COPY ./httpd.conf /etc/httpd/conf/httpd.conf

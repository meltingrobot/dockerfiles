# Version 0.0.1
FROM centos:latest
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN yum -y update
RUN yum -y install epel-release
RUN yum -y localinstall https://labs.consol.de/repo/stable/rhel7/i386/labs-consol-stable.rhel7.noarch.rpm
RUN yum -y install mod_ssl naemon nagios-plugins-all postfix
RUN chmod u+s /usr/bin/ping
RUN echo "Hello World" > /var/www/html/index.html
RUN /usr/bin/newaliases
RUN mkdir /root/bin
RUN echo "/usr/sbin/postfix start" >> /root/.bashrc
RUN echo "/usr/sbin/apachectl" >> /root/.bashrc
RUN echo "/usr/bin/naemon /etc/naemon/naemon.cfg" >> /root/.bashrc
CMD [ "/bin/bash" ]
EXPOSE 80
EXPOSE 443

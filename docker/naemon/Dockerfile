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
RUN echo "#!/bin/bash" > /root/bin/startnaemon.sh
RUN echo "/usr/sbin/postfix start" >> /root/bin/startnaemon.sh
RUN echo "/usr/sbin/apachectl" >> /root/bin/startnaemon.sh
RUN echo "/usr/bin/naemon -d /etc/naemon/naemon.cfg" >> /root/bin/startnaemon.sh
RUN chmod ug+x /root/bin/startnaemon.sh
CMD [ "/bin/bash" ]
EXPOSE 80
EXPOSE 443

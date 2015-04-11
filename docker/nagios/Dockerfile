# Version 0.0.1
FROM centos:latest
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN yum -y update
RUN yum -y install epel-release
RUN yum -y install mod_ssl nagios nagios-plugins-all
RUN touch /var/run/nagios.pid
RUN chown nagios.nagios /var/run/nagios.pid
RUN chmod u+s /usr/bin/ping
RUN echo "Hello World" > /var/www/html/index.html
#RUN /usr/sbin/apachectl
#RUN /usr/sbin/nagios -d /etc/nagios/nagios.cfg
EXPOSE 80
EXPOSE 443

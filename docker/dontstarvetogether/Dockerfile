# Version 0.0.1
FROM centos:latest
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN yum -y update
RUN yum -y install libcurl.i686 libgcc.i686 glibc.i686 tar wget
RUN mkdir /root/dontstarvetogether
RUN cd /root
RUN wget http://media.steampowered.com/installer/steamcmd_linux.tar.gz
RUN tar -xvzf steamcmd_linux.tar.gz
RUN ln -s /usr/lib/libcurl.so.4 /usr/lib/libcurl-gnutls.so.4
RUN ./steamcmd.sh +login anonymous +force_install_dir /root/dontstarvetogether +app_update 343050 -validate +quit
CMD [ "/bin/bash" ]
EXPOSE 10999/udp

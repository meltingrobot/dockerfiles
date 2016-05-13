# Version 0.0.1
FROM docker.io/ubuntu:14.04
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN echo "deb http://us.archive.ubuntu.com/ubuntu/ trusty-backports main restricted universe multiverse" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y dist-upgrade
RUN apt-get -y install language-pack-en
RUN update-locale LANG=en_US.UTF-8
RUN apt-get -y install software-properties-common wget
RUN add-apt-repository ppa:libreoffice/libreoffice-4-4
RUN add-apt-repository ppa:mc3man/trusty-media
RUN wget http://ubuntu.bigbluebutton.org/bigbluebutton.asc -O- | sudo apt-key add -
RUN echo "deb http://ubuntu.bigbluebutton.org/trusty-1-0/ bigbluebutton-trusty main" | tee /etc/apt/sources.list.d/bigbluebutton.list
RUN apt-get update
RUN apt-get -y install build-essential git-core checkinstall yasm texi2html libvorbis-dev libx11-dev libvpx-dev libxfixes-dev zlib1g-dev pkg-config netcat libncurses5-dev ffmpeg
RUN apt-get -y install bigbluebutton bbb-demo bbb-web bbb-check || true
RUN bbb-conf --enablewebrtc
CMD [ "/bin/bash", "-c", "apt-get -y dist-upgrade;/usr/bin/bbb-conf --clean;tail -f /var/log/bigbluebutton/*.log" ]
VOLUME /etc/nagios
VOLUME /etc/httpd
EXPOSE 80
EXPOSE 1935
EXPOSE 9123

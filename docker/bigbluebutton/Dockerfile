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
RUN wget http://ubuntu.bigbluebutton.org/bigbluebutton.asc -O- | sudo apt-key add -
RUN echo "deb http://ubuntu.bigbluebutton.org/trusty-1-0/ bigbluebutton-trusty main" | tee /etc/apt/sources.list.d/bigbluebutton.list
RUN apt-get update
RUN apt-get -y install build-essential git-core checkinstall yasm texi2html libvorbis-dev libx11-dev libvpx-dev libxfixes-dev zlib1g-dev pkg-config netcat libncurses5-dev
RUN cd /usr/local/src;wget "http://ffmpeg.org/releases/ffmpeg-2.3.3.tar.bz2";tar -xvjf ffmpeg-2.3.3.tar.bz2
RUN cd /usr/local/src/ffmpeg-2.3.3;./configure --enable-version3 --enable-postproc --enable-libvorbis --enable-libvpx;make
RUN cd /usr/local/src/ffmpeg-2.3.3;checkinstall --pkgname=ffmpeg --pkgversion="5:2.3.3" --backup=no --deldoc=yes --default
RUN apt-get -y install bigbluebutton bbb-demo bbb-check
RUN bbb-conf --enablewebrtc;bbb-conf --clean
CMD [ "/bin/bash", "-c", "/usr/bin/yum -y update;/usr/bin/yum -y install httpd fping;/usr/sbin/apachectl;/usr/sbin/postfix start;/usr/sbin/nagios /etc/nagios/nagios.cfg" ]
VOLUME /etc/nagios
VOLUME /etc/httpd
EXPOSE 80
EXPOSE 1935
EXPOSE 9123

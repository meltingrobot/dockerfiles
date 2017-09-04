# Version 0.0.2
FROM fedora:latest
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN yum -y update
RUN wget http://download.sonarr.tv/v2/master/mono/NzbDrone.master.tar.gz
RUN tar -xvf ~/NzbDrone.master.tar.gz -C /opt/
RUN yum install mediainfo libzen libmediainfo curl gettext mono-opt mono-opt-devel sqlite.x86_64
CMD [ "/bin/bash", "-c", "/opt/mono/bin/mono /opt/NzbDrone/NzbDrone.exe -nobrowser -data /opt/NzbDrone" ]
VOLUME /opt/NzbDrone
EXPOSE 8989

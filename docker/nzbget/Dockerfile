# Version 0.0.1
FROM fedora:latest
MAINTAINER Roy P "meltingrobot@gmail.com"
RUN dnf -y update
RUN dnf -y install wget
RUN wget https://nzbget.net/download/nzbget-latest-bin-linux.run
RUN chmod +x nzbget-latest-bin-linux.run
RUN sh nzbget-latest-bin-linux.run --destdir /opt/nzbget
RUN echo "export TERM=xterm" >> /root/.bashrc
CMD [ "/bin/bash", "-c", "/opt/nzbget/nzbget -s" ]
VOLUME /opt/nzbget
EXPOSE 6789

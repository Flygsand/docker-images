FROM ubuntu:trusty
MAINTAINER protomouse <root@protomou.se>

RUN apt-get -y update \
 && apt-get -y install wget \
 && wget -P /tmp https://downloads.plex.tv/plex-media-server/1.0.0.2261-a17e99e/plexmediaserver_1.0.0.2261-a17e99e_amd64.deb \
 && wget -O /usr/local/bin/gosu https://github.com/tianon/gosu/releases/download/1.9/gosu-amd64 \
 && chmod +x /usr/local/bin/gosu \
 && dpkg -i /tmp/plexmediaserver*.deb \
 && mkdir /data \
 && chown plex:plex /data \
 && apt-get -y purge wget \
 && apt-get -y autoremove \
 && apt-get -y clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
ADD runner /

EXPOSE 32400
ENTRYPOINT ["/runner"]

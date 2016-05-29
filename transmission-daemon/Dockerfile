FROM alpine:edge
MAINTAINER protomouse <root@protomou.se>

RUN apk -Uv add transmission-daemon su-exec openssl \
 && wget -O /usr/local/bin/confd https://github.com/kelseyhightower/confd/releases/download/v0.12.0-alpha3/confd-0.12.0-alpha3-linux-amd64 \
 && chmod +x /usr/local/bin/confd \
 && mkdir /downloads /incomplete \
 && chown transmission /downloads /incomplete \
 && apk --purge -v del openssl \
 && rm -rf /var/cache/apk/*
ADD runner /
ADD confd /etc/confd

VOLUME /var/lib/transmission
EXPOSE 9001 51413 51413/udp
ENTRYPOINT ["/runner"]

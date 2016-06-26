FROM alpine:3.4
MAINTAINER protomouse <root@protomou.se>

RUN apk -Uv add znc znc-extra su-exec \
 && rm -rf /var/cache/apk/*
ADD etc/confd /etc/confd
ADD bin/confd /usr/local/bin/confd
ADD runner /

EXPOSE 6667 6697 8080
ENTRYPOINT ["su-exec", "znc", "/runner"]

FROM python:2-alpine
MAINTAINER protomouse <root@protomou.se>

RUN pip install flexget transmissionrpc

USER nobody
ENTRYPOINT ["/usr/local/bin/flexget", "--logfile", "/dev/null"]

# Dockerfile for ELK stack
# Kibana 7.13.0

FROM docker.elastic.co/kibana/kibana:7.13.0-arm64
ARG ELK_VERSION=7.13.0
LABEL org.opencontainers.image.source=https://github.com/Pyhass/Addons

### Kibana config
ENV ES_CONF=/usr/share/kibana/config \
    logger.level=WARN


COPY kibana.yml ${ES_CONF}/kibana.yml

EXPOSE 5601

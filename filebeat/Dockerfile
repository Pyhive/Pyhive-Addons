# Dockerfile for ELK stack
# Elasticsearch, Logstash, Kibana 7.12.0

FROM elasticsearch:7.13.0-arm64
ARG ELK_VERSION=7.13.0
LABEL org.opencontainers.image.source=https://github.com/Pyhass/Addons

### Elasticsearch config
ENV ES_PATH_CONF=/etc/elasticsearch/
COPY elasticsearch.yml ${ES_PATH_CONF}


EXPOSE 9200
VOLUME /data

CMD [ "/usr/local/bin/start.sh" ]

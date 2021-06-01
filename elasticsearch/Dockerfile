# Dockerfile for ELK stack
# Elasticsearch, Logstash, Kibana 7.12.0



FROM docker.elastic.co/elasticsearch/elasticsearch:7.13.0-arm64
ARG ELK_VERSION=7.13.0
LABEL org.opencontainers.image.source=https://github.com/Pyhass/Addons

### Elasticsearch config
ENV ES_CONF=/usr/share/elasticsearch/config \
    ES_HOME=/opt/elasticsearch

COPY elasticsearch.yml ${ES_CONF}/elasticsearch.yml
COPY jvm.options ${ES_CONF}/jvm.options
COPY jvm.options.d/jvm.options ${ES_CONF}/jvm.options.d/jvm.options

EXPOSE 9200


# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]



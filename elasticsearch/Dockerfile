# Dockerfile for ELK stack
# Elasticsearch, Logstash, Kibana 7.12.0

FROM docker.elastic.co/elasticsearch/elasticsearch:7.13.0-arm64
ARG ELK_VERSION=7.13.0
LABEL org.opencontainers.image.source=https://github.com/Pyhass/Addons

### Elasticsearch config
ENV ES_CONF=/etc/elasticsearch \
    ES_HOME=/opt/elasticsearch \
    ES_GID=991 \
    ES_UID=991

COPY elasticsearch.yml ${ES_PATH_CONF}/elasticsearch.yml
COPY jvm.options ${ES_PATH_CONF}/jvm.options
COPY jvm.options.d/jvm.options ${ES_PATH_CONF}/jvm.options.d/jvm.options

RUN mkdir ${ES_HOME} \
    && groupadd -r elasticsearch -g ${ES_GID} \
    && useradd -r -s /usr/sbin/nologin -M -d ${ES_HOME} -c "Elasticsearch service user" -u ${ES_UID} -g elasticsearch elasticsearch \
    && chown -R elasticsearch:elasticsearch ${ES_HOME}  ${ES_CONF}

EXPOSE 9200



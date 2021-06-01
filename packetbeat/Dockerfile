# Dockerfile for ELK stack
# Elasticsearch, Logstash, Kibana 7.12.0

FROM docker.elastic.co/beats/packetbeat:7.13.0-arm64
ARG ELK_VERSION=7.13.0
LABEL org.opencontainers.image.source=https://github.com/Pyhass/Addons

### Elasticsearch config
ENV ES_CONF=/usr/share/packetbeat \
    setup.kibana.host=192.168.0.111:5601  \
    output.elasticsearch.hosts=["localhost:9200"]
COPY packetbeat.yml ${ES_CONF}/packetbeat.yml

# Modified from eclipse-mosquitto dockerfile:
# https://github.com/eclipse/mosquitto/blob/0bb602ed7a89da80d25e6b959a130fdcf0556be5/docker/1.4.12/Dockerfile
# to include mosquitto-clients

FROM alpine:latest
MAINTAINER Aephir <aephirone@gmail.com>

LABEL Description="Eclipse Mosquitto MQTT Broker and clients"

RUN apk --no-cache add mosquitto && \
    apk --no-cache add mosquitto-clients && \
    mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log && \
    cp /etc/mosquitto/mosquitto.conf /mosquitto/config/mosquitto.conf && \
    chown -R mosquitto:mosquitto /mosquitto

COPY docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]

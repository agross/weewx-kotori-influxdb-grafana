FROM jgoerzen/weewx

LABEL maintainer="Alexander Groß <agross@therightstuff.de>"

RUN apt-get update \
    && \
    apt-get install \
            --yes \
            python-pip \
    && \
    pip install paho-mqtt \
    && \
    apt-get clean \
    && \
    rm -rf /var/lib/apt/lists/* \
    && \
    wget --output-document=weewx-mqtt.tgz \
         http://lancet.mit.edu/mwall/projects/weather/releases/weewx-mqtt-0.19.tgz \
    && \
    wee_extension --install weewx-mqtt.tgz \
    && \
    rm weewx-mqtt.tgz

CMD [ "/usr/bin/weewxd", "/etc/weewx/weewx.conf", "--loop-on-init" ]

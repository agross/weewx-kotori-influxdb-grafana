FROM grafana/grafana

LABEL maintainer="Alexander Groß <agross@therightstuff.de>"

USER root

RUN apk add \
        --no-cache \
        git \
    && \
    git clone \
        --depth 1 \
        https://github.com/spectraphilic/grafana-windrose.git \
        /var/lib/grafana/plugins/grafana-windrose \
    && \
    git clone \
        --depth 1 \
        https://github.com/ne0x/grafana-windrose-panel.git \
        /var/lib/grafana/plugins/n-grafana-windrose-panel \
    && \
    sed --in-place \
        's/ksz-wind-rose-panel/n-wind-rose-panel/' \
        /var/lib/grafana/plugins/n-grafana-windrose-panel/dist/plugin.json

USER grafana
FROM python:2.7

LABEL maintainer="Alexander Groß <agross@therightstuff.de>"

RUN apt-get update \
    && \
    apt-get install \
            --yes \
            build-essential \
            libffi-dev \
            libssl-dev \
            python-dev \
            python-pip \
    && \
    apt-get clean \
    && \
    rm -rf /var/lib/apt/lists/* \
    && \
    pip install https://github.com/jjmalina/pyinfluxql/tarball/master \
    && \
    pip install kotori[daq,export]

EXPOSE 24642

CMD [ "/usr/local/bin/kotori", "--config=/kotori/kotori.ini" ]

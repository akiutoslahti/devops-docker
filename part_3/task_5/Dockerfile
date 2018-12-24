FROM alpine:edge

WORKDIR /videos

RUN apk add --update python2 py2-pip py-crypto py-lxml gcc libc-dev \
    wget ffmpeg php5 php5-bcmath php5-curl php5-xml \
    && pip install yle-dl \
    && apk del gcc libc-dev \
    && adduser -D videos \
    && chown videos:videos /videos

USER videos

ENTRYPOINT ["/usr/bin/yle-dl"]

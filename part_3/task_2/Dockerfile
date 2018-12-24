FROM ubuntu:18.04

ENV TZ=Europe/Helsinki

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
    && apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y \
        python python-pip python-crypto wget ffmpeg \
        php-cli php-bcmath php-curl php-xml \
    && pip install yle-dl \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean -y

WORKDIR /videos

ENTRYPOINT ["/usr/local/bin/yle-dl"]

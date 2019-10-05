FROM ubuntu:18.04

WORKDIR app/

RUN apt-get update \
    && apt-get install -y ffmpeg python3 python3-pip wget \
    && pip3 install yle-dl \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["yle-dl"]

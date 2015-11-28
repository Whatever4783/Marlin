FROM ioft/armhf-debian:jessie

RUN sed 's/main/main non-free contrib/' /etc/apt/sources.list > /tmp/sources.list && \
    mv /tmp/sources.list /etc/apt/sources.list && \
    apt-get update && \
    env DEBIAN_FRONTEND=noninteractive apt-get dist-upgrade -y && \
    env DEBIAN_FRONTEND=noninteractive apt-get install -yq \
        arduino \
        python-pip \
    && apt-get clean \
    && pip install --compile -U pyserial

#ENTRYPOINT ["/usr/bin/xosview"]
CMD arduino

FROM ubuntu:20.10

RUN echo 'deb http://old-releases.ubuntu.com/ubuntu groovy main multiverse restricted universe' > /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu groovy-updates main multiverse restricted universe' >> /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu groovy-security main multiverse restricted universe' >> /etc/apt/sources.list

RUN apt-get update && \
    apt-get install -y openssh-client tcpdump git vim autoconf libssl-dev zlib1g-dev make && \
    apt-get clean

WORKDIR /data

CMD ["/bin/bash"]
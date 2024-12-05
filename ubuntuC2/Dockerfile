FROM ubuntu:18.10

RUN echo 'deb http://old-releases.ubuntu.com/ubuntu cosmic main multiverse restricted universe' > /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu cosmic-updates main multiverse restricted universe' >> /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu cosmic-security main multiverse restricted universe' >> /etc/apt/sources.list

RUN apt-get update && \
    apt-get install -y openssh-client tcpdump && \
    apt-get clean

WORKDIR /data

CMD ["/bin/bash"]

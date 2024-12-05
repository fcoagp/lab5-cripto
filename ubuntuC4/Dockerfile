FROM ubuntu:22.10

# Actualizar los repositorios a las versiones antiguas y configurar el sistema base.
RUN echo 'deb http://old-releases.ubuntu.com/ubuntu kinetic main multiverse restricted universe' > /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu kinetic-backports main multiverse restricted universe' >> /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu kinetic-proposed main multiverse restricted universe' >> /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu kinetic-updates main multiverse restricted universe' >> /etc/apt/sources.list && \
    echo 'deb http://old-releases.ubuntu.com/ubuntu kinetic-security main multiverse restricted universe' >> /etc/apt/sources.list

# Instalar las herramientas necesarias, incluido openssh-server para el archivo sshd_config.
RUN apt-get update && \
    apt-get install -y openssh-client tcpdump vim autoconf libssl-dev zlib1g-dev make openssh-server && \
    apt-get clean

# Configuración de usuarios y SSH.
RUN echo 'root:root' | chpasswd && \
    useradd -m -d /home/prueba -s /bin/bash prueba && \
    echo 'prueba:prueba' | chpasswd && \
    sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    mkdir -p /var/run/sshd

EXPOSE 22

WORKDIR /data

CMD ["/usr/sbin/sshd", "-D"]

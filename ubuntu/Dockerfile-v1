FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive \
    USR_HOME=/home/tool \
    PATH=$PATH:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN set -x && \
    apt-get update -y && \
#    apt-get install -y software-properties-common && \
#    apt-get update -y && \
    apt-get install -y wget curl iputils-ping net-tools telnet traceroute  netcat dnsutils && \
    apt-get install -y proxychains && \
    apt-get clean

# Running as non-root user.

RUN set -x && \
    useradd tool && \
    [ `id -u tool` -eq 1000 ] && \
    [ `id -g tool` -eq 1000 ] && \
    mkdir -p /home/tool && \
    chown -R tool:tool /home/tool/

WORKDIR $USR_HOME

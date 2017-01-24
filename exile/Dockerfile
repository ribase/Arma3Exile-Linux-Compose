FROM debian:jessie
MAINTAINER Jessy <jessytheripper@gmail.com>

USER root
RUN apt-get update && apt-get -y upgrade
RUN dpkg --add-architecture i386 && apt-get update && apt-get -y install libstdc++6:i386 libtbb2:i386 unzip net-tools
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qy install mysql-client

RUN useradd -u 2000 -m -d /home/steam/ -s /bin/bash steam

USER steam

ADD server.cfg /tmp/server.cfg
ADD modsetup.sh /tmp/modsetup.sh

ENV MOD_SCRIPT /tmp/modsetup.sh


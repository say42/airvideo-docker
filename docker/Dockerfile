FROM ubuntu:xenial

RUN apt-get update -q
RUN apt-get dist-upgrade -y

# Install software
RUN apt-get install -y software-properties-common
RUN apt-add-repository multiverse
RUN apt-get update -q
RUN apt-get install -y vlc avahi-daemon less vim
RUN adduser --uid 1000 --disabled-password --disabled-login airvideo
# Localization
RUN apt-get install -y locales
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

VOLUME /export/video
VOLUME /home/airvideo/AirVideoServer
WORKDIR /home/airvideo/AirVideoServer

EXPOSE 45601
EXPOSE 45633

# Make work dirs for volumes

USER airvideo
CMD ./start.sh

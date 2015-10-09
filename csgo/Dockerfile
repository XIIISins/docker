FROM ubuntu:latest

MAINTAINER xiiisins

ENV CSGO_VERSION LATEST

RUN apt-get update &&\
    apt-get -qqy install bsdmainutils tmux mailutils postfix lib32gcc1 libstdc++6
    
RUN useradd csgoserver &&\
    su - csgoserver

RUN mkdir -p /opt/csgo && cd /opt/csgo &&\
    wget http://gameservermanagers.com/dl/csgoserver &&\
    chmod +x csgoserver &&\
    ./csgoserver install

ADD start_csgo.sh /start-csgo

EXPOSE 27015 27015/udp 27020 27005

USER csgoserver
VOLUME /opt
WORKDIR /opt/csgo
CMD ["/start-csgo"]

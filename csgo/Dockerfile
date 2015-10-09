FROM ubuntu:latest

MAINTAINER xiiisins

ENV CSGO_VERSION LATEST

RUN apt-get update &&\
    apt-get -qqy install bsdmainutils wget tmux mailutils postfix lib32gcc1 libstdc++6 &&\
    useradd csgoserver 

RUN mkdir -p /opt/csgo && chown csgoserver:csgoserver /opt/csgo
    
RUN su - csgoserver -c "cd /opt/csgo &&\
    wget http://gameservermanagers.com/dl/csgoserver &&\
    chmod +x csgoserver &&\
    ./csgoserver auto-install"

ADD start_csgo.sh /start-csgo

EXPOSE 27015 27015/udp 27020 27005

USER csgoserver
VOLUME /opt
WORKDIR /opt/csgo
CMD ["/start-csgo"]

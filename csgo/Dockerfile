FROM ubuntu:latest

MAINTAINER xiiisins

ENV CSGO_VERSION LATEST

RUN apt-get update &&\
    apt-get -qqy install bsdmainutils wget tmux mailutils postfix lib32gcc1 libstdc++6 &&\
    groupadd csgoserver && useradd -m -g csgoserver 

RUN su - csgoserver -c "\
if [ -d /home/csgoserver ]; then \
wget http://gameservermanagers.com/dl/csgoserver &&\
chmod +x csgoserver &&\
./csgoserver auto-install;\
else exit; \
fi\
"

ADD start_csgo.sh /start-csgo

EXPOSE 27015 27015/udp 27020 27005

USER csgoserver
VOLUME /opt
WORKDIR /opt/csgo
CMD ["/start-csgo"]

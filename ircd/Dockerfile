FROM ubuntu:latest

RUN apt-get update

RUN apt-get install -y hybserv ircd-hybrid vim

ADD ircd.conf /etc/ircd-hybrid/ircd.conf
RUN chown irc:irc /etc/ircd-hybrid/ircd.conf
RUN mkdir -p /var/run/ircd
RUN chown irc:irc /var/run/ircd
RUN sed -i s'#/var/run/ircd:/usr/sbin/nologin#/var/run/ircd:/bin/bash#g' /etc/passwd

EXPOSE 6666:6666

ENTRYPOINT su irc -c "/usr/sbin/ircd-hybrid -pidfile /var/run/ircd/ircd-hybrid.pid -foreground"

FROM mysql:8.0.27

RUN apt-key adv --keyserver http://repo.mysql.com/RPM-GPG-KEY-mysql-2022 --recv-key 467B942D3A79BD29

RUN apt-get update && apt-get install -y lsb-release apt-utils wget curl nmap ncat

RUN wget https://repo.percona.com/apt/percona-release_latest.$(lsb_release -sc)_all.deb
RUN dpkg -i percona-release_latest.$(lsb_release -sc)_all.deb

RUN percona-release enable-only tools release
RUN apt-get update
RUN apt-get install -y percona-xtrabackup-80=8.0.27-19-1.$(lsb_release -sc)

EXPOSE 3307
#CMD ["/bin/bash"]
ENTRYPOINT [ "xtrabackup" ]
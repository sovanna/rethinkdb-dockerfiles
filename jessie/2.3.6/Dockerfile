FROM debian:jessie

MAINTAINER Daniel Alan Miller <dalanmiller@rethinkdb.com>

ENV RETHINKDB_PACKAGE_VERSION 2.3.6~0jessie

RUN apt-get update \
  && apt-get install wget -y \
  && wget -qO- https://download.rethinkdb.com/apt/pubkey.gpg | apt-key add -v - \
  && echo "deb http://download.rethinkdb.com/apt jessie main" > /etc/apt/sources.list.d/rethinkdb.list \
  && apt-get update \
  && apt-get install -y rethinkdb=$RETHINKDB_PACKAGE_VERSION \
  && rm -rf /var/lib/apt/lists/*

VOLUME ["/data"]

WORKDIR /data

CMD ["rethinkdb", "--bind", "all"]

#   process cluster webui
EXPOSE 28015 29015 8080

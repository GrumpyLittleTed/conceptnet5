FROM postgres:9.6
MAINTAINER Rob Speer <rob@luminoso.com>

# Install system dependencies (the overall form of this command is recommended by https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
RUN apt-get update \
  && apt-get install -y coreutils diffutils wget gzip \
  && rm -rf /var/lib/apt/lists/*

ADD 10-download.sh /docker-entrypoint-initdb.d/10-download.sh
ADD 20-load-db.sql /docker-entrypoint-initdb.d/20-load-db.sql
ADD 30-done.sh /docker-entrypoint-initdb.d/30-done.sh

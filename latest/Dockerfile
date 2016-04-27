# WE Bridge SymfonyApp + PostgreSQL driver
#
# VERSION 0.1.0

FROM phpmentors/symfony-app:php56
MAINTAINER Thomas Barthelemy <thomas.barthelemy@webridge.asia>

RUN apt-get update -q && \
    apt-get install --no-install-recommends php5-pgsql php5-apcu -qy && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /var/tmp/*

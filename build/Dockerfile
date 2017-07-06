FROM mainiak/p7zip as downloader

ENV PHPROXY_VER='PHProxy%200.5b2%20mod%20SSE+ARKA%2020100825.7z'

WORKDIR /usr/src
 
RUN wget http://sebsauvage.net/temp/$PHPROXY_VER && \
    p7zip -d PHProxy*.7z && \
    mv PHProxy* PHProxy

FROM php:apache

MAINTAINER swoopla <p.vibet@adacis.net>

WORKDIR /var/www/html

COPY --from=downloader /usr/src/PHProxy .

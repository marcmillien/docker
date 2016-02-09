FROM debian:jessie

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update \
 && apt-get dist-upgrade --no-install-recommends -q -o Dpkg::Options::="--force-confold" --force-yes -y \
 && apt-get install --no-install-recommends -q -o Dpkg::Options::="--force-confold" --force-yes -y \
    python-pip \
 && apt-get clean

RUN pip install pelican markdown

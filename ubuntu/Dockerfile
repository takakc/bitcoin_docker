FROM ubuntu:25.04

RUN apt-get update && apt-get install -y \
  git \
  vim \
  libtool \
  g++ \
  libboost-all-dev \
  pkg-config \
  bsdmainutils \
  make \
  autoconf

COPY ./setting/bashrc /tmp/
RUN cat /tmp/bashrc >>~/.bashrc
RUN rm -f /tmp/bashrc

RUN cd /var/ && git clone https://github.com/bitcoin/bitcoin.git
RUN cd /var/bitcoin/ &&  git checkout v28.0 && ./autogen.sh && ./configure && make

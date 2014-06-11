# Io Language
#
# VERSION 0.0.1

FROM debian:stable
MAINTAINER Craig Steinberger "cjs@readyfireaim.org"

RUN apt-get update

RUN apt-get install -y apt-utils wget unzip build-essential cmake libreadline-dev
RUN apt-get install -y libjpeg-dev libpng-dev libtiff-dev 
RUN apt-get install -y libevent-dev libyajl-dev libmemcached-dev libssl-dev libode-dev
RUN apt-get install -y libpcre3-dev 
RUN apt-get install -y libfreetype6-dev 
RUN apt-get install -y libncurses-dev 
RUN apt-get install -y libxml2-dev 
RUN apt-get install -y libgmp3-dev 
RUN apt-get install -y libglfw-dev 
RUN apt-get install -y libcairo-dev libgtkmm-2.4-dev 
RUN apt-get install -y libsqlite3-dev 
RUN apt-get install -y libffi-dev 
RUN apt-get install -y libogg-dev uuid-dev


RUN mkdir /tmp/iobuild
WORKDIR /tmp/iobuild

RUN wget --no-check-certificate https://github.com/stevedekorte/io/archive/2013.12.04.zip -O io-lang.zip
RUN unzip io-lang.zip

WORKDIR /tmp/iobuild/io-2013.12.04

RUN mkdir build

WORKDIR build

RUN cmake -DCMAKE_BUILD_TYPE=release ..
RUN make all
RUN make install
RUN ldconfig

WORKDIR /tmp
# RUN rm -rf /tmp/iobuild

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Define default command.
CMD ["/bin/bash"]

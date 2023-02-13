FROM ubuntu:18.04
LABEL xwzhu="xwzhu7@iflytek.com"
ARG DEBIAN_FRONTEND=noninteractive
WORKDIR /home

RUN apt-get update
RUN apt-get install jq -y

COPY ./cmake-3.5.0.tar.gz /home/
RUN tar -zxvf cmake-3.5.0.tar.gz
WORKDIR /home/cmake-3.5.0
RUN apt-get install build-essential -y
RUN ./bootstrap && make -j8 && make install
RUN cp ./bin/cmake /usr/bin/
RUN apt-get install vim -y
RUN echo -e "deb http://dk.archive.ubuntu.com/ubuntu/ xenial main\ndeb http://dk.archive.ubuntu.com/ubuntu/ xenial universe" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get install gcc-4.8 -y
RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.8 20
RUN apt-get install zip -y
RUN apt-get install unzip -y
RUN apt-get install curl -y
RUN apt-get install wget -y

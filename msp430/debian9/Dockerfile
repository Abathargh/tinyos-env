FROM debian:9-slim

ENV TINYOS_ROOT_DIR=/tinyos
ENV TR=${TINYOS_ROOT_DIR}

ENV CLASSPATH=.:$TR/support/sdk/java/tinyos.jar
ENV PYTHONPATH=$TR/support/sdk/python:$PYTHONPATH


RUN mkdir -p /usr/share/man/man1mkdir -p /usr/share/man/man1
RUN apt-get update && apt-get -y install wget git build-essential stow automake autoconf libtool \
    libc6-dev graphviz python3 python3-serial

RUN wget -O - http://tinyprod.net/repos/debian/tinyprod.key | apt-key add -
RUN echo "deb http://tinyprod.net/repos/debian stretch   main" >> /etc/apt/sources.list.d/tinyprod-debian.list
RUN echo "deb http://tinyprod.net/repos/debian msp430-46 main" >> /etc/apt/sources.list.d/tinyprod-debian.list
RUN apt-get update && apt-get -y install nesc tinyos-tools-devel msp430-46 

WORKDIR /tinyos
RUN git clone https://github.com/tinyos/tinyos-main . && \
    apt-get -y remove wget git && apt-get -y autoremove  


CMD [""]

FROM docker.io/debian:bullseye-20211201-slim

RUN apt update && apt upgrade -y
RUN apt install -y git  xz-utils make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev

WORKDIR /tmp/
ADD https://www.python.org/ftp/python/3.6.15/Python-3.6.15.tar.xz Python.tar.xz
RUN tar -xf Python.tar.xz

WORKDIR /tmp/Python-3.6.15
RUN  ./configure --enable-optimizations --with-ensurepip=install
RUN make -j 8
RUN make altinstall

FROM debian:buster
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y && apt dist-upgrade -y
RUN apt install -y git curl locales python3 build-essential python3-dev python3-pip
RUN apt install -y chromium
RUN pip3 install mkdocs-material WeasyPrint mkdocs mkdocs-with-pdf
ENV LC_ALL=C.UTF-8
RUN dpkg-reconfigure locales
